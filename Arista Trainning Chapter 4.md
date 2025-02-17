### Aboot
#### **Aboot 개요**
- 스위치에서 BIOS 및 부트로더(Bootloader)기능을 수행하는 Startup 소프트웨어
- Aboot 프로세스에서 Boot-config를 통해 EOS 소프트웨어를 로드하여 구동시키며, 실패 시 Aboot Shell 모드로 자동 진입하게 된다
- Aboot Shell을 사용하는 경우
1) 공장 초기화
2) Password 분실로 인한 Recovery
3) 콘솔 엑세스 관련 설정을 복원할 경우 (Baud Rate, Parity, Stopbits 등)
4) 플래시의 내용을 USB Flash에 저장된 설정 및 이미지 파일로 교체할 경우

- **부팅 중 'Ctrl + C' 신호를 전송 시 Aboot Shell 모드로 진입 가능**
 
![image](https://github.com/user-attachments/assets/f9af961a-ebb4-441f-bbac-563b2b1a32a9)

- Boot-config에 Aboot Shell 모드로 진입하는 Password를 설정할 수 있다.

![image](https://github.com/user-attachments/assets/7259e41c-1892-425e-b5da-15b6b718b83b)

**※ Aboot Password를 분실하여도 3회 실패하면 초기화를 할 수 있는 방법으로 진행된다**

---
#### ** Aboot Shell 명령어**

![image](https://github.com/user-attachments/assets/772a8031-26a0-4d70-a348-1e083960a7e8)

**※ Aboot Shell 모드에서 USB와 Flash의 경로
      USB1 : /mnt/usb1
      Flash : /mnt/flash**  

---
### Startup-config 수정 
#### **Aboot Shell에서 Startup-config 수정**
- Startup-config는 Flash에 존재하며, **Flash의 주소는 '/mnt/flash'이다.**
- vi 편집기를 이용해 설정파일 수정이 가능하다. 
**※ 'rm/mnt/flash/start-config'를 사용하여 설정 파일을 삭제하면 초기화된다.**
  
![image](https://github.com/user-attachments/assets/7914b568-c05b-40bd-8619-e6ea5502ac06)

---
### Password Recovery 
#### **Password Recovery**
- Password 분실시 Aboot Shell에서 vi 편집기를 이용해 Startup-config에서 해당 설정 내용들을 삭제 후 저장하고 Aboot Shell
모드 종료 또는 부팅 하면된다.
**※ 편집모드 진입 : 'a', 편집모드 해제 : 'ESC', vi편집기 종료 : 'q', 변경요소 무시 후 종료 : ':q!',
현재 상태 저장 : 'w', 현재상태 저장 후 종료 : ;:wq'**
- 부팅 완료 후 계정과 패스워드를 다시 설정

![image](https://github.com/user-attachments/assets/824d5a87-9420-4b82-8a77-4f33aead93e8)

---
### USB Flash를 이용한 Recovery 
#### **USB Flash를 이용한 복원 (초기화)**
- Flash에 저장된 OS 파일에 문제가 생겼거나, 다른 이유로 EOS로 부팅이 되지 않을 때 USB를 이용해 복구를 진행할 수 있다.
1) USB Flash Disk 준비 : 파일 시스템은 FAT 계열로 포맷 되어야 인식이 가능
2) USB Flash Disk 내 아래와 같은 파일 복사 및 생성
- EOS file : .swi 확장자를 사용하는 EOS파일을 USB Flash에 저장
- fullrecover : 텍스트 파일로 fullrecover를 USB Flash에 생성, 내용은 빈 파일, 확장자 없음
- boot-config : 텍스트 파일로 boot-config를 생성, 확장자 없음, 내용은 아래와 같이 EOS 파일에 대한 링크에 대한 정의가 존재 하여야 함

![image](https://github.com/user-attachments/assets/f02fb4ca-02db-4525-bef1-82a283c9d909)

3. 스위치의 USB 포트에 USB Flash 삽입
4. 콘솔 연결 후 터미널 모니터링
5. 전원을 켜거나 리로드 
- 부팅 중 내부 Flash를 삭제하고 USB에서 파일을 복사, 완료 후 자동 재부팅
6. 부팅 완료 후 ZIP 해제 
