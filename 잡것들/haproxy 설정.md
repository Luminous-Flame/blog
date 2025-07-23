
l7 트래픽 보고 거기 맞춰서 테스트 진행
설정 아무것도 없이 (auto) 로 테스트 해보고 load랑 htop 보고 필요하면 numa 설정 넣고 테스트 



 2024-02-15 10:07:57 ⌚  slb-03 in ~
 
○ → cat /etc/hapee-2.8/hapee-lb.cfg
global
	log 127.0.0.1 len 65534 local1 notice

	log 10.3.11.162:514 len 65534 local0
	log 10.3.11.162:514 len 65534 local0 notice
	user               hapee-lb
	group              hapee
	chroot             /var/empty
	stats socket       /var/run/hapee-2.8/hapee-lb.sock user hapee-lb group hapee mode 660 level admin expose-fd listeners
	stats timeout      10m
	module-path        /opt/hapee-2.8/modules
	cpu-map	auto:1/1-40 0-39
	description	SLB-03
	daemon
	log-send-hostname

	tune.ssl.cachesize        1000000
	tune.ssl.lifetime         120
	tune.ssl.default-dh-param 2048
	tune.maxrewrite           409600
	tune.bufsize              409600
	ulimit-n                  2048000
	maxconn                   716800
	spread-checks             4

	ca-base              /etc/ssl/certs
	crt-base             /etc/ssl/private
	ssl-dh-param-file    /etc/hapee-2.8/certs/dhparam.pem

	ssl-default-bind-ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384
	ssl-default-bind-ciphersuites TLS_AES_128_GCM_SHA256:TLS_AES_256_GCM_SHA384:TLS_CHACHA20_POLY1305_SHA256
	ssl-default-bind-options prefer-client-ciphers no-sslv3 no-tlsv10 no-tlsv11 no-tls-tickets

	ssl-default-server-ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384
	ssl-default-server-ciphersuites TLS_AES_128_GCM_SHA256:TLS_AES_256_GCM_SHA384:TLS_CHACHA20_POLY1305_SHA256
	ssl-default-server-options no-sslv3 no-tlsv10 no-tlsv11 no-tls-tickets

defaults
	mode               http
	log                global
	option             httplog
	option             dontlognull
	option             forwardfor except 127.0.0.0/8
	option             redispatch
	retries            3
	timeout connect    10s
	timeout client     300s
	timeout server     300s

listen admin-web-stats
	bind 10.3.11.68:9080
	maxconn 100
	mode http
	http-request use-service prometheus-exporter if { path /metrics }
	stats enable
	stats hide-version
	stats show-node
	stats show-legends
	stats refresh 10
	stats uri /
	stats realm slb-03\ Statistics

frontend  fe-astg-legacy-http
	bind 10.3.11.68:80
	bind 10.3.11.68:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/hapee/certs/wildcard_widerplanet_com.pem
	mode	http
	timeout client 2m
	option	forwardfor
	option	httplog
	description "Legacy ASTG frontend for netscaler servername: slb-03_68"

	acl php_molecule path_beg /delivery/moleculeid
	acl php_wpg_a path_beg /delivery/wpg_a.php
	acl php_wpg path_beg /delivery/wpg.php
	acl php_wpp path_beg /delivery/wpp.php
	acl php_rd path_beg /delivery/rd.php

	acl java_wpc path_beg /delivery/wpc.php
	acl java_storage path_beg /delivery/storage
	acl java_duration path_beg /log/duration

	use_backend be-astg-php-80 if php_molecule
	use_backend be-astg-php-80 if php_wpg_a
	use_backend be-astg-php-80 if php_wpg
	use_backend be-astg-php-80 if php_wpp
	use_backend be-astg-php-80 if php_rd

	use_backend be-astg-java-90 if java_wpc
	use_backend be-astg-java-90 if java_storage
	use_backend be-astg-java-90 if java_duration

	default_backend	be-astg-php-80

backend     be-astg-php-80
	balance leastconn
	mode    http
	fullconn    40960
	option  http-server-close
	option  http-keep-alive
	option  prefer-last-server
	option  httpchk GET /index.php
	timeout http-keep-alive 5s
	timeout connect 5000
	timeout server  50000

	http-check expect status 200
	http-check  expect rstring 200\ OK
	http-check  disable-on-404
	http-request    add-header X-Forwarded-Proto https if { ssl_fc }
	default-server  inter 2s rise 2 fall 5

	server  astg-41 10.2.1.41:80 weight 50 check
	server  astg-42 10.2.1.42:80 weight 50 check
	server  astg-43 10.2.1.43:80 weight 50 check
	server  astg-44 10.2.1.44:80 weight 50 check
	server  astg-45 10.2.1.45:80 weight 50 check
	server  astg-47 10.2.1.47:80 weight 50 check
	server  astg-48 10.2.1.48:80 weight 50 check
	server  astg-50 10.2.1.50:80 weight 50 check

