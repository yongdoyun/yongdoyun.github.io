---
title: 리눅스 원격접속을 위한 서버세팅. 
toc: true
toc_sticky: true 

---
## openssh-server 설치  
Ubuntu  
$ sudo apt install openssh-server  

CentOS  
$ yum install openssh-server openssh-clients openssh-askpass  

설치후 sudo vi /etc/ssh/sshd_config 에서 필요에 따라 Port부분, X11부분 주석을 해제한다.  

ps -ef | grep sshd를 이용하여 sshd가 돌아가고 있는지 확인해야함.   


## Job for ssh.service failed because the control process exited with error code. 에러  

### 에러 발생 이유
sshd_config가 유효하지 않음. 잘못 수정함.  

잘못된 부분 찾을 수 있음.  
```bash
$ sudo sshd -t
/etc/ssh/sshd_config 
```

-t는 test mode 옵션. 내가 수정한 sshd_config가 유효한지 알려줌. 오류가 있는 부분을 고치면 정상작동. 
