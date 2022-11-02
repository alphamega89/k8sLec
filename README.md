# k8sLec

ova 설치
```https://drive.google.com/uc?id=1txvrlpJ_BEsS5VMNsGwh_0A5c0JjtcrM&export=download```

ubuntu 20설치 // 22는 트러블슈팅할게 많아서 실습시 사용안함.
https://releases.ubuntu.com/20.04/

한꺼번에 지우기..
k8s@master1:~/container-ex$ sudo docker rm $(sudo docker ps -aq)

k8s@master1:~/container-ex$ sudo docker rmi $(sudo docker images -aq)


# guest쪽 방화벽 허용처리
sudo ufw status
sudo ufw disable



sudo docker run -d -p 8080:80 nginx
-d 옵션 -- background에서 실행
-p 포트를 사용하기 위한 옵션
8080:80 --------8080포트로 접속시도했을시, 80포트로 처리 하겠다
(포트포워딩)

# 도커파일 작성시 
ex) nano 에디터 사용
$ nano Dockerfile

FROM ubuntu:20.04        <<--------- 실행되는 base OS정보

MAINTAINER onlooker2zip "onlooker2zip@naver.com"  <<---작성자 정보

RUN apt-get update

RUN apt-get install -y nginx   <<--------- 중간에 -y 가 꼭 들어가야한다.. Time Zone 관련에러

WORKDIR /etc/nginx             <<--------- 작업 dir 설정

CMD ["nginx", "-g", "daemon off;"]  <<--------- backgournd 처리 할때 쓰는 옵션

EXPOSE 80                           <<--------- 80 포트를 열때



#kube 설정

k8s@master1:~$ mkdir ~/.kube
k8s@master1:~$ sudo cp /etc/rancher/k3s/k3s.yaml ~/.kube/config
k8s@master1:~$ sudo chown -R $(id -u):$(id -g) ~/.kube
k8s@master1:~$ echo "export KUBECONFIG=~/.kube/config" >> ~/.bashrc
k8s@master1:~$ source ~/.bashrc
