root at cosmos-m-01 in /etc/letsencrypt/live/cosmos.cns.widerlab.io
$ cat make.sh
#!/bin/bash

echo 'certbot certonly --dns-rfc2136 --dns-rfc2136-credentials /etc/letsencrypt/.secrets/rfc2136.ini -d "*.cosmos.cosmos.cns.widerlab.io" -d "*.cosmos.cns.widerlab.io"'

echo 'update /etc/letsencrypt/live/cosmos.cns.widerlab.io/rgw-tls.pem'
cat /etc/letsencrypt/live/cosmos.cns.widerlab.io/privkey.pem /etc/letsencrypt/live/cosmos.cns.widerlab.io/cert.pem /etc/letsencrypt/live/cosmos.cns.widerlab.io/chain.pem > /etc/letsencrypt/live/cosmos.cns.widerlab.io/rgw-tls.pem

echo 'update /etc/ceph/cosmos.cosmos.cns.widerlab.io.pem'
cat /etc/letsencrypt/live/cosmos.cns.widerlab.io/privkey.pem /etc/letsencrypt/live/cosmos.cns.widerlab.io/cert.pem /etc/letsencrypt/live/cosmos.cns.widerlab.io/chain.pem > /etc/ceph/cosmos.cns.widerlab.io.pem

echo 'update /etc/ceph/dashboard_key.pem'
cat /etc/letsencrypt/live/cosmos.cns.widerlab.io/privkey.pem > /etc/ceph/dashboard_key.pem

echo 'update /etc/ceph/dashboard_crt.pem'
cat /etc/letsencrypt/live/cosmos.cns.widerlab.io/cert.pem /etc/letsencrypt/live/cosmos.cns.widerlab.io/chain.pem > /etc/ceph/dashboard_crt.pem

#openssl x509 -noout -text -in /etc/ceph/cosmos.cosmos.cns.widerlab.io.pem

echo 'update cosmos-m-01 certificate grafana'
ceph config-key set mgr/cephadm/cosmos-m-01/grafana_key -i /etc/ceph/dashboard_key.pem
ceph config-key set mgr/cephadm/cosmos-m-01/grafana_crt -i /etc/ceph/dashboard_crt.pem

echo 'update cosmos-m-02 certificate grafana'
ceph config-key set mgr/cephadm/cosmos-m-02/grafana_key -i /etc/ceph/dashboard_key.pem
ceph config-key set mgr/cephadm/cosmos-m-02/grafana_crt -i /etc/ceph/dashboard_crt.pem

echo 'update cosmos-m-03 certificate grafana'
ceph config-key set mgr/cephadm/cosmos-m-03/grafana_key -i /etc/ceph/dashboard_key.pem
ceph config-key set mgr/cephadm/cosmos-m-03/grafana_crt -i /etc/ceph/dashboard_crt.pem

echo 'reconfig grafana'
ceph orch reconfig grafana

echo 'update certificate dashboard'
ceph dashboard set-ssl-certificate -i /etc/ceph/dashboard_crt.pem
ceph dashboard set-ssl-certificate-key -i /etc/ceph/dashboard_key.pem

echo 'sync certificate from remote server'
ansible-playbook -i /etc/ceph/inventory.ini /etc/ceph/cert-sync.yaml









root at cosmos-m-01 in /etc/letsencrypt/live/cns.widerlab.io
$ cat make.sh
#!/bin/bash

echo 'certbot certonly --dns-rfc2136 --dns-rfc2136-credentials /etc/letsencrypt/.secrets/rfc2136.ini -d "*.cosmos.cns.widerlab.io" -d "*.cns.widerlab.io"'

echo 'update /etc/letsencrypt/live/cns.widerlab.io/rgw-tls.pem'
cat /etc/letsencrypt/live/cns.widerlab.io/privkey.pem /etc/letsencrypt/live/cns.widerlab.io/cert.pem /etc/letsencrypt/live/cns.widerlab.io/chain.pem > /etc/letsencrypt/live/cns.widerlab.io/rgw-tls.pem

echo 'update /etc/ceph/cosmos.cns.widerlab.io.pem'
cat /etc/letsencrypt/live/cns.widerlab.io/privkey.pem /etc/letsencrypt/live/cns.widerlab.io/cert.pem /etc/letsencrypt/live/cns.widerlab.io/chain.pem > /etc/ceph/cosmos.cns.widerlab.io.pem

echo 'update /etc/ceph/dashboard_key.pem'
cat /etc/letsencrypt/live/cns.widerlab.io/privkey.pem > /etc/ceph/dashboard_key.pem

echo 'update /etc/ceph/dashboard_crt.pem'
cat /etc/letsencrypt/live/cns.widerlab.io/cert.pem /etc/letsencrypt/live/cns.widerlab.io/chain.pem > /etc/ceph/dashboard_crt.pem

#openssl x509 -noout -text -in /etc/ceph/cosmos.cns.widerlab.io.pem

echo 'update cosmos-m-01 certificate grafana'
ceph config-key set mgr/cephadm/cosmos-m-01/grafana_key -i /etc/ceph/dashboard_key.pem
ceph config-key set mgr/cephadm/cosmos-m-01/grafana_crt -i /etc/ceph/dashboard_crt.pem

echo 'update cosmos-m-02 certificate grafana'
ceph config-key set mgr/cephadm/cosmos-m-02/grafana_key -i /etc/ceph/dashboard_key.pem
ceph config-key set mgr/cephadm/cosmos-m-02/grafana_crt -i /etc/ceph/dashboard_crt.pem

echo 'update cosmos-m-03 certificate grafana'
ceph config-key set mgr/cephadm/cosmos-m-03/grafana_key -i /etc/ceph/dashboard_key.pem
ceph config-key set mgr/cephadm/cosmos-m-03/grafana_crt -i /etc/ceph/dashboard_crt.pem

echo 'reconfig grafana'
ceph orch reconfig grafana

echo 'update certificate dashboard'
ceph dashboard set-ssl-certificate -i /etc/ceph/dashboard_crt.pem
ceph dashboard set-ssl-certificate-key -i /etc/ceph/dashboard_key.pem

echo 'sync certificate from remote server'
ansible-playbook -i /etc/ceph/inventory.ini /etc/ceph/cert-sync.yaml