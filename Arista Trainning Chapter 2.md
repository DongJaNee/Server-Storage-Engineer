![image](https://github.com/user-attachments/assets/e116283e-5f0a-45ae-919e-46a3a151e0a0)![image](https://github.com/user-attachments/assets/7fc6ded1-6054-4595-85f7-ac92a4530f29)## CLI 모드의 종류 및 모드 변경 방법
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

- 프로토콜 변경 방법 

---
## SVI (Switched VLAN Interface)
Interface VLAN
- Layer 2인 VLAN에 논리적인 인터페이스를 활성화 하여 Layer 3 기능을 사용할 수 있게 하는 기능
- ex) L2 스위치의 관리의 용도(SNMP, NTP, TELNET, SSH, SYSLOG 등)
- Gateway용도 : Inter-VLAN Routing
- Layer 3 Routing

#### Interface VLAN 설정

![Interface VLAN 설정](https://github.com/user-attachments/assets/f0d01783-0d19-40ad-bccc-f46544bdf314)

- SVI를 생성하면 설정한 VLAN ID의 네트워크와 자동 매핑되며, 해당 VLAN 내부의 단말 및 장치들과 IP 통신을 수행할 수 있으며, 해당 VLAN의 구성원들은 다른 네트워크와도 통신이 가능하다.
- VLAN에 활성화 된 물리 인터페이스가 없으면, SVI는 상태 Up이 되지 않는다.

---
## InterFace (L2) 
#### Trunk (Tagging) vs Access (U nntagging) 

![image](https://github.com/user-attachments/assets/e065ec6b-86a2-4299-8ee0-99dcf609f36c)

#### Layer2 인터페이스 설정 
- Access Port 설정법

![image](https://github.com/user-attachments/assets/f6260b2d-ee2c-4224-b116-9b700430de45)


- Trunk Port 설정법 

![image](https://github.com/user-attachments/assets/780a5d04-5f7d-483a-9a49-ad438dd3920f)


※ VLAN tag를 인식하지 못하는 장치와 연결될 시에도 통신이 가능하도록 사용되는 기능으로 해당 VLAN에 대해서는 Unntagging 처리되며, Untagged 패킷을 수신한 경우, Native VLAN으로 Taggin 하여 내부 처리 된다. 

## Interface (L3) 
#### Layer 3 인터페이스 설정 
- L3 인터페이스 포트 설정법

![image](https://github.com/user-attachments/assets/636e7c1d-dc3c-4677-85c9-5e9300e94716)

---
## LAG (Link Aggregation) 
#### Link Aggregation
- 물리적으로 여러 개의 링크를 합쳐 논리적으로 하나의 링크처럼 동작시키는 기술
- 제조사 또는 환경에 따라 용어가 달리 사용되나 동일한 카테고리에 속하는 기술 
1) LACP : IEEE 802.3ad에서 제정된 표준화 된 LAG를 위한 프로토콜
2) EtherChannel : Cisco에서 개발된 링크 접합 기술 및 그룹 (= PAgP (Port Aggregatioon Protocol))
3) Port-Channel : 표준으로 제정된 링크 접합 기술 및 그룹
4) Bonding(Bon) : Linux 환경에서 불리는 기술
5) Teamming : Windows 서버 환경에서 불리는 기술
6) LAG(Link Aggregation Group) & Static LAG : 여ㅕ러 개의 링크를 그룹화 하는 표준 기술
7) Port-Group : 가상화 플랫폼에서 가상화 네트워크 내에 가상화 인터페이스를 그룹으로 묶어 관리하는 기술
8) Trunking : Layer 4 제조사들에서 사용되던 용어
- 네트워크 장비 기준, 최대 8개의 링크를 그룹화 가능 (설정은 16개까지 되나 8개는 대기 상태)

![image](https://github.com/user-attachments/assets/b5327812-9e24-43e3-aa30-6d7a7b94ab05)


#### LAG on Arista
- Channel-Group 설정

![image](https://github.com/user-attachments/assets/cb779d9c-22b7-4acf-9522-274790707675)

  
- Channel-Group 상태 확인

![image](https://github.com/user-attachments/assets/594d202e-2a72-4992-bd5b-751c16a7bde8)


---
## FHRP(First Hop Redundanncy Protocool) 
- 다중화 된 라우터 간에 가상 라우터를 생성하여 장애가 발생하더라도 Gateway IP 변경 없이 서비스를 지속 유지 할 수 있는 기술
- FHRP에 속하는 프로토콜
1) VRRP(Virtual Router Redundancy Protocol) : IETF에서 표준화 제정된 게이트웨이 가상화
2) HSRP(Hot Standby Router Protocol) : Cisco에서 개발한 게이트웨이 가상화
3) GLBP(Gateway Load Balancing Protocol) : Cisco에서 개발한 다중 게이트웨이 환경에서 사용가능한 로드 밸런싱이 탑재된 게이트웨이 가상화
- VRRP의 구성
1) Virtual Router : 가상의 IP와 MAC으로 생성되는 가상의 라우터
2) Active Router : Virtual의 역할을 수행하며, 실제 패킷의 전달 및 ARP Request 등의 역할을 수행하는 라우터
3) Standby Router : Active Router가 장애가 발생할 시 그 역할을 이어받아 수행하는 라우터