backend     be-astg-java-90
	balance leastconn
	mode    http
	fullconn    40960
	option  http-server-close
	option  http-keep-alive
	option  prefer-last-server
	option  httpchk GET /index.php
	timeout http-keep-alive 5s
	timeout connect 5000
	timeout server  50000

	http-check expect status 200
	http-check  expect rstring 200\ OK
	http-check  disable-on-404
	http-request    add-header X-Forwarded-Proto https if { ssl_fc }
	default-server  inter 2s rise 2 fall 5

	server  astg-41 10.2.1.41:90 weight 50 check
	server  astg-42 10.2.1.42:90 weight 50 check
	server  astg-43 10.2.1.43:90 weight 50 check
	server  astg-44 10.2.1.44:90 weight 50 check
	server  astg-45 10.2.1.45:90 weight 50 check
	server  astg-47 10.2.1.47:90 weight 50 check
	server  astg-48 10.2.1.48:90 weight 50 check
	server  astg-50 10.2.1.50:90 weight 50 check





$ cat /etc/haproxy/haproxy.cfg | grep -v "#"
global
    log 10.3.11.161:21514 len 65534 local3
    log 10.3.11.161:21514 len 65534 local3 notice
    chroot /var/lib/haproxy
    stats socket /run/haproxy/admin.sock mode 660 level admin expose-fd listeners
    stats timeout 30s
    user haproxy
    group haproxy
    nbthread 56
    cpu-map auto:1/1-8		0-7
    cpu-map auto:1/9-16		8-15
    cpu-map auto:1/17-24	16-23
    cpu-map auto:1/25-32	24-31
    cpu-map auto:1/33-40	32-39
    cpu-map auto:1/41-48	40-47
    cpu-map auto:1/57-64	56-63

    daemon
    tune.ssl.cachesize        1000000
    tune.ssl.lifetime         120
    tune.ssl.default-dh-param 2048
    tune.maxrewrite           409600
    tune.bufsize              409600
    ulimit-n                  2048000
    maxconn                   716800
    spread-checks             4

    ca-base              /etc/ssl/certs
    crt-base             /etc/ssl/private
    ssl-dh-param-file    /etc/haproxy/certs/dhparam.pem


    ssl-default-bind-ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384
    ssl-default-bind-ciphersuites TLS_AES_128_GCM_SHA256:TLS_AES_256_GCM_SHA384:TLS_CHACHA20_POLY1305_SHA256
    ssl-default-bind-options prefer-client-ciphers no-sslv3 no-tlsv10 no-tlsv11 no-tls-tickets

    ssl-default-server-ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384
    ssl-default-server-ciphersuites TLS_AES_128_GCM_SHA256:TLS_AES_256_GCM_SHA384:TLS_CHACHA20_POLY1305_SHA256
    ssl-default-server-options no-sslv3 no-tlsv10 no-tlsv11 no-tls-tickets

defaults
    log     global
    mode    http

    option  log-health-checks
    option  log-separate-errors
    option  httplog
    option  splice-auto
    option  socket-stats

    option    dontlognull
    option    forwardfor except 127.0.0.0/8
    option    redispatch

    timeout connect    10s
    timeout client     10s
    timeout server     10s

    fullconn        409600

    retries    3

resolvers cnsdns
    nameserver ns1 10.3.11.11:53
    nameserver ns2 10.3.11.12:53
    nameserver ns3 10.3.11.13:53
    resolve_retries 30
    timeout retry 2s
    hold valid 10s
    accepted_payload_size 8192

resolvers awsdns
    nameserver ns1 205.251.195.87:53
    nameserver ns2 205.251.199.41:53
    nameserver ns3 205.251.197.59:53
    nameserver ns4 205.251.192.192:53
    resolve_retries 30
    timeout retry 2s
    hold valid 10s
    accepted_payload_size 8192


