# embedded_pc_knu
산업용PC 설치 매뉴얼 (경북대)


> 블로그형 간단한 설명 : https://www.embeddedarm.com/blog/practical-guide-to-getting-started-with-the-ts-7250-v2/ 
> 정식 매뉴얼 : https://docs.embeddedarm.com/TS-7250-V2

## Booting

### eMMC 부팅

하드웨어 점퍼3을 on에서 off로(microsd로 부팅 X)


시리얼케이블로 연결

#### 리눅스
```
minicom -s
```

> 115200 8N1 No No


#### 윈도우
![KakaoTalk_20200506_135616723_01](https://user-images.githubusercontent.com/56524306/81162029-83293080-8fc7-11ea-989e-eaf4b5bd8713.png)


파워연결하면 eMMC로 부팅


```
# Boot automatically to Debian:
tshwctl --setjp=1
reboot
```

![KakaoTalk_20200506_135616723_02](https://user-images.githubusercontent.com/56524306/81162050-8a503e80-8fc7-11ea-9e8f-4654c68527a8.png)
![KakaoTalk_20200506_135616723_03](https://user-images.githubusercontent.com/56524306/81162056-8ae8d500-8fc7-11ea-82f8-74c77ffd3055.png)


SD로 부팅됨


> login id : root


/etc/network/interfaces eth0 주석풀고 eth0.1로 수정한 뒤 ip 변경


종료

![KakaoTalk_20200506_135616723_04](https://user-images.githubusercontent.com/56524306/81162058-8b816b80-8fc7-11ea-9952-60b84c9ea02a.png)
![KakaoTalk_20200506_135616723_05](https://user-images.githubusercontent.com/56524306/81162060-8b816b80-8fc7-11ea-874d-950add248abf.png)


### MicroSD 부팅


하드웨어 점퍼3을 off에서 on으로(microsd로 부팅) 변경


시리얼 연결상태로 부팅


## Network configuration


/etc/network/interfaces eth0 주석풀고 eth0.1로 수정한 뒤 ip 변경

```
/etc/init.d/networking restart
```


ifconfig로 eth0.1 아이피 확인


외부 ping 테스트


## Miscellaneous


df -h로 sd카드인지 확인


```
passwd root
adduser parsivel # useradd하면 안됨
passwd parsivel
su parsivel
vi .bash_profile # alias 풀기
```


![KakaoTalk_20200506_135616723_06](https://user-images.githubusercontent.com/56524306/81162062-8c1a0200-8fc7-11ea-9ddd-ed823c1510ef.png)
![KakaoTalk_20200506_135616723_07](https://user-images.githubusercontent.com/56524306/81162064-8c1a0200-8fc7-11ea-886c-51ccc424f50a.png)
