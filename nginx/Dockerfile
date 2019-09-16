#Ubuntu image설치
FROM ubuntu:latest

#Nginx 설치
RUN apt-get update && apt-get install -y -q nginx 

#Nginx시작
CMD [ "nginx", "-g", "daemon off;" ]
