## Useful CMD & TROUBLESHOOT

---

### 유용한 명령어 - 시스템 정보 확인 
- 모델, 시리얼 번호, S/W Version, 구동시간, 메모리용량 - **'Show Version'**

![image](https://github.com/user-attachments/assets/99080e43-2b59-4218-afbd-a6da23e95c74)

---
### Inventory 확인 
#### **Show Inventory**
- 장비와 장비에 연결된 모듈들에 대한 하드웨어 정보

![image](https://github.com/user-attachments/assets/884b49b1-65ec-4bb9-b4a8-19839b25f051)

---
### 환경 센서 및 관련 모듈 확인 
#### **Show Environment all**
- 장비의 센서별 온도 및 FAN, Power 상태 확인

![image](https://github.com/user-attachments/assets/f60a7e05-e383-449e-8520-a04122db143a)

---
### CPU 정보 확인  
#### **'cat / proc / cpuinfo'**
- 일반 CLI 모드에서 'bash'를 앞에 붙이면 모드 변경없이 사용 가능 

![image](https://github.com/user-attachments/assets/d049627f-5304-4186-9fac-04132fe9ae4c)

---
### CPU 및 메모리, 프로세스 확인 
#### **Show Process Top** 
-**TOP / TASKS / CPU#**
![image](https://github.com/user-attachments/assets/4f327712-cb38-4ae8-b4fe-eae72540cf2a)

- **MMEM / SWAP / Processes**

![image](https://github.com/user-attachments/assets/3bdecf73-d2b5-4eb9-9c76-5b66cc21bbff)

---
### 로그 확인 방법 
#### **Show Logging (EOS / 네트워크 로그)**
**last**
뒤에 붙는 시간 옵션에 따라 그 이전부터 현재까지 발생된 로그를 열람할 수 있다. 
ex) show logging last 5 min : 5분전부터 현재까지의 로그

![image](https://github.com/user-attachments/assets/da3c9a5a-4aaa-4fda-ab2e-22e1a28f8ac9)


#### **Show Logging System (시스템 로그) 
- Arista EOS의 Base OS인 Linux Kernel의 로그이다.
- Linux Kernel의 동작 기록 및 Daemon의 동작 정보를 볼 수 있다.

![image](https://github.com/user-attachments/assets/1aaf606a-6c34-440e-a57b-26fe94c3853f)


#### **Show Agent Logs (에이전트 로그) 
- /mnt/flash/agent.log : Arista TAC에 기술지원을 받을 때 Agent 로그를 요청받을 경우 이 옵션으로 Flash에 파일로 저장 가능 

![image](https://github.com/user-attachments/assets/5776b21d-0686-4b4f-87dc-06bf9f3b5c30)

---
### TCPDUMP 
#### **Tcpdump (CLI)** 
- Arista EOS 4.10 이전버전에선 Bash Shell 모드에서만 사용 가능
- 스위치 CPU로 향하는 Control Plane 트래픽을 캡처하여 헤더 정보를 출력
- Bash Shell 모드에서의 옵션과 CLII에서의 옵션은 약간 형태가 다르다 

![image](https://github.com/user-attachments/assets/03e4faae-1438-408b-a147-decb23f9374e)


#### **Tcpdump (Bash)

![image](https://github.com/user-attachments/assets/204162d8-dc21-4608-ae59-28d5138918a9)

---
### 파일 복사 
#### **Copy** 
- USB Flash를 사용하는 경우 Arista장비에서 인식하는 포멧은 FAT계열 및 VFAT이므로 해당 방식으로 포멧하여야 한다.
**※NTFS는 지원하지 않음**

![image](https://github.com/user-attachments/assets/c463e59f-5d8b-4056-8228-6b887400a788)

---
### 성능 측정 도구 
#### **iPerf**
- 성능측정 도구인 iPerf가 EOS에 내장되어 있음
- Server / Client 모드 지원
- Bash Shell 모드에서 작동

- **Server 모드 실행** 

![image](https://github.com/user-attachments/assets/741d06f1-deae-449c-968e-b78cef7d0c57)


- **Client 모드 실행** 

![image](https://github.com/user-attachments/assets/8ba037e8-47e2-40fd-80e0-f9282cdc3e3e)


![image](https://github.com/user-attachments/assets/46adf88d-2731-4ac7-89e2-ce4ff7f788f4)

---
### 트래픽 생성 도구 
#### **ETHXMIT**
- 사용자가 설정가능한 헤더 필드를 기반으로 패킷을 생성하는 도구
- L2 Broadcast, L3 Unicast, L3 Multicast패킷을 생성 가능 

- **L2 Broadcast Frame with VLAN tag**

![image](https://github.com/user-attachments/assets/5da2c97c-14f2-4da9-a17a-7e28eee09266)


- **L3 Unicast Packet**

![image](https://github.com/user-attachments/assets/98bbadaf-a9e9-4a45-abe0-94ad682afb24)


- **L3 Multicast Packet**

![image](https://github.com/user-attachments/assets/d2ff947c-bb90-47d9-b90b-1f95aab46abf)


![image](https://github.com/user-attachments/assets/79f17138-653d-49d6-941f-a9a259199148)

---
### SNMP MIB/OID 확인 
#### **SNMP MIB**
- SNMP walk가 EOS안에 내장되어 있어 CLI에서도 MIB 및 OID 값을 확인할 수 있다. 
---
- **사용 가능한 MIB 이름 출력**

![image](https://github.com/user-attachments/assets/0605dbe8-4b51-490b-acf6-4f394d55d1f1)


---
- **SNMP walk로 실제 SNMP의 하위 값들을 출력**

![image](https://github.com/user-attachments/assets/978246c4-c059-4fab-9314-b49c15e893c6)

---
- **SNMP get으로 SNMP의 결과 값을 출력**

![image](https://github.com/user-attachments/assets/ae0c6ac0-0a2c-452b-834d-319d6b7558be)

---
-  **인터페이스 ifindex 출력**

![image](https://github.com/user-attachments/assets/a4aaedbd-d66a-4617-8bd6-00f8c325108e)

---
- **MIB로 OID값 확인**

![image](https://github.com/user-attachments/assets/b237e932-b378-4ef1-a927-10489f642471)

---
- **OID로 MIB 확인** 

![image](https://github.com/user-attachments/assets/a1a532d5-b506-42c5-b7d5-4878b9790c28)

---
### SNMP OID 값 
#### **Arista SNMP OID**

![image](https://github.com/user-attachments/assets/8bdb0fb9-e946-4f57-8a86-1b3e257e8dec)

---
### Show Runninng-config 옵션 
#### **Show Running-config All
- 설정 가능한 모든 내용들을 출력
- 설정이 안된 초기 장비 일시 공장 기본 설정값 

![image](https://github.com/user-attachments/assets/302a1f2b-6605-43e3-a679-6776b8196042)

---
#### **Show Running-config Interface**
- 인터페이스(Ethernet / Fabric / Loopback / Management / Port-Channnel / Tunnel / VLAN / VXLAN)에 설정된 내용을 출력

![image](https://github.com/user-attachments/assets/89344d74-1414-4470-b35b-4143764fa9bd)

---
#### **Show Running-config Section**
- 특정 문구가 포함된 구역의 설정 내용을 출력

![image](https://github.com/user-attachments/assets/51e292f4-fc3b-44f9-b640-4acf79b19e27)

---
#### **Show Running-config diffs**
- Startup-config와 Running-config를 비교하여 차이가 나는 부분을 추려서 출력(설정이 변경된 부분 확인)
- 설정을 저장하기 전에 사용하여야 한다.

![image](https://github.com/user-attachments/assets/c27c6535-274d-4d7c-b618-bf186481aa13)

---
### 인터페이스 정보
#### **Show Interface**
- 인터페이스의 동작 상태, 인바운드 / 아웃바운드 패킷 정보, 에러 등을 볼 수 있다.

![image](https://github.com/user-attachments/assets/7484c53f-4c36-44a9-aa40-e0450b7d1e61)

---
#### **Show Innterface Transceiver & Phy Detail
- 인터페이스에 장착되어 있는 광 트랜시버의 정보를 볼 수 있다.
- show interface <Interface Name> transceiver를 사용하면 특정 인터페이스 정보만 볼 수 있다.
- 온도(Temp), 전력(Voltage), 레이저 다이오드에 공급되는 정전류(Blas Current), 송신 광 신호 세기(Tx Power),
수신 광신호 세기(Rx Power)를 확인 

※이상적인 광 신호 세기 : Tx -> (-2 ~ -9dBm),  Rx -> (-2 ~ -18dBm)
- Phy는 MAC계층과 트랜시버 간의 변환을 진행하는 인터페이스로 물리계층의 구성요소이다. 
 
![image](https://github.com/user-attachments/assets/69008b04-186c-4488-9da8-1f6393240c4b)

---
#### **Show Innnterface Transceiver Detail**

![image](https://github.com/user-attachments/assets/eae27f58-3105-4746-b2f9-0eac923a0fe7)

---
#### **Show Interface Status & Errdisabled**
- 인터페이스의 전반적인 상태를 확인하기 유용한 명령어
- Name(Discription), 상태(connect / notconnect / errdisabled / mirrior), VLAN(VLAN번호, Trunk, Routed), 
Duplecx(full, half), 연결 속도, 미디어 타입을 확인 가능하다.
- Errdisabled : 인터페이스가 상대방과 통신에 문제가 있을 때 비활성화 상태로 전환 방어 동작
**※ 배부분 링크플랩과 상대방과의 컨피그미스매치로 인한 발생이 다수이며, 
  해제하는 방법은 인터페이스를 shutdownn/no shutdown 하면된다.**
  
![image](https://github.com/user-attachments/assets/b8d5a726-4c72-4438-b6bb-571b52711fe5)

---
#### **Errdisable Recovery**
- errdiisable에 대해 원인을 찾고 이를 제거하는 것이 제일 좋겠지만, 원인 해결이 곤란한 경우, 자동으로 복구 되는 기능 사용을 고려해볼 수 있다.
- errdisable이 걸리게 되는 조건을 완화하거나 끄는 설정도 가능하다. 

![image](https://github.com/user-attachments/assets/3cf00818-f81f-4a43-a011-1b67b673aab0)

---
#### **Show IP Interface Brief**
- Layer 3 인터페이스의 상태 정보를 요약해서 볼 수 있다.
- IP 주소, 상태(Status), 프로토콜 통신 상태(Protocol), MTU 크기 등의 정보가 표시 된다.
**※ Status는 물리적인 연결 상태이며, Protocol은 상대ㅐ방과 논리적인 통신이 가능한 상태인가를 보여주는 차이가 있다. 
    Status는 'up'인데, Protocol이 'down'인 경우는 신호교환은 가능하지만 정상적인 통신이 안되는 상태로,
    대부분 설정 미스매치로 발생한다.**

![image](https://github.com/user-attachments/assets/31b884bd-567b-4e22-b12d-096939b4fdaf)

---
### 인터페이스 패킷량 
#### **Show Interface Counters**
- 인터페이스별 인/아웃바운드 패킷의 량
- show interface <Interface Name> counnters를 사용하면 특정 인터페이스 정보만 볼 수 있다.
- 범위 설정도 가능하며, show interface e1-4 counters 같은 방식으로 사용 가능하다.

![image](https://github.com/user-attachments/assets/39514e95-e1d9-45e8-94f0-27dee25e0d48)

---
### 인터페이스 에러 패킷량
#### **Show Interface Counters Errors**
- 인터페이스별 인/아웃바운드 패킷의 량
- show interface <Innterface NName> counters를 사용하면 특정 인터페이스 정보만 볼 수 있다.

![image](https://github.com/user-attachments/assets/6f8114a7-405e-4990-98f7-eed03a87b3f3)

---
### 실시간 변화 확인
#### **Watch command**
- 특정 명령어의 변화를 실시간으로 모니터링 할 수 있다.
- 갱신 주기는 기본값 2초이며 매개변수로 바꿀 수 있다.
  
![image](https://github.com/user-attachments/assets/76a14ae0-eebf-4433-a0ca-ff20e296b77e)

---
### 라우팅 정보
#### **Show IP Route**
- 고정 경로, 직접 연결 경로, 학습된 동적 경로, FIB(Forwarding Information Base)의 경로의 정보를 표시한다.
- 매개변수로 IP 주소를 사용하면 해당 IP 주소로의 경로를 볼 수 있다.

![image](https://github.com/user-attachments/assets/937789e3-1edb-4555-a6dd-319eff3dd141)

---
### Ping and Traceroute
#### **Ping**
- 상대방과의 통신을 체크하기 위하여 많이 사용되는 툴로 패킷 데이터 사이즈 / 빈도 수 / 빈도 간격 / 아웃 인터페이스
  / 소스 인터페이스 등의 매개변수를 사용가능하다.

![image](https://github.com/user-attachments/assets/2b6e1dc6-5927-48a2-bc24-1a1b63c5a6ce)

---
#### **Traceroute**
- 상대방과 통신되는 경로상의 홉들을 체크하는 툴로 다중경로가 있을 시 어느 경로를 통해서 통신되는지 확인하는데 사용된다.
- 최대 30홉까지 체크하며, ICMP를 사용하기에 ICMP를 허용하지 않는 장치가 있을 시 '* * *'로 표시된다.
- 상대 홉으로 들어가는 인터페이스만 확인 할 수 있으며, 다음의 홉으로 나가는 인터페이스는 체크하지 않는다.

![image](https://github.com/user-attachments/assets/33fb878c-a68f-40c9-a3e8-72df84aeff90)

---
### ARP Table 확인 
#### **Show IP Arp**
- ARP 테이블에 등록된 내용을 확인 할 수 있다.
- IP, 테이블에 등록된 시간(age), MAC(Hardware Addr), ARP 수신 인터페이스(interface)가 포함된다.
- 상대방과 통신 가능 여부 확인이나 IP를 가지고 MAC주소를 확인할 때 사용된다.
**※ 인터페이스 SVI가 표시되므로 물리 포트 확인은 MAC Address-table에서 확인**
**※ 상대방과 ARP 교환이 발생해야 테이블에 등록되므로, 휴면 상태인 경우 ARP 교환이 없었을 수 있다. 
  이 경우 Ping을 보내면 ARP 테이블에 등록 된다.**

![image](https://github.com/user-attachments/assets/5db08b46-100e-42aa-a8ea-70729bc1d92d)

---
### MAC address Table 확인
#### **Show MAC Address-Table**
- MAC 테이블에 등록된 정보를 볼 수 있다.
- 학습된 MAC주소와 타입, 학습된 인터페이스 정보를 볼 수 있다. Moves는 학습된 인터페이스가 변화가 있을 때 변화된 횟수이다. 

![image](https://github.com/user-attachments/assets/020435be-7e20-4db3-b76d-567a1889e253)

---
### Supervisor Redundancy
#### **Show Redunndancy Status**
- 샤시형 장비에서 Supervisor를 이중화 할 경우, supervisor1과 2 간에 연동 상태를 확인 할 수 있다.

![image](https://github.com/user-attachments/assets/d6ee1c38-6adf-474f-b82e-13bdaf5e4e5a)

---
### Tech Support 
#### **Tech-Support**
- Tech-support는 장비 상태를 나타내는 지표들을 연속으로 출력하는 명령이며, 장애 발생 시 원인 분석에 사용할 수 있으며,
Arista TAC 기술지원시에 필수이다.
- 'show tech-support'로 출력되며, 하위매개변수로 모든 show와 관련된 명령어들을 출력하는 'all'과 주로 많이 사용되는 내용으로 추린 'summary'등등이 있다.
ex) terminal length 0, | no-more
 **※ 상당히 많은 시간이 소요되므로 '>' 를 사용해 파일로 저장 후 옮기는 것이 수월하다.**

![image](https://github.com/user-attachments/assets/cac68cd6-b401-497b-a8e6-7294c92b5df0)

---
#### **Tech-Support Schedule**
- Arista 스위치는 기본적으로 Tech-support를 저장하는 스케쥴러가 동작하고 있으며 60분 마다 실행된다.
- 스케쥴 빈도는 변경이 가능하다.

![image](https://github.com/user-attachments/assets/6e8f7644-2100-49c8-9441-d28a9242fe52)

