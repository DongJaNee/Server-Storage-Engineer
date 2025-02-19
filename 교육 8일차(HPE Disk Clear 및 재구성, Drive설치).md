### HPE 디스크 Clear 및 재구성
- BIOS 화면에서 System Configuration을 접속 -> 맨 밑 Storage 클릭 -> Main Menu 접속하면 Disk Clear 및 Raid구성, 상태확인 등을 할 수 있다.
※ SATA Disk와 SAS 디스크는 호환이 되지않지만, Server에 SATA와 SAS Disk 둘 다 삽입하면, 각각 따로 Raid 설정을 할 수 있고, 필요에 따른 Disk 사용이 가능하다.

### HPE OS설치
- IODD를 Server에 연결한 뒤 Windows2022에 접속하여 설치한다.

### Drive 설치 
- Disk설정과 OS를 설치하였으면, Window 내PC Drive접속하여 Launch Sum을 클릭하면 cmd가 Update를 한다.
- Update가 끝나면 자동적으로 Localhost Guided Update가 자동적으로 켜지는데 HPE에서 호환을 선호하는 것을 업데이트하려면 Auto로 설정을하여 업데이트를 진행해야한다.
- Update가 끝나면 장치관리자에 접속 -> 장치들에 '!'가 사라진 것을 확인하면 끝이다. 
