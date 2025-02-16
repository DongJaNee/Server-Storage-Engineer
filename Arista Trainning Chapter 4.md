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
