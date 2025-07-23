
host : ase-terra-01 ~ 30
docker 
- 7777~7783
	- ASE API
	- swagger ui
- 24224
	- fluntd

captain에서 배포?

명정님 서버 찾기


​호스트 및 변수 설정

- **호스트**: `{{ wp_target }}`에 정의된 호스트
- **변수**: `wp_app_version`, `wp_app_port`, `wp_fluentd_port`, `wp_restart`, `wp_switch`, `wp_serial`

### 태스크 구성

1. **Pre Tasks**: 작업 실행 전 사전 확인
    - `wp_app_version` 변수가 정의되어 있는지 확인하고, 정의되지 않았다면 메시지 출력
    - `wp_app_port` 및 `wp_fluentd_port`로 지정된 포트가 열려 있는지 확인

1. **역할(Role) 실행**:
    - `init_service`: 포트가 열려있지 않거나, `wp_restart` 변수가 "false"로 설정되어 있으면 실행
    - `switch-service`: 포트가 열려 있으면, 서비스 중단(`down`) 또는 서비스 시작(`up`) 시행
    - `deploy-source`: `wp_restart` 변수가 "false"로 설정되어 있으면 실행
    - `docker-compose`: Docker Compose 실행
    - `fluentd`: Fluentd 설정이 필요한 경우에 실행




 