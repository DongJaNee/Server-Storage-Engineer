## 1. NAS 와 SAN의 정의 및 비교
- 서버와 스토리지를 어떤 방식으로 연결 하느냐에 따라 NAS와 SAN으로 나뉘어진다.

###**NAS (Network Attached Storage)란?**
- 네트워크로 통신하여 저장장치에 연결한다.
- NAS는 TCP / IP와 같은 표준 네트워크로 Network Switch와 연결하여 사용한다.

※(TCP / IP : 서로 다른 시스템을 가진 컴퓨터들을 서로 연결하고, 데이터를 전송하는 데 사용하는 통신 프로토콜) 

![image](https://github.com/user-attachments/assets/dcaa2437-07d0-4718-9504-f335fcf98e39)

---
###**SAN (Storage Area Networking)**
- 스토리지 전용 네트워킹
- 대규모 네트워크 사용자를 위해 저장장치를 데이터 서버와 연결하여 별도의 네트워크로 관리하는 고속 네트워크 시스템이다.
- 이해하기 쉽게 SAN을 Network와 비교하자면, 우리가 일반적으로 사용하는 **LAN선 대신에 광케이블 (FC Cable)을 사용한다.**
- 광케이블(FC Cable)을 위한 각 서버용 모듈 (FC HBA Card)과 네트워크 스위치 (FC Switch \ SAN Switch)를 사용한다.
- 일반적으로 광을 이용한 네트워크를 SAN의 표준으로 보고있다.

![image](https://github.com/user-attachments/assets/e90352ba-674e-471c-9801-6a58bd60ac64)

---
## 2. NAS와 SAN의 장/단점
### NAS (Network Attached Storage)
**장점** : 파일 공유
- 여러 매체에서 네트워크를 통해 접속하여 파일을 공유 하고 저장된 파일의 정보들을 여러 서버에 공유할 수 있다.
- 장소에 구애 받지 않고 내부, 외부에서도 쉽게 접근할 수 있다.

**단점** : 성능 저하 
- 네트워크 환경이 불안정 하면 트래픽 문제가 발생할 수 있고, Latency 증가로 인한 대규모 처리에서 성능 문제가 발생할 수 있다.
(Latency : 네트워크에서 하나의 데이터 패킷이 한 지점에서 다른 지점으로 보내지는 데 소요도디는 시간)

---
### SAN (Storage Area Networking)
**장점** : 빠른 속도와 안정적인 시스템 
- 대용량의 데이터를 연결된 서버에 상관없이 원거리에 분산 된 저장장치 사이에서 데이터를 주고받을 수 있다.
- 빠른 속도와 확장성 및 유연성, 편리성이 뛰어나다는 큰 장점이 있다.

**단점** : 비싼 비용과 복잡한 구성
- SAN은 초기 구축 시 많은 비용을 투자 해야 한다.

---
## 3. NAS와 SAN의 용도
### NAS (Network Attached Storage)
- 파일공유, 동시 접속이 필요한 업무 (웹하드 등), 비정형 데이터 사용에 적합 (동영상 파일, 오디오 파일, 사진, 문서, 메일 본문 등), 다수 클라이언트의 데이터 공유를 위하여 사용 

### SAN (Storage Area Networking)
- 볼륨을 공유하는 목적으로 블록 형태의 I/O가 필요한 업무, DB같은 구조화된 워크로드, 고용량 및 고성능이 요구되는 업무에 사용
   

![image](https://github.com/user-attachments/assets/542f0b19-9e05-455d-887a-b2344b17252d)
