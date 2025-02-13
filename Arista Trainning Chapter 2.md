![image](https://github.com/user-attachments/assets/7fc6ded1-6054-4595-85f7-ac92a4530f29)## CLI 모드의 종류 및 모드 변경 방법
- EXEC 모드 (EXEC 모드에서는 장비의 기초적인 정보만 확인 가능)
  ex) switch>
- EXEC -> Privileged EXEC 모드 이동(ennnable password가 설정되어 잇다면 PW입력이 필요 ※디폴트 X) 
  ex) switch> enable 
    switch# 
- Privileged EXEC 모드(계정의 권한레벨 (Privileged Level)에 따라 허용된 범위의 정보를 확인 가능
  ex) switch#
- Privileged EXEC -> Global Configuration 모드(config 또는 configuration terminal로 진입)
  ex) switch# config 
    switch(config)#  
- Global Configuration 모드(장비의 기능들의 전반적인 설정이 가능한 모드)
  ex) switch(config)#

--- 

## CLI 모드의 계층 구조 및 이동 방법 

![CLI Mode](https://github.com/user-attachments/assets/60164861-b8a2-47ce-99b2-c9e2d09408c9)

---

## Base Command 
- Help : 명령어 뒤에 "?"를 사용하면 사용가능 한 하위 옵션들이 표시
- no : 설정한 내용을 삭제하고자 할때 동일한 명령어 앞에 'no'를 붙이면 해당 설정이 삭제 (**일부 명령어는 no가 아닌 default로 설정해야 삭제 되는 경우도 존재**)
- Show : 동작상태, 설정상태 등 확인을 할 때 사용 
- 축약 - 명령어 전체를 입력하지 않아도 일부분만 입력이 가능(단, 다른 옵션이 중복되지 않는 텍스트까지 기입) 
- 자동완성 :  일부 명령어를 입력 후 'Tap'키를 사용하면 자동으로 명령어 전체가 기입(단, 텍스트가 중복되지 않아야 함)
- Dir - Flash Disk, System, USB Flash 등 파일 저장소의 파일 리스트 및 정보를 출력
- 결과값 선별 옵션

![결과값 선별 옵션 사용 예시](https://github.com/user-attachments/assets/dceec4d6-f60e-4829-bda1-9a816588bb83)

- 파일 삭제 : delete <Storage:File Name>
- 파일 복사 : copy <Source Storage:File Name><Destination Storage:File Name>
- 페이징 설정 (기본값 : Length 0, Width 0): 
terminal length <0-32767> 
terminal width <0-32767>
- 로깅 모니터 설정(터미널 접속(Telnet, SSH)시에 실시간으로 발생하는 로그를 화면에 출력) : terminal monitor 

--- 

## Configuration Files 

![Configuration Files](https://github.com/user-attachments/assets/ddd4f99c-a3b7-4fba-8b0b-f2a57437f587)

---
#### 호스트 네임 변경과 계정 설정 

![호스트 네임과 계정 설정 방법](https://github.com/user-attachments/assets/5f2af75f-8874-4e08-9dfb-12c2c9cd0b07)

---
#### 도메인 네임 설정 및 DNS 설정 

![도메인 네임 설정](https://github.com/user-attachments/assets/62750efe-4468-44ed-b340-ea784725123f)

---
#### 시간 설정 및 NNTP 설정 

![시간 설정 및 NTP 설정](https://github.com/user-attachments/assets/f808ccf7-70a7-4f21-aa8f-4f51d9f1ec68)

---
#### 시간, NTP 상태 및 동작 확인 방법 

![시간, NTP 상태 및 동작 확인 방법](https://github.com/user-attachments/assets/c2a861bd-c46f-4b12-801f-4b8751e70182)

---
#### 로깅 설정 

![로깅 설정](https://github.com/user-attachments/assets/039d3a8d-6052-46e9-a1f1-d8dea9c07abf)

---
#### SNMP 설정

![SNMP 설정](https://github.com/user-attachments/assets/f83d1f2b-08a3-498b-bf44-f26eabc2d716)

---
#### 배너 설정 

![배너 설정](https://github.com/user-attachments/assets/1ee5a878-7656-4e69-b3d8-890239ce3813)

---
#### 터미널 프로토콜 별 설정 

![터미널 프로토콜 설정](https://github.com/user-attachments/assets/b8648fd9-007c-4d14-a14c-ad8681a48333)

---
#### 관리 인터페이스 설정과 VRF (Virtual Routing and Forwarding)

![관리 인터페이스 설정과 VRF](https://github.com/user-attachments/assets/1d2deffe-e777-42ae-aebb-87dd8f75487c)

---
#### OOB Configuration

![OOB Management](https://github.com/user-attachments/assets/78070907-3b3a-458f-9fe8-3dc1649667d6)

---
#### LLDP (Link Layer Discovery Protocol)

![image](https://github.com/user-attachments/assets/7fe9ae74-5025-4fd3-bb89-6b33286850fa)

---
#### VLAN (Virtual Local Area Network)
- VLAN 생성 및 설정, 확인

![VLAN](https://github.com/user-attachments/assets/b0297dfe-e0f3-4706-8669-e285495dc823)

---

## STP (Spanning-tree)
- 스위치의 기본 동작은 동일 네트워크(VLAN)에 속한 모든 인터페이스로 패킷을 복제하여 전달(Forwarding)
- 네트워크 구성이 복잡성이 증가하게 되면 복제된 동일 패킷이 계속 증가하며 네트워크 내에 흐를 수 있음(LOOP)
- STP는 이를 방지하기 위한 기술로 네트워크 구성을 스스로 판별하고 통신하지 않는 인터페이스를 차단(Blocking)
- 지원 프로토콜 : MSTP, Rapid-PVST, RSTP
- Arista 기본값 : MSTP
 ![STP](https://github.com/user-attachments/assets/fb780a9e-da67-40d8-b78d-6e5b531a58f0)

---
## SVI (Switched VLAN Interface)
Interface VLAN
- Layer 2인 VLAN에 논리적인 인터페이스를 활성화 하여 Layer 3 기능을 사용할 수 있게 하는 기능
- ex) L2 스위치의 관리의 용도(SNMP, NTP, TELNET, SSH, SYSLOG 등)
- Gateway용도 : Inter-VLAN Routing
- Layer 3 Routing
