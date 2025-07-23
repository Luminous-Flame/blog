잡무
	- 2023년 라이센스 관련 조사 (완료)
			https://docs.google.com/spreadsheets/d/1JMzOkAyEORIrXsNMOxPP_EYn9xwfEGYKrcfY8p3fvXA/edit#gid=0
	- admindb 장비 세팅 (완료)
			https://issue.widerlab.io/browse/TS-2781?src=confmacro
	- chanel rm log rolling 적용 (완료)
		https://meet.google.com/nix-dgdb-rsf?authuser=0&hs=122&ijlm=1706236410245
	- 더존 PC 업그레이드 및 서버 IP 변경하여 접속 테스트
	- 사무실 이삿짐 포장 (xox icube 서버 다운)
	- voip-mgmt 착신전환 테스트 및 호스트 배포
	- 구글 드라이브 윈도우 액티브 디렉토리 처럼 사용 가능한지 서치
	- ADE 롤링 restart 모니터링

아틀라시안 업그레이드 관련
	- 아틀라시안 영업/기술지원 방문 요청 메일 (완료)
		  
		제목: 아틀라시안 클라우드 라이센스 마이그레이션 관련 회의 일정 조율 요청
		
		안녕하세요, 와이더플래닛 신환희입니다.
		
		당사에서 현재 사용 중인 아틀라시안 제품의 라이센스를 클라우드로의 마이그레이션을 고려중입니다. 
		
		다음주 목요일에 영업 및 엔지니어와 회의를 통해 라이센스 마이그레이션에 대한 상세한 내용을 논의하려 합니다. 이에 따라 영업직원 및 엔지니어 직원의 참석을 부탁드립니다.
		
		일시: 다음주 목요일, [2024 2/1], [13:00]
		
		참석이 어려운 경우 빠른 시일 내에 대체 일정을 제안해주시면 감사하겠습니다.
		
		확인 후 회신 요청드립니다.
		
		감사합니다.
	- 미팅 정리 (완료)
		- 애드온 서비스
			- 19년도 부터 사용중이며, 사용중인게 많음.
			  - https://marketplace.atlassian.com/ 에서 각각의 기능 확인 가능
				   - 각각의 애드온 클라우드 지원 여부 확인 가능
			  - 애드온 살아있는 것중에 챙길것만 리스트 업 필요  (사용 안하는 애드온 제거 필요)
			  - 클라우드로 마이그레이션 할 때 지원 안 하는 애드온 있을 수 있으며, 별도 구매 필요
		  - 구매 관련
			  - 월간은 우리(와이더)가 직접 구매 / 플래티어는 연간 구매에만 관여
			  - 라이센스 별 인원 (25 / 50 / 100 ...) 구간이 정해져있음 (스탠다드 / 프리미엄) 구분
				  - 계약 중간에 인원 변경 가능
			  - 하드 용량에 따라 요금 구분
			  - 라이센스 간 성능 차이 없음
		 - 비트버킷
			 - 연 요금 따로 있음
			 - 스탠다드는 각자 구매 / 플래티어는 프리미엄만 판다
			 - 용량 테스트 가능 (링크 알려준다고 함)
		   
	 - 문의 사항
		 - 온프레미스로 운영 하려면 어떻게 해야하는가?
			  - '데이터센터' 라는 라이센스가 있는데 이건 500명 이상 부터 지원 가능 (케파 안맞)
		 - 아틀라시안 외부에 공개 없이 내부로만 VPN 설정 가능?
			  - 안 될 가능성 높으나, 문의는 해보겠다 함
		  - 클라우드 ACL 접근 권한 통제
			   - ip 허용 목록으로 구현 가능하나, 화이트 리스트 관리 할 때 VPN 접근이 막히는 문제 있음
		 - 타 플랫폼에서 운영 가능? (AWS 에서 서비스 띄우기)
			  - SAS 서비스라서 불가능
		 - 운영하다가 장애 발생시 (SLA 관련)
			  - 플래티어에 접수 하기
			  - 글로벌 장애일때만 보상 제공
			  - 연간 8시간 이상일때 보상 제공 (99.9%)
		 - 서버 라이센스가 없어진 이유
			  - 구독형으로 돈빨아 먹을라고.
		
	  - 마이그레이션 관련 
		 - 라이센스 2/14 종료 - 모든 보안 및 업데이트 지원 종료
		 - SSO (https://www.atlassian.com/ko/software/access)
			 - crowd > access 로 변경 지원 x (직접 해야함)
			 - access 는 무조건 애저에만 호환 지원 가능 액티브 디렉토리 안됨..
			 - access 설치 후 도메인 인증을 받아서 직원들 일괄 등록
			 - 일일히 애저에 계정 등록하고 아틀라시안 계정 매핑 후 마이그레이션 진행 해야 한다 
				 - 반대로 마이그레이션 후 계정 리 인덱싱 되는가?
					 - 비활성화 되는 유저들에 관하여 서칭이 안될 가능성 있다
				 - 비활성 계정들 일괄 계정으로 통합 가능한가?
					 - 검색 시, 한번에 수만건에 대해서 검색이 되어서 불편 할 수 있다.
				  - 비활성 계정들은 자료들도 날아가는가?
					  - 문서 내용 볼 수 있음. 누가 썼는지만 모를 뿐
		  - 마이그레이션 엔지니어링 지원 비용 있음 
			  - 하루에 100~200만원 선
			  - 당일 해결 기준이며, 초과 시, 해결 후 요금 협의
		  - 마이그레이션 지원
			  - 애드온이 많아서 마이그레이션 지원 2명은 와야할 것 같다 함
			  - 공수도 길 것 같다 함
			  - 용량이 많아서 조금 비싸더라도 시니어가 와야할 것 같음
			  - 직접 하려면 가이드만 받아 볼 수 있음
		  - 착수 시점
			  - 빠르면 3월 초 늦어도 5월 이내를 원함
			  - 4월 추천함 (엔지니어들 스케쥴 때문에)
		
	  - 요청 할 문서
		  - 직접 마이그레이션 진행 시, 마이그레이션 가이드
		  - 현재 라이센스 유지 시, 업그레이드 할 안정화 버전  
		  - 아틀라시안 access 사용 과금 체계
		  - 라이센스 견적 (총 3개)
			  - 지라/위키 100 유저 비트버킷 50 유저 기준으로 견적
				  - 애드온 제외 기본 3개(지라,버킷,위키) 견적 1
				  - 애드온 전부 포함한 견적
					  - 클라우드 지원 없는 애드온을 제외한 견적 2
					  - 클라우드 대체 애드온이 존재하는 경우 추가한 견적 3
		  - 마이그레이션 비용 산정 가능하면 추가 견적
	- 미팅 결과 (완료)
	  - 클라우드로 안감
		  - 시나리오 : 우리는 내부 품의 시도했으나 기안 반려 당함
		  - 라이센스 업그레이드 안한다고 사용하는데 문제 없음
		  - 유저 수 업그레이드 안됨 
			  - 100 유저 라이센스 > 200 유저 라이센스 변경 불가
			  - 현재 사용중인 라이센스 내에서는 자유롭게 유저 추가 삭제 가능
		  - 연간 3200만원 구매 하던거 중단
		  - 버전 업그레이드는 해야 함.
		  - 도커라이징 하면 좋을듯 (완료)
	- 관련 문서 요청 메일 (완료)
		제목: 아틀라시안 클라우드 라이센스로의 마이그레이션 관련 문서 요청
		
		안녕하세요, 와이더플래닛 신환희입니다.
			
		회의에서 논의된 내용을 바탕으로 아래의 문서를 요청드립니다.
			
		1. Cloud License Migration 가이드
			- 현재 사용 중인 제품들을 직접 Migration 할 경우 Migration에 대한 상세한 가이드 문서
		2. 기존 License 버전 업그레이드 가이드
			- 작업 일정이 늦춰질 것을 대비한 현재 사용중인 License(Jira, Bitbucket, Confluence)를 업그레이드 할 수 있는 안정화 버전 정보 및 업그레이드 가이드 문서
		3. 아틀라시안 Access 사용 과금 체계 설명
			- Access 서비스의 과금 체계에 대한 가이드
		4. License 및 Migration 비용 견적
			- 다음 3가지에 대한 견적 부탁드립니다.
				- 애드온 제외 기본 3개 제품(Jira, Bitbucket, Confluence)의 라이센스 견적 1
				- 클라우드 지원이 불가능한 애드온을 제외한 견적 2
				- 클라우드 대체 애드온이 존재하는 경우 추가한 견적 3
		5. Migration 비용 산정 (가능한 경우)
		    - Migration 엔지니어링 지원 비용에 대한 세부적인 산정 및 일정
			
		위의 내용을 토대로 각 항목에 대한 자세한 정보를 문서화 하여 회신 부탁드립니다.
			
		감사합니다. 
	- 정보 확인 요청 
		- [Jira] 
			- 사용중인 버전
			- 이슈, 첨부파일등 전체 용량
			- 프로젝트 수량
		- [Confluence] 
			- 버전
			- 사용중인 컨텐츠(첨부파일) 용량
			- 스페이스 수량
		- [Bitbucket] 
			- 리파지토리 수량
			- 소스코드 용량
		- [Addon] 
			- 구매할 Add-on 목록 확인
		- 

make-leather-new 고치기
	-  Basic_set.yaml
	    - Rocky linux ntp role 사용 안하도록 설정
	    - Rocky linux chrony role 사용하도록 설정
	- Rocky 8, 9
	    - repository 설정 추가
	        - 기존 Base Mirror(외부 repo) 비활성화
	        - widerplanet repository 바라보도록 경로 재 설정
	        - Rocky 8,9에서 사용가능하도록 하나의 파일로 관리
	    - install common package
	        - 미사용 설정 제거
	    - install repel repository 추가 및 지원하지 않는 패키지 설치 시, 에러 허용
	    - rsyslog 패키지 없을경우 설치하도록 변경
	- UpdateCertificate
	    - dns 쿼리문 수정
	    - Ubuntu 16.04 별도 동작하도록 태스크 추가
	- td-agent
	    - 현재 우리 repo에서 debian 계열만 설치 가능하여, debian만 설치하도록 설정

서버 자산 관련
	- 등록 자산 명세 최신화 (완료)
		- 더존 기록
			- 나중에 서버를 추가로 구매 하거나 파기 할때 주기적으로 업데이트 필요
			- 감가상각은 23년도 기준으로 계산 된 것으로 추가 계산 필요
			- 잔존 수량이 실사 수량과 일치 하도록 조정
		- 수량비교 (총 994대)
			- 초과 수량 (더존 자료에 비해 가지고있는게 더 많은 경우)
				- RX2540 M1 :  1대 더 가지고있음
				- RX2540 M4 : 1대 더 가지고있음
				- RX1330 M1 : 2대 더 가지고있음
				- RX1330 M2 : 6대 더 가지고있음
			- 공백 수량 (더존 자료에 비해 가지고있는게 부족 경우)
				- RX1330 M4 : 8대 모자람
				- GX2460 M1 : 1대 모자람
			- 수량 조정
				- RX2540 M1 한대 표기 안함 (다음 파기 때 표기보다 한대 더 버릴 것)
				- RX1330 M1, M2 총 8대 RX1330 M4 표기
				- RX2540 M1  1대 GX2460 M1 표기
			- 파기수량
				- 2020년도 이전 히스토리 참조하여 서버 파기 기록 입력
				- 2023.06.27일에 파기 기록은 저희 서버 대수 맞추기 위해 입력 해둔 것 (품의 필요)
				- 더존비교 시트에 자동 반영 되니 서버 버릴때마다 여기 업데이트
					- https://docs.google.com/spreadsheets/d/10i2tK6EIpdufn_7hYXrDhub3Ehd_9vfp/edit?pli=1#gid=644286060
			- 각 서버 별 시리얼 부여 및 프린트
			- 파기 서버는 숨김처리 (일련번호 부여는 해둠)
			- 현재 실제로 가지고있는 서버에 더존 시트에서 만들어둔 시리얼넘버에 맞춰서 리스트업
				- https://docs.google.com/spreadsheets/d/1eusZ1YqLJZW6ai4V4CIVFy9NKHJnLYcaBlL26RXfPSU/edit#gid=438258595
			- 라벨링
	- 장비 파기 목록화 (완료) 
		- https://docs.google.com/spreadsheets/d/1QXE1CGs2SlJlSQ8z7nXCtzgLPc09YvH5HJlSD947q8U/edit#gid=1655361296
		- https://docs.google.com/spreadsheets/d/10i2tK6EIpdufn_7hYXrDhub3Ehd_9vfp/edit?pli=1#gid=139995081
	- 파기 서버 제원 확인 및 통일

도곡 IDC 철수 (완료) 
	- Q28 열 상면 정리
		- 샤넬 데이터 노드에 마운트 된 디스크 박스 제거 
			- 데이터 노드 제거 아님. (디커미션 후 CPU 리소스 사용함.)
			- yarn log가 디스크에 쌓이고있어서 로그 디렉토리 변경 작업 필요함.
			- 2월 14~16일에 완료 예정 (@김윤정 님.)
	- 도곡 IDC 철수
		- Passback 서버들 철수
			- Q28에 마운트 및 세팅
		- 용도
			- 준비 된 작업에 관한 Passback 용도의 서버
			- 준비 되지 않은 장애 > AWS template terraform 작성
	- 도곡 설정 제거
		- Host 제거
		- DNS 제거 
			- Route 53 제거
			- sproxy 제거
		- 서버 셧다운
	- Q28로 서버 이동

F/W 업그레이드 작업 (2024/02/22) (완료)
	- 방화벽 업그레이드 간, Citrix 사용 불가
		- SLB-03, 04 로 SLB-01, 02에 있는 astg 서비스 이전 (103.105.158.0/24 회수 목적)
		- 교체되어 남은 SLB-01, 02 장비 이용하여 Citrix 대체 LB 세팅 (상면 그대로, 호스트 네임 안 정함)
			- L7에서 BB로 SLB 케이블 이전하여 네트워크 별도 분리 후 Haproxy 세팅 (like RLB)
				- Haproxy - ~~2.9 ?~~  2.8
					- Citrix에서 사용중인 158 대역 서비스 전부 세팅 
					- numa node 부하 테스트
			- SLB 두대는 어떻게 서비스 할 것인가?
				- Active/Active (AWS)
					- 가중치 기반 A 레코드 설정
				- Active/standby (Keepalived)
					- Keepalived
	- 방화벽 업그레이드 (*6시간 이상 예상)
		- 완료 시, Citrix로 서비스 원복
	- CLB 제거
		- Host DNS 제거
		- 장비 셧다운


CN=Administrator,CN=Users,DC=widerlab,DC=com



10.1.251.243


위의 설정들을 가지고 ngrinder에서 부하 테스트를 진행 하였어.

Statistics Report for pid 689147 on tlb-01
> General process information
pid = 689147 (process #1, nbproc = 1, nbthread = 56)
uptime = 0d 0h31m03s
system limits: memmax = unlimited; ulimit-n = 2048000
maxsock = 1792219; maxconn = 716800; maxpipes = 179200
current conns = 1; current pipes = 0/0; conn rate = 0/sec; bit rate = 0.271 kbps
Running tasks: 0/129; idle = 100 %
 	active UP	 	backup UP
active UP, going down		backup UP, going down
active DOWN, going up		backup DOWN, going up
active or backup DOWN  		not checked
active or backup DOWN for maintenance (MAINT)  
active or backup SOFT STOPPED for maintenance  
Note: "NOLB"/"DRAIN" = UP with load-balancing disabled.	Display option:
Scope : 
Hide 'DOWN' servers
Disable refresh
Refresh now
CSV export
JSON export (schema)
External resources:
Primary site
Updates (v2.7)
Online manual
admin	
Queue	Session rate	Sessions	Bytes	Denied	Errors	Warnings	Server
Cur	Max	Limit	Cur	Max	Limit	Cur	Max	Limit	Total	LbTot	Last	In	Out	Req	Resp	Req	Conn	Resp	Retr	Redis	Status	LastChk	Wght	Act	Bck	Chk	Dwn	Dwntme	Thrtle
Frontend		0
2
-	1	2	100	30
31149	1033594
0	0	29					OPEN	
sock-1		 	1	3	0	30	 	 	31149	1033594	0	0	29					OPEN	
Backend	0	0		0	0		0	0	409600	0
0	0s	31149	1033594
0	0		0	0	0	0	31m3s UP	 	0/0	0	0	 	0	 	
fe-aa-http	TestDomain - ax-aa.widerplanet.com
Queue	Session rate	Sessions	Bytes	Denied	Errors	Warnings	Server
Cur	Max	Limit	Cur	Max	Limit	Cur	Max	Limit	Total	LbTot	Last	In	Out	Req	Resp	Req	Conn	Resp	Retr	Redis	Status	LastChk	Wght	Act	Bck	Chk	Dwn	Dwntme	Thrtle
Frontend		0
647
-	0	91	716800	148812
22172988	45685284
0	0	0					OPEN	
sock-1		 	0	0	0	0	 	 	0	0	0	0	0					OPEN	
sock-2		 	0	0	0	0	 	 	0	0	0	0	0					OPEN	
sock-3		 	0	91	0	148812	 	 	22172988	45685284	0	0	0					OPEN	
sock-4		 	0	0	0	0	 	 	0	0	0	0	0					OPEN	
be-ade-http	
		Queue	Session rate	Sessions	Bytes	Denied	Errors	Warnings	Server
Cur	Max	Limit	Cur	Max	Limit	Cur	Max	Limit	Total	LbTot	Last	In	Out	Req	Resp	Req	Conn	Resp	Retr	Redis	Status	LastChk	Wght	Act	Bck	Chk	Dwn	Dwntme	Thrtle
	poc-ade-01	0	0	-	0	640		0
30	-	148812
148812	17m3s	22172988	45685284		0		0	0	0	0	31m3s UP	L7OK/200 in 1ms	50/50	Y	-	0	0	0s	-
Backend	0	0		0	640		0	30	409600	148812
148812	17m3s	22172988	45685284
0	0		0	0	0	0	31m3s UP	 	50/50	1	0	 	0	0s	
Choose the action to perform on the checked servers : 
 
be-pb-coffee-http	
		Queue	Session rate	Sessions	Bytes	Denied	Errors	Warnings	Server
Cur	Max	Limit	Cur	Max	Limit	Cur	Max	Limit	Total	LbTot	Last	In	Out	Req	Resp	Req	Conn	Resp	Retr	Redis	Status	LastChk	Wght	Act	Bck	Chk	Dwn	Dwntme	Thrtle
	poc-pbcoffee-01	0	0	-	0	0		0
0	-	0
0	?	0	0		0		0	0	0	0	31m3s UP	L7OK/200 in 0ms	50/50	Y	-	0	0	0s	-
Backend	0	0		0	0		0	0	409600	0
0	?	0	0
0	0		0	0	0	0	31m3s UP	 	50/50	1	0	 	0	0s	



Statistics Report for pid 683459 on tlb-02
> General process information
pid = 683459 (process #1, nbproc = 1, nbthread = 56)
uptime = 0d 0h31m05s
system limits: memmax = unlimited; ulimit-n = 2048000
maxsock = 1792219; maxconn = 716800; maxpipes = 179200
current conns = 1; current pipes = 0/0; conn rate = 0/sec; bit rate = 1.903 kbps
Running tasks: 0/129; idle = 100 %
 	active UP	 	backup UP
active UP, going down		backup UP, going down
active DOWN, going up		backup DOWN, going up
active or backup DOWN  		not checked
active or backup DOWN for maintenance (MAINT)  
active or backup SOFT STOPPED for maintenance  
Note: "NOLB"/"DRAIN" = UP with load-balancing disabled.	Display option:
Scope : 
Hide 'DOWN' servers
Disable refresh
Refresh now
CSV export
JSON export (schema)
External resources:
Primary site
Updates (v2.7)
Online manual
admin	
Queue	Session rate	Sessions	Bytes	Denied	Errors	Warnings	Server
Cur	Max	Limit	Cur	Max	Limit	Cur	Max	Limit	Total	LbTot	Last	In	Out	Req	Resp	Req	Conn	Resp	Retr	Redis	Status	LastChk	Wght	Act	Bck	Chk	Dwn	Dwntme	Thrtle
Frontend		0
2
-	1	3	100	31
32152	1067958
0	0	30					OPEN	
sock-1		 	1	3	0	31	 	 	32152	1067958	0	0	30					OPEN	
Backend	0	0		0	0		0	0	409600	0
0	0s	32152	1067958
0	0		0	0	0	0	31m5s UP	 	0/0	0	0	 	0	 	
fe-aa-http	TestDomain - ax-aa.widerplanet.com
Queue	Session rate	Sessions	Bytes	Denied	Errors	Warnings	Server
Cur	Max	Limit	Cur	Max	Limit	Cur	Max	Limit	Total	LbTot	Last	In	Out	Req	Resp	Req	Conn	Resp	Retr	Redis	Status	LastChk	Wght	Act	Bck	Chk	Dwn	Dwntme	Thrtle
Frontend		0
948
-	0	328	716800	174279
25967571	14987994
0	0	0					OPEN	
sock-1		 	0	0	0	0	 	 	0	0	0	0	0					OPEN	
sock-2		 	0	0	0	0	 	 	0	0	0	0	0					OPEN	
sock-3		 	0	0	0	0	 	 	0	0	0	0	0					OPEN	
sock-4		 	0	328	0	174279	 	 	25967571	14987994	0	0	0					OPEN	
be-ade-http	
		Queue	Session rate	Sessions	Bytes	Denied	Errors	Warnings	Server
Cur	Max	Limit	Cur	Max	Limit	Cur	Max	Limit	Total	LbTot	Last	In	Out	Req	Resp	Req	Conn	Resp	Retr	Redis	Status	LastChk	Wght	Act	Bck	Chk	Dwn	Dwntme	Thrtle
	poc-ade-01	0	0	-	0	0		0
0	-	0
0	?	0	0		0		0	0	0	0	31m5s UP	L7OK/200 in 1ms	50/50	Y	-	0	0	0s	-
Backend	0	0		0	0		0	0	409600	0
0	?	0	0
0	0		0	0	0	0	31m5s UP	 	50/50	1	0	 	0	0s	
Choose the action to perform on the checked servers : 
 
be-pb-coffee-http	
		Queue	Session rate	Sessions	Bytes	Denied	Errors	Warnings	Server
Cur	Max	Limit	Cur	Max	Limit	Cur	Max	Limit	Total	LbTot	Last	In	Out	Req	Resp	Req	Conn	Resp	Retr	Redis	Status	LastChk	Wght	Act	Bck	Chk	Dwn	Dwntme	Thrtle
	poc-pbcoffee-01	0	0	-	0	939		0
270	-	174279
174279	17m5s	25967571	14987994		0		0	0	0	0	31m5s UP	L7OK/200 in 0ms	50/50	Y	-	0	0	0s	-
Backend	0	0		0	939		0	270	409600	174279
174279	17m5s	25967571	14987994
0	0		0	0	0	0	31m5s UP	 	50/50	1	0	 	0	0s	



