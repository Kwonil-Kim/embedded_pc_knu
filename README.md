# embedded_pc_knu
산업용PC 설치 매뉴얼 (경북대)

## Booting

하드웨어 점퍼3을 on에서 off로(microsd로 부텅 X)


시리얼케이블로 연결

```
minicom -s
```

> 115200 8N1 No No


파워연결하면 eMMC로 부팅


```
# Boot automatically to Debian:
tshwctl --setjp=1
reboot
```


SD로 부팅됨


> login id : root


/etc/network/interfaces eth0 주석풀고 eth0.1로 수정한 뒤 ip 변경


종료


하드웨어 점퍼3을 off에서 on으로(microsd로 부팅) 변경


시리얼 연결상태로 부팅


## Network configuration


/etc/network/interfaces eth0 주석풀고 eth0.1로 수정한 뒤 ip 변경

'''
/etc/init.d/networking restart
'''


ifconfig로 eth0.1 아이피 확인


외부 ping 테스트


## Miscellaneous


df -h로 sd카드인지 확인


'''
passwd root
adduser parsivel # useradd하면 안됨
passwd parsivel
su parsivel
vi .bash_profile # alias 풀기
'''
