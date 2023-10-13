# Cisco 기초 명령어.
<br>

## 공장 초기화
mode 버튼을 누른채 전원 on  
switch:  
switch: flash_init  
switch: delete flash:vlan.dat  
switch: boot  

## 초기화 명령어
erase startup-config  
reload  

## 오타방지
no ip domain-lookup

## 이름변경
hostname <새 이름>

## 암호설정
enable secret <비밀번호>

## SSH 엑세스 설정
스위치에 원격으로 엑세스할 수 있습니다.  
ip ssh version 2  
crypto key generate rsa modulus 2048  
line vty 0 15  
transport input ssh  
<br>
사용자 계정 생성
<br>
username <사용자이름> secret <비밀번호>

## 텔넷 차단
line vty 0 15  
transport input ssh  

## 콘솔 연결 암호 설정
line con 0  
password <비밀번호>  
login  


## 시간 설정
시간 설정은 로그 및 보안 인증에 중요합니다.  
clock set HH:MM:SS <월> <일> <년>  
ntp server <NTP 서버 IP 주소>  

## 관리용IP 설정
int vlan 1  
ip address <IP주소> <서브넷마스크>  
no shutdown

## VLAN 설정과 포트 할당 방법
vlan <VLAN 번호>  
name <VLAN 이름>  
exit  
interface range <포트 범위(예: g0/1-24)>  
switchport access vlan <VLAN 번호>  


## 로깅 설정
스위치의 상태와 문제를 실시간으로 모니터링하고  
문제 발생 시 해당 로그 메시지를 확인하여 빠른 대응을 할 수 있습니다.  
logging buffered 4096  
logging console critical



