listen admin
    bind 10.3.11.71:9080
    maxconn 100
    mode http
    http-request use-service prometheus-exporter if { path /metrics }
    option dontlog-normal
    option dontlognull
    log 127.0.0.1:10514 len 65535 local0 info
    log 127.0.0.1:10514 len 65535 local0 notice
    stats enable
    stats hide-version
    stats show-node
    stats show-legends
    stats refresh 60
    stats uri /
    stats realm Haproxy\ Statistics
    stats admin if TRUE



frontend    fe-admixer-http
    bind    103.105.159.10:80
    bind    103.105.159.70:80
    bind    103.105.159.10:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.70:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_am_http hdr(host) -i ax-am.widerplanet.com
    description "Admixer - ax-am.widerplanet.com"
    default_backend be-ade-http


frontend    fe-lgcnstg-http
    bind    103.105.159.12:80
    bind    103.105.159.72:80
    bind    103.105.159.12:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.72:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httpslog
    acl ACL_ax_lg_http hdr(host) -i ax-lg.widerplanet.com
    description "lgcns(tg) - ax-lg.widerplanet.com"
    default_backend be-ade-http

frontend    fe-widerplanet-http
    bind    103.105.159.13:80
    bind    103.105.159.73:80
    bind    103.105.159.13:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.73:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httpslog
    acl ACL_ax_tg_http hdr(host) -i ax-tg.widerplanet.com
    description "Wider Planet - ax-tg.widerplanet.com"
    default_backend be-ade-http

frontend    fe-manplushb-http
    bind    103.105.159.14:80
    bind    103.105.159.74:80
    bind    103.105.159.14:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.74:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_mp_http hdr(host) -i ax-mp.widerplanet.com
    description "Manplus HB - ax-mp.widerplanet.com"
    default_backend be-ade-http

frontend    fe-kakaoexternal-http
    bind    103.105.159.15:80
    bind    103.105.159.75:80
    bind    103.105.159.15:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.75:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    option  httplog
    option  forwardfor
    timeout client 2m
    acl ACL_ax_ke_http hdr(host) -i ax-ke.widerplanet.com
    description "Kakao External - ax-ke.widerplanet.com"
    default_backend be-ade-http


frontend    fe-kakaointernal-http
    bind    103.105.159.17:80
    bind    103.105.159.77:80
    bind    103.105.159.17:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.77:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    option  httplog
    option  forwardfor
    timeout client 2m
    acl ACL_ax_ka_http hdr(host) -i ax-ka.widerplanet.com
    description "Kakao Internal - ax-ka.widerplanet.com"
    default_backend be-ade-http

frontend    fe-googledisplay-http
    bind    103.105.159.18:80
    bind    103.105.159.78:80
    bind    103.105.159.18:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.78:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httpslog
    acl ACL_ax_gd_http hdr(host) -i ax-gd.widerplanet.com
    description "Google Display - ax-gd.widerplanet.com"
    default_backend be-ade-http


frontend    fe-bidence-http
    bind    103.105.159.20:80
    bind    103.105.159.80:80
    bind    103.105.159.20:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.80:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_bn_http hdr(host) -i ax-bn.widerplanet.com
    description "Bidence - ax-bn.widerplanet.com"
    default_backend be-ade-http

frontend    fe-mobmixer-http
    bind    103.105.159.21:80
    bind    103.105.159.81:80
    bind    103.105.159.21:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.81:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_mb_http hdr(host) -i ax-mb.widerplanet.com
    description "Mobmixer - ax-mb.widerplanet.com"
    default_backend be-ade-http

frontend    fe-lgcns-http
    bind    103.105.159.22:80
    bind    103.105.159.82:80
    bind    103.105.159.22:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.82:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_lc_http hdr(host) -i ax-lc.widerplanet.com
    description "LG CNS - ax-lc.widerplanet.com"
    default_backend be-ade-http

frontend    fe-admixerrtb-http
    bind    103.105.159.23:80
    bind    103.105.159.83:80
    bind    103.105.159.23:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.83:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_ad_http hdr(host) -i ax-ad.widerplanet.com
    description "Admixer RTB - ax-ad.widerplanet.com"
    default_backend be-ade-http

frontend    fe-cashwalkrtb-http
    bind    103.105.159.24:80
    bind    103.105.159.84:80
    bind    103.105.159.24:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.84:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_cr_http hdr(host) -i ax-cr.widerplanet.com
    description "Cashwalk RTB - ax-cr.widerplanet.com"
    default_backend be-ade-http

frontend    fe-cauly-http
    bind    103.105.159.25:80
    bind    103.105.159.85:80
    bind    103.105.159.25:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.85:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_ca_http hdr(host) -i ax-ca.widerplanet.com
    description "Cauly - ax-ca.widerplanet.com"
    default_backend be-ade-http

