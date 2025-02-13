![image](https://github.com/user-attachments/assets/40a53a5f-6fe5-4250-993f-47849ffe1f0d)### Booting 
1. 로그인 : 초기 상태의 계정은 admin이며 PW는 없다. 
2. EXEC -> Privileged EXEC 모드 이동 : enable password가 설정되어 있다면 PW입력이 필요 ( ※디폴트는 없음) 
3. OS Upgrade 
1) 신품 장비라 하더라도 최신 OS가 설치되어 있는 것이 아니기에 설치 초기에 OS 버전을 확인하고 OS 변경하는 것을 권장.
--- 

![OS version 확인](https://github.com/user-attachments/assets/813d446b-aa31-4053-8b3c-7b9d065edcc9)

2)  OS version 확인
---

 ![설정 백업](https://github.com/user-attachments/assets/3b4f2c20-53fd-4a4e-b556-c88f4a5d6365)

3) 설정 백업(필요시)
---

![디스크 용량 확인](https://github.com/user-attachments/assets/5bdcff2f-e375-4172-ad5f-1d3f05e9892c)

4) 디스크 용량 확인
  용량 부족 시 불필요 파일 정리 
---

![EOS 파일 복사](https://github.com/user-attachments/assets/4a0428a5-a100-42ab-a322-1ab3eb473244)

5) EOS 파일 복사 
  FTP, SCP, TFTP, HTTP 등의 프로토콜은 네트워크 설정 및 연결이 필요하기 때문에 USB Flash를 이용하는 것이 용이하다. 
Arista가 지원하는 File System은 FAT 계열 및 VFAT을 지원하며, NTFS는 지원하지 않는다(USB Format시 주의) 

--- 

![EOS File Hash 비교 체크](https://github.com/user-attachments/assets/1bcee578-4886-495c-b860-989013388312)

6) EOS File Hash 비교 체크  

---

![Boot 설정 변경](https://github.com/user-attachments/assets/dcd190e5-0e99-4027-9e7a-998f62cf82b8)


7) Boot 설정 변경 

---

![설정 저장 및 재부팅](https://github.com/user-attachments/assets/dc9862b6-f752-4d58-84de-7ebd0bc97ff9)

8) 설정 저장 및 재부팅 
   다음장의 ZTP disable 과정에서 재부팅이 강제 자동 진행되므로 초기 설치 시에는 다음 단계(Zero Touch Disalbe)에서 재부팅하는 것이 유리하다. 

---

4. 로그인 및 ZTP (Zero-touch provisioning) 모드 해제
- ZTP (Zero-touch Provisioning)모드 해제 (※ 디폴트로 활성화 되어 있음)
- 초기 부팅시 ZTP모드로 부팅되어 zero-touch cancle 또는 disable 명령어를 입력하여 모드를 해제 
- 재부팅이 동반됨 
- ZTP : 신규 디바이스에 대한 설정 및 구성을 자동화하는 구성(동일 네트워크 내에 기반 솔루션이 존재하여야 함)

![ZTP 모드 해제](https://github.com/user-attachments/assets/1836f7b3-807d-4ad1-bcdf-7c266a9e95ca)

--- 
5. 상태확인 CLI
- 상태 확인 명령어 
1) show environment[ all / cooling / power / temperature ] 
  Fan 동작 상태, Power 공급 상태 확인 

![상태 확인 명령어](https://github.com/user-attachments/assets/5ee18343-e0f8-4eec-aa7e-8a5b54412831)

2) show inventory
- 납품된 모듈(파워/팬/라인카드 등), SFP 인식 상태 확인 

![image](https://github.com/user-attachments/assets/e331a66d-c829-42fb-9dda-853f090bdceb)


![image](https://github.com/user-attachments/assets/a626e182-370f-45e6-bd5c-fcf732335bbb)

3) show interface status 
- SFP 인식 상태 확인 

![SFP 인식 상태 확인](https://github.com/user-attachments/assets/6a675646-ce65-4c1f-9079-2b1a87fc0b24)
