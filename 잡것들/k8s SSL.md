
- letsencrypts 사용

![[Pasted image 20231020141123.png]]

staging : api (인증서가 발급되지는 않..고 그냥 테스트임 acme.letsencrtpt 랑 통신이 잘 되는지)
https://acme-staging-v02.api.letsencrypt.org/

prod : AWS에서 발급

스테이징으로 테스트 하고 정상 작동 시, prod로 갱신하도록 운영

인증서 요청 차이

annotation 설정해야 함

Host zoneid : 도메인 존 ID
Access Key_id : 유저 계정의 서비스 어카운트 발급 키 (dns_challenge)

새 인증서 발급 때 까지 통상 2분 걸림

cluster issuer : 클러스터 전체
issuer : 특정 네임스페이스

certmanager pod 에서 처리 함
갱신 기간? 언제 체크?
