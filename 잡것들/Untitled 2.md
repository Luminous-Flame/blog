

frontend fe-manplusrtb-http
    bind    103.105.159.39:80
    bind    103.105.159.99:80
    bind    103.105.159.39:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.99:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout client 2m
    option forwardfor
    option httplog

    stick-table type ip size 1m expire 2m store conn_cur
    http-request track-sc0 src

    acl too_many_conns_backend0 be_conn(be-ade-http/ade-01) gt 300
    acl too_many_conns_backend1 be_conn(be-ade-http/ade-02) gt 300
    acl too_many_conns_backend2 be_conn(be-ade-http/ade-03) gt 300
    # 모든 백엔드 서버에 대해 동일하게 설정

    use_backend be-pb-coffee-http if too_many_conns_backend0 or too_many_conns_backend1 or too_many_conns_backend2
    # 모든 백엔드 서버에 대한 조건 추가

    description "Manplus RTB - ax-mr.widerplanet.com"
    default_backend be-ade-http

frontend fe-manplushb-http
    bind    103.105.159.14:80
    bind    103.105.159.74:80
    bind    103.105.159.14:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    bind    103.105.159.74:443 ssl alpn h2,http/1.1 npn h2,http/1.0,http/1.1 crt /etc/haproxy/certs/wildcard_widerplanet_com.pem
    mode    http
    timeout client 2m
    option forwardfor
    option httplog

    stick-table type ip size 1m expire 2m store conn_cur
    http-request track-sc0 src

    acl too_many_conns_backend0 be_conn(be-ade-http/ade-01) gt 300
    acl too_many_conns_backend1 be_conn(be-ade-http/ade-02) gt 300
    acl too_many_conns_backend2 be_conn(be-ade-http/ade-03) gt 300
    # 모든 백엔드 서버에 대해 동일하게 설정

    use_backend be-pb-coffee-http if too_many_conns_backend0 or too_many_conns_backend1 or too_many_conns_backend2
    # 모든 백엔드 서버에 대한 조건 추가

    description "Manplus HB - ax-mp.widerplanet.com"
    default_backend be-ade-http

backend be-ade-http
    balance leastconn
    mode http
    option http-server-close
    option http-keep-alive
    option prefer-last-server
    option httpchk GET /index.php
    timeout http-keep-alive 5s
    http-check expect string 200\ OK
    http-check disable-on-404
    http-request add-header X-Forwarded-Proto https if { ssl_fc }
    default-server inter 2s rise 2 fall 5
    server ade-01 10.2.5.111:80 weight 50 check
    server ade-02 10.2.5.112:80 weight 50 check
    # 나머지 백엔드 서버 설정 추가

backend be-pb-coffee-http
    balance leastconn
    mode http
    option http-server-close
    option http-keep-alive
    option prefer-last-server
    timeout http-keep-alive 5s
    option httpchk GET /index.php
    http-check expect string 200\ OK
    http-request add-header X-Forwarded-Proto https if { ssl_fc }
    default-server inter 2s rise 2 fall 5
    server pb-coffee-01 10.2.4.11:80 weight 50 check
    server pb-coffee-02 10.2.4.12:80 weight 50 check
    # 나머지 백엔드 서버 설정 추가
