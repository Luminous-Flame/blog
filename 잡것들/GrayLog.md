- MongoDB
	- ## MongoDB 커뮤니티 에디션 설치[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#install-mongodb-community-edition "이 제목에 대한 영구 링크")

패키지 관리자를 사용하여 MongoDB Community Edition을 설치하려면 다음 단계를 따르세요 `apt`.

1

### 패키지 관리 시스템에서 사용되는 공개 키 가져오기[![](https://www.mongodb.com/docs/manual/assets/link.svg)] 

MongoDB 공개 GPG 키를 가져오기
[https://pgp.mongodb.com/server-7.0.asc](https://pgp.mongodb.com/server-7.0.asc)

```
curl -fsSL https://pgp.mongodb.com/server-7.0.asc | \   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \   --dearmor
```

2

### MongoDB용 목록 파일 만들기[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#create-a-list-file-for-mongodb "이 제목에 대한 영구 링크")

`/etc/apt/sources.list.d/mongodb-org-7.0.list`사용 중인 Ubuntu 버전에 대한 목록 파일을 만듭니다 .

우분투 22.04(제미)

우분투 20.04(포컬)

`/etc/apt/sources.list.d/mongodb-org-7.0.list` Ubuntu 22.04(Jammy)용 파일을 만듭니다 .

```
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```

root@snort-02:/etc/apt/sources.list.d# ll
total 20
drwxr-xr-x 2 root root 4096 Oct 19 12:29 ./
drwxr-xr-x 8 root root 4096 Oct 19 12:18 ../
-rw-r--r-- 1 root root  147 Oct 19 12:29 mongodb-org-7.0.list
-rw-r--r-- 1 root root   68 Oct 19 12:18 wp_es.list
-rw-r--r-- 1 root root   85 Oct 17 18:40 wp_ppa.list

### 로컬 패키지 데이터베이스 다시 로드[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#reload-local-package-database "이 제목에 대한 영구 링크")

로컬 패키지 데이터베이스를 다시 로드하려면 다음 명령을 실행하십시오.

```
sudo apt-get update
```

4

### MongoDB 패키지 설치[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#install-the-mongodb-packages "이 제목에 대한 영구 링크")

MongoDB의 최신 안정 버전이나 MongoDB의 특정 버전을 설치할 수 있습니다.

최신 버전의 MongoDB를 설치하세요.

MongoDB의 특정 릴리스 설치

최신 안정 버전을 설치하려면 다음을 실행하십시오.

```
sudo apt-get install -y mongodb-org
```

선택 과목. 사용 가능한 MongoDB 버전을 지정할 수 있지만 에서는 `apt-get`최신 버전을 사용할 수 있게 되면 패키지를 업그레이드합니다. 의도하지 않은 업그레이드를 방지하려면 현재 설치된 버전에서 패키지를 고정할 수 있습니다.

```
echo "mongodb-org hold" | sudo dpkg --set-selectionsecho "mongodb-org-database hold" | sudo dpkg --set-selectionsecho "mongodb-org-server hold" | sudo dpkg --set-selectionsecho "mongodb-mongosh hold" | sudo dpkg --set-selectionsecho "mongodb-org-mongos hold" | sudo dpkg --set-selectionsecho "mongodb-org-tools hold" | sudo dpkg --set-selections
```

Ubuntu에 MongoDB를 설치하는 동안 발생한 오류 문제 해결에 대한 도움말은 [문제 해결](https://www.mongodb.com/docs/manual/reference/installation-ubuntu-community-troubleshooting/#std-label-install-ubuntu-troubleshooting) 가이드를 참조하세요.

## MongoDB 커뮤니티 에디션 실행[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#run-mongodb-community-edition "이 제목에 대한 영구 링크")

### 한도 고려사항[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#ulimit-considerations "이 제목에 대한 영구 링크")

대부분의 Unix 계열 운영 체제는 프로세스가 사용할 수 있는 시스템 리소스를 제한합니다. 이러한 제한은 MongoDB 작업에 부정적인 영향을 미칠 수 있으므로 조정해야 합니다. 플랫폼에 권장되는 설정은 [UNIX `ulimit`설정을](https://www.mongodb.com/docs/manual/reference/ulimit/) 참조하세요 .

/etc/security/limits.conf/
* soft nofile 102400
* soft nproc 102400
* hard nproc 102400
* hard nofile 81920
* hard memlock unlimited
* hard core unlimited

## 메모

MongoDB 4.4부터 `ulimit`열린 파일 수 값이 `64000`.

### 디렉토리[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#directories "이 제목에 대한 영구 링크")

패키지 관리자를 통해 설치한 경우 설치 중에 데이터 디렉터리 `/var/lib/mongodb`와 로그 디렉터리가 생성됩니다.`/var/log/mongodb`

기본적으로 MongoDB는 `mongodb`사용자 계정을 사용하여 실행됩니다. MongoDB 프로세스를 실행하는 사용자를 변경하는 경우 데이터 및 로그 디렉터리에 대한 권한도 수정하여 이 사용자에게 이러한 디렉터리에 대한 액세스 권한을 부여 **해야 합니다 .**

### 구성 파일[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#configuration-file "이 제목에 대한 영구 링크")

공식 MongoDB 패키지에는 [구성 파일](https://www.mongodb.com/docs/manual/reference/configuration-options/#std-label-conf-file) ( `/etc/mongod.conf`)이 포함되어 있습니다. 이러한 설정(예: 데이터 디렉터리 및 로그 디렉터리 사양)은 시작 시 적용됩니다. 즉, MongoDB 인스턴스가 실행되는 동안 구성 파일을 변경하는 경우 변경 사항을 적용하려면 인스턴스를 다시 시작해야 합니다.

### 절차[![](https://www.mongodb.com/docs/manual/assets/link.svg)](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#procedure "이 제목에 대한 영구 링크")

시스템에서 MongoDB Community Edition을 실행하려면 다음 단계를 따르세요 . 이 지침에서는 Ubuntu 에서 제공하는 비공식 패키지가 아닌 공식 패키지를 사용하고 있으며 기본 설정을 사용하고 있다고 가정합니다.`mongodb-org``mongodb`

**시스템 초기화**

프로세스를 실행하고 관리하려면 [`mongod`](https://www.mongodb.com/docs/manual/reference/program/mongod/#mongodb-binary-bin.mongod)운영 체제에 내장된 [init 시스템을](https://www.mongodb.com/docs/manual/reference/glossary/#std-term-init-system) 사용하게 됩니다 . **최신 버전의 Linux는 systemd** (명령 사용 )를 사용하는 경향이 있는 반면, 이전 버전의 Linux는 **System V init** (명령 사용 ) `systemctl`을 사용하는 경향이 있습니다 .`service`

플랫폼이 어떤 초기화 시스템을 사용하는지 확실하지 않은 경우 다음 명령을 실행하십시오.

```
ps --no-headers -o comm 1
```

그런 다음 결과에 따라 아래에서 적절한 탭을 선택합니다.

- `systemd`- 아래 **systemd(systemctl)** 탭을 선택합니다.
    
- `init`- 아래 **System V Init(서비스)** 탭을 선택합니다.




proxmox일 경우 cpu type host로 해야 데몬이 정상 작동 함.
![[Pasted image 20231020085957.png]]



![[Pasted image 20231020093452.png]]
`Environment="MONGODB_CONFIG_OVERRIDE_NOFORK=1"`는 MongoDB 서버를 실행할 때 사용하는 환경 변수 중 하나입니다. 이 환경 변수는 MongoDB 서버의 동작 방식을 조정하는 데 사용됩니다. 여기에서 `MONGODB_CONFIG_OVERRIDE_NOFORK`은 환경 변수의 이름이고, `1`은 그 값입니다.

`MONGODB_CONFIG_OVERRIDE_NOFORK` 환경 변수는 MongoDB 서버가 백그라운드에서 실행될 때 포크(fork)하는 동작을 조절하는 데 사용됩니다. 기본적으로 MongoDB 서버는 포그라운드(foreground)에서 실행되며, 이 환경 변수가 설정되지 않으면 MongoDB 서버가 백그라운드로 포크(fork)되지 않습니다. 백그라운드에서 실행되면 서버는 제어 터미널을 반환하고 프로세스가 백그라운드에서 계속 실행됩니다.

`MONGODB_CONFIG_OVERRIDE_NOFORK=1` 설정은 MongoDB 서버가 백그라운드에서 실행될 때 포크(fork)하지 않도록 막는 역할을 합니다. 즉, MongoDB 서버가 포그라운드에서 실행될 것입니다. 이러한 설정은 일반적으로 디버깅 목적으로 사용되며, 서버 동작을 모니터링하거나 문제 해결을 위해 로깅 및 디버깅을 수행할 때 유용합니다.

일반적으로 MongoDB는 백그라운드에서 실행되도록 설정하며, `MONGODB_CONFIG_OVERRIDE_NOFORK`를 사용하여 이 동작을 변경하는 것은 특정 상황 또는 디버깅 목적으로 필요한 경우에만 권장됩니다.


소켓 문제로 보임 /tmp/소켓 파일을 지우고 재시작 하던가 리부트 해야함
/etc/mongod.conf 에서  아래 부분 잘못 수정 하면 이런거 뜸
```
# network interfaces
net:
  port: 27017
  bindIp: 127.0.0.1
```


10.5.0.0 으로 해도 안됨. 0.0.0.0으로 하니 멀쩡해짐
근데 보안상 안좋으니, security 설정 활성화 하라고 함

```
# network interfaces
net:
  port: 27017
  bindIp: 0.0.0.0

security:
  authorization: enabled
```

나중에 안건데
**[중요] replica set 구성은 “security: enable” 상태에서는 설정되지 않는다 → 나중에 key로 대체**



  
rs.initiate(
{
_id : "rs0",
members : [
{ _id:0, host: "10.1.5.2:27017"},
{ _id:1, host: "10.1.5.3:27017"},
{ _id:2, host: "10.1.5.4:27017"}
]
}
)

![[Pasted image 20231020101203.png]]


뭔가 이상하다 이렇게 잘 될리가 없다.
역시 health check 부분 0으로 뜬다 통신 안되는거야 이거
![[Pasted image 20231020101954.png]]


아 이거지,
![[Pasted image 20231020114940.png]]

7.0 개 쓰레기 같은거 6.0으로 다시깔았다.


cfg.members.forEach(function(member) { if (member.host === "10.1.5.2:27017") { member.priority = 2; } })



rs.reconfig({ _id: "6532046acd366c5645f8ff6e", version: 1, 
members: [
{ _id: 0, host: "10.1.5.2:27017" }, 
{ _id: 1, host: "10.1.5.3:27017" }, 
{ _id: 2, host: "10.1.5.4:27017", \arbiterOnly: true } 
] })


1. ```
    mongod --port 27021 --dbpath /var/lib/mongodb --replSet rs0  --bind_ip localhost
    ```