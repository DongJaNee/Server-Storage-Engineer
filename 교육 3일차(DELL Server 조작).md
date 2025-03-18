## DELL 440R BIOS 연결 조작 및 확인
- System BIOS Settings -> Process Setting (CPU 확인 가능)
CPU : Intel(r) Xeon(R) Gold 6138 2.00GHz 
Coers : 20 
Memory : 0.75TB

- System BIOS Settings -> Memory Setting (Memory 용량, 속도 등 확인 가능)
Memory : 32GB
Speed : 2666Mhz

- System Device Setting (삽입되어있는 Disk 확인 가능)
Disk : 1개

- System Device Setting -> Main Menu -> Configuration Management -> Create Virtual Disk (Raid 설정 및 확인 가능)
Raid : 0

- IDRAC Settings -> User Configuration (IP 설정 및 아이디 비밀번호 설정 가능)
ip : 10.0.0.100
Gateway : 10.0.0.1 

---
### DELL Server 노트북 연결 네트워크 확인 및 Server 문제 인식
- 1. 검색에 네트워크 검색 
  2. 이더넷 속성 설정 
  3. IP주소와 Gateway 설정 맨 뒷자리 번호가 0 ~ 255중 DELL의 IP와 GateWay에 설정했던 끝 번호가 달라야한다. 
ex) DELL Server에 설정했던 IP : 10.0.0.**100** 
                노트북 IP설정 : 10.0.0.**2** (이렇게 끝번호만 다르게 앞번호는 같음 ) ※ GateWay도 동일하게
  4. 설정이 끝나면 CMD로 IP가 정상적으로 작동하는지 확인 (명령어 : ipconfig)
  5. 정상적으로 작동하면 CMD로 Ping확인 (명령어 : ping)      ※계속해서 확인하는 명령어 : -t / 끝내기 : ctrl + c
  6. Web Browser에 DELL에 설정한 IP 주소 검색
  7. DELL에 설정한 ID, PW를 입력하여 로그인 

---
### DELL Server 문제 인식 및 해결 방법
- DELL Server에 문제가 발생시 Server Disk 옆쪽에 불빛 확인. (파란색 - 정상작동 / 주황색 - 문제 O)
- 문제 해결 : Server 내부 장치에 문제가 없을 때 주황색으로 깜빡거릴 때 불빛 옆 아이콘으로 어떤 장치에 문제가 있는지 식별 가능.

