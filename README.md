# hello-docker
hello-docker

# 📑 목차

1. [**Image List 가져오기**](#1-image-list-가져오기)

2. [**Container List 가져오기**](#2-container-list-가져오기)

3. [**실행중인 Process List 가져오기**](#3-실행중인-process-list-가져오기)

4. [**Image 가져오기**](#4-image-가져오기)

5. [**Image로부터 Container 만들기**](#5-image로부터-container-만들기)

6. [**Container 생성 및 실행하기**](#6-container-생성-및-실행하기)

7. [**Container 시작하기**](#7-container-시작하기)

8. [**Container 중지하기**](#8-container-중지하기)

9. [**Container 삭제하기**](#9-container-삭제하기)

10. [**도커 안으로 진입하기**](#10-도커-안으로-진입하기)

11. [**Image 삭제하기**](#11-image-삭제하기)


## 1. 이미지 List 가져오기
```bash
# -a : --all
docker image list -a
```

## 2. 컨테이너 List 가져오기
```bash
# -a : -all
docker container list -a
```

## 3. 실행중인 Process List 가져오기
```bash
# -a : -all
docker ps -a
```

## 4. Image 가져오기
```bash
# docker pull <이미지 이름>:<이미지 태그>
docker pull mysql:9.5.0
```

## 5. Image로부터 Container 만들기
```bash
# docker run <이미지 이름>:<이미지 태그>
docker run mysql:9.5.0
```

## 6. Container 생성 및 실행하기
``` bash
# docker run [OPTIONS] <이미지 이름>:<이미지 태그>
#
# OPTIONS:
#   --name <컨테이너 이름>
#   -p <호스트Port>:<컨테이너Port>
#   -v <호스트경로>:<컨테이너경로>
#   -e <환경변수KEY>=<값>
#   -d

docker run --name=mydata -p 3306:3306 -v C:/Users/USER/Documents/dockerdata/mysqldata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=docker123 -d mysql:9.5.0
```

## 7. Container 시작하기
```bash
# docker start <컨테이너 아이디 or 컨테이너 이름>
docker start 650698a530f1
docker start myData
```

## 8. Container 중지하기
``` bash
# 멈추지 않은 것은 지워지지 않음.
# docker stop <컨테이너 아이디 or 컨테이너 이름>
docker stop 650698a530f1
docker stop myData
```


## 9. Container 삭제하기
```bash
# docker start <컨테이너 아이디 or 컨테이너 이름>
docker container rm 650698a530f1
docker container rm myData
```

## 10. 도커 안으로 진입하기
``` bash
# docker exec -it <Container Name> bash
docker exec -it myData bash
```

## 11. Image 삭제하기
``` bash
# docker image rm <Image Id>
docker image rm mysql:9.5.0
```
