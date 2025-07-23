
테스트 1. 기존 설정 동작 테스트
- Citirx에 기존 설정과 동일하게 설정
	- POC-AA vserver 생성 및 poc-ade-01 백엔드 서버 등록
	- Spillover 300으로 설정 후, poc-pbcoffee로 리다이렉트 되도록 설정
- Route53의 ax-aa 도메인에 Citrix POC-AA vserver IP 설정
- ngrinder에서 400커넥션으로 부하 개시하여 Spillover 동작 확인
	- 300개 커넥션 까지 ade 처리
	- 이후 추가로 발생하는 커넥션에 대해서만 Spillover 발생

테스트 2. Haproxy ACL 조건 설정 & 부하 테스트
- Route53의 ax-aa 도메인에 tlb-01 IP 설정
- haproxy 3.0 install 및 ACL 설정

### 2-1. 총 세션 속도 기반 스필오버

**설명 :** `be-ade-http` 백엔드의 세션 속도가 300을 초과할 때 트래픽을 백업 백엔드로 리다이렉트
실패 사유 : 이 설정은 세션 속도(즉, 초당 세션 수)를 기준으로 함. 따라서, 단위 시간당 세션 수 체크이므로 총 연결 수 기준인 스필오버와 맞지 않음

`stick-table type ip size 1m expire 2m store conn_cur acl too_many_conns_backend0 be_sess_rate(be-ade-http) gt 300 use_backend be-pb-coffee-http if too_many_conns_backend0`

### 2-2. 초당 요청 비율 기반 스필오버

**설명 :** 클라이언트 IP별 초당 요청 비율이 300을 초과할 때 트래픽을 백업 백엔드로 리다이렉트
실패 사유 : 이 설정은 클라이언트 IP별 초당 요청 비율을 기준으로 함. 초당 요청 수를 체크하는 방식이므로, 총 연결 수를 기준으로 초과된 트래픽을 리다이렉트하는 것이 아님

`stick-table type ip size 1m expire 1m store http_req_rate(1s) http-request track-sc0 src acl too_many_conns sc_http_req_rate(0) ge 300 use_backend be-pb-coffee-http if too_many_conns`

### 2-3. 개별 서버 연결 수 기반 스필오버

**설명 :** 특정 백엔드 서버의 현재 연결 수가 300을 초과할 때 트래픽을 백업 백엔드로 리다이렉트
실패 사유 : 이 설정은 개별 서버의 현재 연결 수를 기준으로 함. 백엔드 서버 중 하나라도 300을 초과하면 리다이렉트되기 때문에, 원하는 기능인 프론트엔드의 총 연결 수 기준 스필오버와 맞지 않음

`acl too_many_conns_backend0 srv_conn(be-ade-http/poc-ade-01) gt 300 use_backend be-pb-coffee-http if too_many_conns_backend0`

### 2-4. 현재 연결 수 기반 스필오버

**설명 :** 클라이언트 IP별 현재 연결 수가 300을 초과할 때 트래픽을 백업 백엔드로 리다이렉트
실패 사유 : 이 설정은 클라이언트 IP별 현재 연결 수를 기준으로 함. 총 연결 수가 아니라 각 클라이언트별 연결 수를 체크하기 때문에, 원하는 기능인 총 연결 수 기반 스필오버와 다름.

`stick-table type ip size 1m expire 2m store conn_cur http-request track-sc0 src acl too_many_conns sc0_conn_cur gt 300 use_backend be-pb-coffee-http if too_many_conns`

### 2-5. 초당 연결 비율 기반 스필오버

**설명 :** 클라이언트 IP별 초당 연결 비율이 150을 초과할 때 트래픽을 백업 백엔드로 리다이렉트
실패 사유 : 이 설정은 클라이언트 IP별 초당 연결 비율을 기준으로 함. 초당 연결 수를 체크하기 때문에, 총 연결 수와는 다릅니다. 원하는 기능은 총 연결 수를 기준으로 초과된 트래픽을 리다이렉트하는 것입니다.

`stick-table type ip size 1m expire 1s store conn_rate(1s) http-request track-sc0 src acl too_many_conns sc0_conn_rate gt 150 use_backend be-pb-coffee-http if too_many_conns`

### 2-6. 백엔드 총 연결 수 기반 스필오버

**설명:** 백엔드 `be-ade-http`의 총 연결 수가 300을 초과할 때 트래픽을 백업 백엔드로 리다이렉트
**일치점:** 이 설정은 백엔드의 총 연결 수를 기준으로 함. 백엔드 `be-ade-http`의 총 연결 수가 300을 초과할 때 초과된 트래픽만 백업 백엔드로 리다이렉트하기 때문에, 원하는 기능과 일치함

`acl total_conns_above_300 be_conn(be-ade-http) gt 300 use_backend be-pb-coffee-http if total_conns_above_300`

- 테스트 1과 동일하게 ngrinder에서 400커넥션으로 부하 개시하여 Spillover 동작 확인