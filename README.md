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

