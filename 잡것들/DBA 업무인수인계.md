
ndb-sql-01, 02
management node (ndb_mgm)
- 클러스터 넣고 빼고 하는 작업 가능
- 데이터 디스크 작업 등

ndb에서 궁금한거
- sql 노드는 어느 노드로 들어가도 조회 가능
- 배치성 작업이 있을것.

admindb
- mha에 admindb-m-02 가 승격되도록 설정 되어있음
- s-14 : bi 무거운 쿼리 날리는 용도

cmsdb (productdb-proxy)
- hadoop 에서 rtb 등 리포트 성 데이터

midas 운영
- 잡탕 (스몰서버 모음집)

onsite
- cdp-db

공홈
- aws에 있음
- wp-info 였던 서버
- majunior에서 원격 접속

아틀라시안
- 비트 버킷 (Postgry)
	- 백업만 하고있음
- 위키 지라는 5.7인데, 특정 쿼리 질의시, 느린이슈가 있었는데 8버전부터 완화 되어서 mysql 8.0 사용중




-------서버 별 설정 정보--------

요즘은 utf8mb4 많이 쓴다 함
https://cirius.tistory.com/1769

char set / 문자셋
collation 문자셋의 정렬 https://blog.naver.com/sory1008/223071678680


sql mode == mysql 변수값
- db 안에서 sql 규칙
- ~~STRICT_TRANS_TABLES~~ 엄격한
	- 기본값이 지정되지 않은 테이블 (null 값)이 과거에 존재했어서 해당 룰을 임시로 막아둠
- ERROR_FOR_DIVISION_BY_ZERO
- NO_AUTO_CREATE_USER
- NO_ENGINE_SUBSTITUTION|

admindb 전체 부하가 너무 커서 statdb로 테이블 분리
statdb : 통계 정보
근데 지금은 다시 합침

위의 이유로 vip가 많은데 다쓰지는 않음

백업 방식 : 마스터에 적용된 내용을 백업에 적용하느 방식

마스터 커밋 > 슬레이브가 가져감 > 릴레이 로그 > 슬레이브 db 적용

기본 계정
비밀번호 와이더플래닛
ISMS 검사할땐 패스워드 정책 검사 전에 미리 정책보여주면 안봄




ndb_-----------------------
admindb : admin data, stat data
ndb : openx_v1

chanel-edge에서 작업
프로시저 : 데이터 베이스 작업 내의 함수
프로시저가 openx_v1_stat2 + ADIM데이터를 합쳐서 STAT에 모아줌 
단점 : 관리 힘듦

intermediate 5분에 한번 입력됨
ox_data_summary_ad_hourly

OPENX_V1_STATS  

ox_data_summary_ad_daily_ad  
  d d
ox_data_summary_ad_daily_zone  

ox_data_summary_ad_daily_campaign  

ox_data_summary_ad_daily_zone_ctype

daily 
데이터 보존하여 새로운 테이블에 저장

크론탭 설정 백업 필요
cmsdb-01 /home/sysoper/admin/truncate_win_ratio.sh


----------mha----------

마스터로 승격 될 서버에 resetslave 정보를 날려버림

haproxy 원복 설정

데이터 정합성 확인을 위해 원복은 확인 후 수동으로 원복


----------ndb----------
1번 아니면 2번
메모리에 올라간 db
복구를 위해 스키마는 들고있어야함
계정은 별로 생성해줘야함

sql 노드

----------conf----------

general_log없어도 됨

log_bin 바이너리 로그 인데 보통 활성화 되어있음 적용하려면 디비 재시작 필요  

innodb_force_recovery
로그기반 복구 설정
물리적으로 고장난건 복구 불가

복구 테스트 

flush_log

semisync
옛날엔 플러그인이었는데 기본 기능이 되었다.
마스터 설정을 슬레이브가 동기화가 되었는지 확인하는 설정
마스터 > 슬레이브로 확인 요청을 해서 확인 후 릴레이 로그에 남음

malloc-lib 속도 향상
부적 옵션


xhRlrhseb1!