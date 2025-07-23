
- 동적 배너 이미지 생성
- 노드js로 만들어짐
- aws에서 운영중

노티와 delete는 python 

타임아웃 또는 이미지가 안뜨면 삭제 : backoffice

- 리사이징은 광고주 요청 따라?
- 크기에 맞춰서 자동?
	- ade에서 만들어주는 url가지고 작동함

비정상 요청
200 304 제외
latency 0 이상



중호님 경민님 aws 계정 부여 하기

노티 조치


진입점 controller
express 사용중


service 아래 로직 실행
repository s3, 광고주 사이트에서 가져오도록



에러 핸들링 util 및 app.js

어떤 이미지를 가져오는지 보고싶다면  util 및  image utiles  

qsc : ade에서 url을 만들어서 주는데 만약 클라이언트에서 resize로 크기를 변경할 수 있는데 우리 부하가 높아짐 이 변조를 막기위해 쿼리스트링 체크썸 생성함 테스트 할 때에 이걸로 만들어서 넣어줘야함 (만료 없음)



템플릿 관리
svg 로 관리함 fill={매크로 문자}
원래는 selenium 썼는데 람다에 올리려면 브라우저를 올려서 써야하는데 메모리 사용률 올라가고 패키지 크기도 커져서 이렇게 함


s3 item 
tgimages
resize
native_new

이미지 형식 / 클라이언트 아이디 / 


테스트 
yarn dev


노드 18버전