frontend    fe-exelbidrtb-http
    bind    103.105.159.26:80
    bind    103.105.159.86:80
    bind    103.105.159.26:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.86:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_ex_http hdr(host) -i ax-ex.widerplanet.com
    description "Exelbid RTB - ax-ex.widerplanet.com"
    default_backend be-ade-http


frontend    fe-nhnace-http
    bind    103.105.159.28:80
    bind    103.105.159.88:80
    bind    103.105.159.28:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.88:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_na_http hdr(host) -i ax-na.widerplanet.com
    description "NHN Ace - ax-na.widerplanet.com"
    default_backend be-ade-http

frontend    fe-natertb-http
    bind    103.105.159.29:80
    bind    103.105.159.89:80
    bind    103.105.159.29:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.89:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_nt_http hdr(host) -i ax-nt.widerplanet.com
    description "Nate RTB - ax-nt.widerplanet.com"
    default_backend be-ade-http

frontend    fe-adpie-http
    bind    103.105.159.30:80
    bind    103.105.159.90:80
    bind    103.105.159.30:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.90:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_pi_http hdr(host) -i ax-pi.widerplanet.com
    description "Adpie RTB - ax-pi.widerplanet.com"
    default_backend be-ade-http

frontend    fe-adpopcorn2-http
    bind    103.105.159.31:80
    bind    103.105.159.91:80
    bind    103.105.159.31:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.91:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_po_http hdr(host) -i ax-po.widerplanet.com
    description "Adpopcorn - ax-po.widerplanet.com"
    default_backend be-ade-http



frontend    fe-tpmnrtb-http
    bind    103.105.159.34:80
    bind    103.105.159.94:80
    bind    103.105.159.34:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.94:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_tp_http hdr(host) -i ax-tp.widerplanet.com
    description "TPMN RTB - ax-tp.widerplanet.com"
    default_backend be-ade-http


frontend    fe-smaato-http
    bind    103.105.159.36:80
    bind    103.105.159.96:80
    bind    103.105.159.36:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.96:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_sm_http hdr(host) -i ax-sm.widerplanet.com
    description "Smaato - ax-sm.widerplanet.com"
    default_backend be-ade-http

frontend    fe-dablertb-http
    bind    103.105.159.37:80
    bind    103.105.159.97:80
    bind    103.105.159.37:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.97:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httpslog
    acl ACL_ax_da_http hdr(host) -i ax-da.widerplanet.com
    description "Dable RTB - ax-da.widerplanet.com"
    default_backend be-ade-http

frontend    fe-pubnative-http
    bind    103.105.159.38:80
    bind    103.105.159.98:80
    bind    103.105.159.38:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.98:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_pn_http hdr(host) -i ax-pn.widerplanet.com
    description "Pubnative - ax-pn.widerplanet.com"
    default_backend be-ade-http

frontend    fe-manplusrtb-http
    bind    103.105.159.39:80
    bind    103.105.159.99:80
    bind    103.105.159.39:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.99:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_mr_http hdr(host) -i ax-mr.widerplanet.com
    description "Manplus RTB - ax-mr.widerplanet.com"
    default_backend be-ade-http


frontend    fe-admixerg-http
    bind    103.105.159.41:80
    bind    103.105.159.101:80
    bind    103.105.159.41:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.101:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_ag_http hdr(host) -i ax-ag.widerplanet.com
    description "admixger(G) - ax-ag.widerplanet.com"
    default_backend be-ade-http

frontend    fe-genieworks-http
    bind    103.105.159.42:80
    bind    103.105.159.102:80
    bind    103.105.159.42:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.102:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_gw_http hdr(host) -i ax-gw.widerplanet.com
    description "Genieworks - ax-gw.widerplanet.com"
    default_backend be-ade-http

frontend    fe-newid-http
    bind    103.105.159.43:80
    bind    103.105.159.103:80
    bind    103.105.159.43:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.103:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_id_http hdr(host) -i ax-id.widerplanet.com
    description "NEW ID - ax-id.widerplanet.com"
    default_backend be-ade-http

frontend    fe-signalplay-http
    bind    103.105.159.44:80
    bind    103.105.159.104:80
    bind    103.105.159.44:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.104:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_sp_http hdr(host) -i ax-sp.widerplanet.com
    description "Signalplay - ax-sp.widerplanet.com"
    default_backend be-ade-http