![image](https://github.com/user-attachments/assets/b956b028-b957-4ec2-8e81-53811643e9a3)

#### VRRP 설정 

![image](https://github.com/user-attachments/assets/cc54feb8-5c5a-4df5-81a9-cd91fb6c8784)


#### VRRP 상태 확인 

![image](https://github.com/user-attachments/assets/4ced5976-61dc-4232-beb2-27c4f9d0fd1a)


#### VARP (Virtual Address Resolution Protocol)
- Layer3 Anycaast Gateway라고도 한다 (DellEMC는 Anycast IP Gateway for VLANs)
- Active-Standby 구성의 단점을 보완하여 Active-Actiive 구성을 구현하는 표준 프로토콜
- Shared Virtual MAC주ㅜ소를 사용하여 Shared Virtual IP 주소에 대한 ARP 및 GARP ( Gratuious ARP)에 대한 요청에 설정된 모든 라우터가 응답을 수행
-Virtual Address는 ARP 및 GARP를 제외한 동작을 하지 않기 때ㅐ문에 라우팅에 사용 불가능(Routing Source로는 사용할 수 없다) 
- **장점**
1) 멤버 장치 모두 Active 역할을 수행하므로 Gateway간 피어링크에 트래픽이 이동할 필요가 없다
2) Gateway로 향하는 패킷을 능동적으로 분산 수신 가능(A장치의 GW는 A스위치, B장치의 GW는 B스위치 같은 식으로 실제로는 먼저 받는 쪽이 수행)
3) ARP 로드 밸런싱 제공
4) 설정의 간편함 

![image](https://github.com/user-attachments/assets/eec9db9b-e728-4ba1-9a38-0f5aeea05bb9)

#### VARP 설정 

![image](https://github.com/user-attachments/assets/cbaa6e83-7416-4566-9817-467859955e3c)

- VMAC주소는 아무거나 써도 무방, Arista 권장은 001c.7300.0099

#### VARP 상태 확인 

![image](https://github.com/user-attachments/assets/523964ec-a9b0-42c8-a1cc-6ed146cc3325)

---
## **Routing** 
- **네트워크에서 데이터 패킷이 출발지에서 목적지까지 전달되는 경로를 결정하는 과정**
- 패킷 헤더에는 출발지 IP 및 MAC과 목적지 IP 및 MAC이 기록되어 있으며 이를 참조하여 경로 결정 연산
- 라우팅의 종료
- 목적지 라우팅(Destination Routing) : 목적지 정보를 참고하여 경로를 선정하는 방식
1) 정적 라우팅(Static Routing) : 목적지에 대한 게이트웨이(Hop)를 직접 지정하는 방식
2) 동적 라우팅(Dynamic Routing) : 소유한 네트워크에 대한 정보를 상호 교환하여 최적의 경로를 선정하는 방식
3) RIP(Routing information Protocol) : 거리 벡터 라우팅 알고리즘으로 목적지와 Hop의 거리(Max. 15)에 따라 경로를 선정
4) EIGRP(Enhanced Inteior Gateway Routing Protocool) : Cisco의 동적 라우팅, 고급 거리 벡터 알고리즘으로 지연, 대역폭, 신뢰성, 부하 등의 요소 사용
5) OSPF(Open Shortest Path First) : 링크 상태 라우팅 알고리즘으로 비용(Cost) 및 대역폭을 기반으로 경로 연산 
6) BGP(Border Gateway Protocol) : 경로 벡터 라우팅 알고리즘으로 경로 속성(Path Attributes)을 사용하며 ISP 망에서 주로 사용
7) IS-IS(Intemediate System to Inermediate System) : 링크 상태 라우ㅜ팅 알고리즘으로 사용자 정의를 기반으로 사용하며 ISP와 통신망 사업자에서 사용

- 소스 라우팅(Source Routinng) : 출발지 정보를 참고하여 경로를 선정하는 방식

#### 라우팅 기능 활성화

