### 설치 순서
#### 1. CentOS 설치
#### 2. Node.js 설치

1) nvm 설치
~~~
$curl -o- https://raw.githubusercontents.com/creationix/nvm/v0.25.3/install.sh | bash
~~~
2) Node.js 0.12.4 설치
~~~
$ nvm install v0.12.4
$ nvm alias default v0.12.4
~~~
버전 확인
~~~
$ node -v
v0.12.4
~~~
환경파일 수정
~~~
$sudo visudo
~~~

. 첫 번째 수정(env_reset을 무효화)
~~~
Defaults env_reset
          ↓
Defaults ***!***env_reset   ## <--- env_reset에서 방망이 추가됨.
~~~

. 두 번째 수정(HOME을 추가)
~~~
# Defaults env_keep += "HOME"
          ↓
Defaults env_keep += "HOME"  ## <--- 맨 첫글자의 주석 제거
~~~

. 세 번째 수정(sudo 명령어 실행 시 사용할 패스를 덮어쓰지 않도록 주석 처리한다)
~~~
Defaults secure_path = /sbin:/bin:/usr/sbin:/usr/bin
          ↓
# Defaults secure_path = /sbin:/bin:/usr/sbin:/usr/bin    ## <--- 주석처리
~~~

wq! 저장하고 나오기


3) git 설치
~~~
$ sudo yum install git
~~~

4) npm으로 모듈 설치
~~~
$ npm install request
~~~
