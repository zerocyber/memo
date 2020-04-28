# memo
메모 및 참고사항 기록용



## 2020-04-28
* Docker MySQL 컨테이너를 8버전으로 띄운 후 툴에서 접속이 안되는 현상
 - 8버전부터는 인증 플러그인을 caching_sha2_password 방식을 사용
 - 드라이버에서 지원을 안하는 경우 접속에러가 발생
 - 컨테이너를 띄울 때 다음과 같은 방식으로 명령어를 실행하여 해결
 docker run -p 3306:3306 --name mysql_80 -e MYSQL_ROOT_PASSWORD=password -d mysql:8 mysqld --default-authentication-plugin=mysql_native_password