frontend    fe-techlabsrtb-http
    bind    103.105.159.45:80
    bind    103.105.159.105:80
    bind    103.105.159.45:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.105:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout    client 2m
    option    forwardfor
    option    httplog
    acl ACL_ax_tb_http hdr(host) -i ax-tb.widerplanet.com
    description "Techlabsrtb - ax-tb.widerplanet.com"
    default_backend be-ade-http


backend    be-ade-http
    balance   leastconn
    mode      http
    option    http-server-close
    option    http-keep-alive
    option    prefer-last-server
    option    httpchk GET /index.php
    timeout   http-keep-alive 5s
    http-check expect string 200\ OK
    http-check disable-on-404
    http-request add-header X-Forwarded-Proto https if { ssl_fc }
    default-server inter 2s rise 2 fall 5

    server  ade-01 10.2.5.111:80 weight 50 check
    server  ade-02 10.2.5.112:80 weight 50 check
    server  ade-03 10.2.5.113:80 weight 60 check
    server  ade-04 10.2.5.114:80 weight 50 check
    server  ade-05 10.2.5.115:80 weight 50 check
    server  ade-06 10.2.5.116:80 weight 50 check
    server  ade-07 10.2.5.117:80 weight 50 check
    server  ade-08 10.2.5.118:80 weight 50 check
    server  ade-09 10.2.5.119:80 weight 50 check
    server  ade-10 10.2.5.120:80 weight 50 check
    server  ade-11 10.2.5.121:80 weight 50 check
    server  ade-12 10.2.5.122:80 weight 50 check
    server  ade-13 10.2.5.123:80 weight 50 check
    server  ade-14 10.2.5.124:80 weight 50 check
    server  ade-15 10.2.5.125:80 weight 50 check
    server  ade-16 10.2.5.126:80 weight 50 check
    server  ade-17 10.2.5.127:80 weight 50 check
    server  ade-18 10.2.5.128:80 weight 50 check
    server  ade-19 10.2.5.129:80 weight 50 check
    server  ade-20 10.2.5.130:80 weight 50 check
    server  ade-21 10.2.5.131:80 weight 50 check
    server  ade-22 10.2.5.132:80 weight 50 check
    server  ade-23 10.2.5.133:80 weight 50 check
    server  ade-24 10.2.5.134:80 weight 50 check
    server  ade-25 10.2.5.135:80 weight 50 check
    server  ade-26 10.2.5.136:80 weight 50 check
    server  ade-27 10.2.5.137:80 weight 50 check
    server  ade-28 10.2.5.138:80 weight 50 check
    server  ade-29 10.2.5.139:80 weight 50 check
    server  ade-30 10.2.5.140:80 weight 50 check
    server  ade-31 10.2.5.141:80 weight 50 check
    server  ade-32 10.2.5.142:80 weight 50 check
    server  ade-33 10.2.5.143:80 weight 50 check
    server  ade-34 10.2.5.144:80 weight 50 check
    server  ade-35 10.2.5.145:80 weight 50 check
    server  ade-36 10.2.5.146:80 weight 50 check
    server  ade-37 10.2.5.147:80 weight 50 check
    server  ade-38 10.2.5.148:80 weight 50 check
    server  ade-39 10.2.5.149:80 weight 50 check
    server  ade-40 10.2.5.150:80 weight 50 check
    server  ade-41 10.2.5.151:80 weight 50 check
    server  ade-42 10.2.5.152:80 weight 50 check
    server  ade-43 10.2.5.153:80 weight 50 check
    server  ade-44 10.2.5.154:80 weight 50 check
    server  ade-45 10.2.5.155:80 weight 50 check
    server  ade-46 10.2.5.156:80 weight 50 check
    server  ade-47 10.2.5.157:80 weight 50 check
    server  ade-48 10.2.5.158:80 weight 50 check
    server  ade-49 10.2.5.159:80 weight 50 check
    server  ade-50 10.2.5.160:80 weight 50 check
    server  ade-51 10.2.5.161:80 weight 50 check
    server  ade-52 10.2.5.162:80 weight 50 check
    server  ade-53 10.2.5.163:80 weight 50 check
    server  ade-54 10.2.5.164:80 weight 50 check
    server  ade-55 10.2.5.165:80 weight 50 check
    server  ade-56 10.2.5.166:80 weight 50 check
    server  ade-57 10.2.5.167:80 weight 50 check
    server  ade-58 10.2.5.168:80 weight 50 check
    server  ade-59 10.2.5.169:80 weight 50 check
    server  ade-60 10.2.5.170:80 weight 50 check