![image](https://github.com/user-attachments/assets/116435f0-1962-48dc-a88d-a24e36c23ae8)
- 본 설정이 안되어 있는 경우 Routing은 동작 하지 않는다.


-  라우팅 경로 확인

![image](https://github.com/user-attachments/assets/a097e671-1b57-4aeb-88ce-0177cc554c13)

#### Static Routinng 
- 정적 경로 설정법

![image](https://github.com/user-attachments/assets/61fca626-baa6-40a9-be3e-c2a7a51a43af)



- Static Routee 확인

![image](https://github.com/user-attachments/assets/eba6f859-0084-430f-8f2f-cf918e23eaf6)


#### RIP (Routing Information Protocol)
- RIP 설정법

![image](https://github.com/user-attachments/assets/94ff2ef2-4d34-47e2-bbd3-4d5bfcf6444f)


- RIP 확인

![image](https://github.com/user-attachments/assets/b5dca026-ed6e-42b9-a739-aeb595b23d1c)


#### OSPF (Open Shortest Path First) 
- OSPF 설정법

![image](https://github.com/user-attachments/assets/ff1fddc9-729f-4d13-b525-2d92198d44c2)


- OSPF 확인

![image](https://github.com/user-attachments/assets/3ef9c175-e5ef-4b24-9e78-2f72c8f66841)

![image](https://github.com/user-attachments/assets/952406a9-c02a-4f32-bf5f-37fdd4beafcb)


#### BGP (Border Gateway Protocol) 
- BGP 설정법

![image](https://github.com/user-attachments/assets/9576ca42-d88f-45c3-b8bf-f60d3541f5ba)


- BGP 확인

![image](https://github.com/user-attachments/assets/6e94a595-6987-4990-b8a6-5126581b9133)

- show ip bgp
- show ip bgp detail 

![image](https://github.com/user-attachments/assets/821d9899-ad75-4aef-b104-5976ab4130d6)

- show ip bgp 50.0.0.0/8
- show ip route 50.0.0.0/8

![image](https://github.com/user-attachments/assets/645b6fd6-4b6d-47c0-a119-6063cb902624)

- show ip bgp summary
- show ip bgp peer-group

![image](https://github.com/user-attachments/assets/048a14a2-b930-426d-9704-87a3dc5f1db5)

- show ip bgp neighbors
- show ip bgp neighbors history

---
## ACL(Access-list)
- **이더넷에서 출발지와 목적지 정보를 이용하여 허용 또는 거부하는데 사용되는 목록**
- Layer에 따른 분류 : MAC ACL(L2), IP ACL(L3), Layer 4 ACL, Layer 7 ACL
- 요소에 따른 분류 
1) Standard : Source의 정보를 사용
2) Extended : Source, Destination, TCP, UDP, ICMP, Layer 4 Port 등의 정보를 사용 
- 차단/허용 방식에 따른 분류 
1) White-list : 허용할 트래픽을 제외한 다른 트래픽을 차단
2) Black-list : 차단할 트래픽을 제외한 다른 트래픽을 허용
- 일반적인 Subnet Mask가 아닌 Wildcard Mask를 사용 (255.255.255.0 = 0.0.0.255)
- 리스트의 마지막은 deny any any가 생략 및 적용 되어 있음


- Standard ACL 설정법

![image](https://github.com/user-attachments/assets/ae5064cf-cab7-4a03-907d-c32f1f0e87f7)


- Extended ACL 설정법 

![image](https://github.com/user-attachments/assets/25c3b475-3182-4002-9252-b1df695edd10)


- ACL 적용방법 

![image](https://github.com/user-attachments/assets/8205883c-4046-428a-a2d9-e9e7463712fe)


- ACL 확인방법

![image](https://github.com/user-attachments/assets/bf16d5a8-c478-4314-a8b2-2067d139d6f4)


---
## Port Mirroring (SPAN)
- **네트워크 스위치 상 포트ㅔ 전달되는 네트워크 패킷을 복제하여 다른 포트로 보내주는 개념**
- 복제되는 대상 포트를 Mirroring Port, 복제된 포트를 Mirrored Port라고 한다.
- **Mirrored Port는 통신을 할 수 없다.**
- 복제하는 트래픽 방향에 따라 Rx(Ingress) / Tx(Egress) / Both(In/Out)이 존재         ※ 장비 기준 방향
- 수행 장치에 따른 분류
1) 로컬 인터페이스 간 Mirroring : SPANN(Switched Port Analyzer)
2) 장비 간 Mirrorinng : RSPAN(Remote SPAN)
3) 장비 간 Mirroring + 암호화 : ERSPAN(Encasulated Remote SPAN)

- 대표적인 사용 용도
1) 트래픽을 분석 하는 보안 솔루션(Analizer)
2) DB 모니터링
3) 트래픽 가시성 솔루션(Visibility)
4) 네트워크 디버깅  

![image](https://github.com/user-attachments/assets/701fa23c-d250-4036-9ebb-3023c9ae750b)


#### Monitor Session 
- SPAN 설정은 Monitor Session으로 설정하며, Source Port(원본 포트) / Destination Port(복제된 포트) / Direction(트래픽 방향) / Filter(ACL 이용)를 설정할 수 있다.
- **MLAG 멤버 포트를 미러 대상(Destination)으로 사용해서는 안된다.** 
- 지원하는 모니터 세션 수

![image](https://github.com/user-attachments/assets/3445ee39-a3da-4d0b-91bc-c3267b29e524)


- Monitor Session 설정 방법

![image](https://github.com/user-attachments/assets/0b32be06-63af-4ff7-8245-a0753e6ef89d)


- 설정 내용 확인 

![image](https://github.com/user-attachments/assets/b4a156e6-a084-4705-9eec-ac4b4469effb)


- 설정된 포트 상태

![image](https://github.com/user-attachments/assets/54f5fa82-ee87-4169-851c-6c090939f631)


- 설정 삭제 

![image](https://github.com/user-attachments/assets/df3b056e-51fb-4850-aa59-bef8ff584067)
