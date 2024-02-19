
## ref
- jsmin6330/autolb#1

### compose
- 수민님 dockerhub 사용하기 함
- complse.yml 파일내 설정


## 블로그는 아래와 같이 도커 허브에 배포(참고용)
```
sudo docker build -t gitblog .
sudo docker tag gitblog soominjeong/gitblog:0.1.0
sudo docker push soominjeong/gitblog:0.1.0
```
## compose
```
sudo docker pull nginxproxy/nginx-proxy

sudo docker compose -f compose/autolb/compose.yml up -d --build --force-recreate
# sudo docker compose -f compose/autolb/compose.yml ls
sudo docker compose -f compose/autolb/compose.yml  up -d --scale blog=5
# sudo docker compose -f compose/autolb/compose.yml ps
sudo docker compose -f compose/autolb/compose.yml  up -d --build --force-recreate
```
여러 명령어들이 있는데, 각각을 설명해드릴게요:

1. `sudo docker pull nginxproxy/nginx-proxy`: 이 명령어는 Docker Hub에서 `nginxproxy/nginx-proxy` 이미지를 다운로드합니다. 이 이미지는 nginx reverse proxy를 위한 공식 이미지입니다.

2. `sudo docker compose -f compose/autolb/compose.yml up -d --build --force-recreate`: 이 명령어는 Docker Compose를 사용하여 지정된 YAML 파일을 기반으로하여 컨테이너를 빌드하고 실행합니다. `-d` 플래그는 컨테이너를 백그라운드에서 실행하도록 합니다. `--build` 플래그는 컨테이너를 빌드하도록 합니다. `--force-recreate` 플래그는 이미 존재하는 컨테이너를 강제로 재생성합니다.

3. `sudo docker compose -f compose/autolb/compose.yml up -d --scale blog=5`: 이 명령어는 Docker Compose를 사용하여 지정된 YAML 파일을 기반으로하여 `blog` 서비스를 5개의 인스턴스로 확장하여 실행합니다. `-d` 플래그는 컨테이너를 백그라운드에서 실행하도록 합니다.

4. `sudo docker compose -f compose/autolb/compose.yml up -d --build --force-recreate`: 이미 설명한 명령어와 동일하지만, 빌드하고 실행하는 명령어입니다.

## view
chrome 브라우저에서 http://aws.google.com:9889/
확인 위해 window hosts 파일 수정 필요(관리자권한으로 수정)
호스트 파일 경로: C:\Windows\System32\drivers\etc

127.0.0.1 aws.google.com

## chk
compose.yml 고치고 적용하기 위해

$ sudo docker compose -f compose.yml up -d --build --force-recreate

### nGrinder실행
```
$ pwd /home/jsmin630/app/ng/ngrinder-agent 
$ ./run_agent.sh
```
 이걸 먼저 실행하고


```
$ pwd /home/jsmin630/app/ng/controller 
$ java -jar ngrinder-controller-3.5.8.war
```
이걸 실행하신 다음에

http://localhost:8080/ 접속하시면 됩니다. ngrinder
