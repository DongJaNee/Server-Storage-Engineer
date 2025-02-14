## PowerEdge R440 Server 서버 관리 및 설치 가이드
---

#### 1. 원격 전원 관리
- Graceful Shutdown 클릭 -> Power Off: 원격으로 서버 장비의 전원을 켜고 끌 수 있다.

#### 2. BIOS 버전 확인 및 업데이트
- Dell 웹사이트 -> 지원 홈 -> 제품 식별 검색창에 서비스 태그 입력 -> 제품 정보를 확인할 수 있습니다.
- 제품 정보에서 최신 펌웨어 제공: 설치 방법, 종류, 중요 정보, 개선 사항 등 제공

#### 3. 시스템 개요 (System - Overview)
- 시스템 정보: 장비 구분 및 식별을 위해 정보 확인 가능

- 전원 상태 (Power State), 모델 (Model), 호스트 이름 (Host Name), 운영 체제 (Operating System), 운영 체제 버전 (Operating System Version), 서비스 태그 (Service Tag)

- 스토리지 (Storage) -> 컨트롤러 (Controllers) -> 이름: RAID 컨트롤러 확인

- 대시보드 (Dashboard): 장비 상태 간략히 확인

- 배터리 상태 (System - Batteries): 배터리 상태 확인 (거의 반영구적)

- 냉각 상태 (Cooling): 장비 온도 확인

- 팬 상태 (Fan Status): 팬이 정상 작동하는지 확인

- 온도 (Temperature): 상태 이상 시 메시지 및 알람 표시

- CPU 정보 (CPU): 지원하는 CPU 정보 확인 가능

- 전압 상태 (Voltages): 파트별로 전압이 잘 들어가는지 확인 가능

#### 4. 시스템 상세 정보 (System - Details) : 더 정확한 사항을 확인할 수 있습니다.

#### 5. 시스템 인벤토리 (System - Inventory) : 문제가 발생할 때 확인할 수 있습니다.

#### 6. 스토리지 요약 (Storage - Summary) : 인식된 디스크를 확인할 수 있습니다.

#### 7. 스토리지 컨트롤러 (Storage - Controllers) : RAID 설정 가능

#### 8. 대시보드 - 가상 콘솔 (Dashboard - Virtual Console) : 서버와 연결된 모니터가 없을 경우 노트북으로 연결 가능

#### 9. USB 보호마개 설치 여부 중요 고객한테 꼭 물어봐야한다. 

#### 10. 라이선스 (Licenses) : 업데이트 갱신

#### 11. 시스템 설정 (System Setting) : 설정 조절 가능

#### 12. BIOS 설정 (BIOS Setting)

#### 13. 서버 구성 프로파일 (Server Configuration Profile) : 설정 저장, 보내기 가능

#### 14. 서버의 설치 파일 장치 : CD와 USB 사용 가능, 파일 활용 가능

#### 15. 최근 로그 (Recent Log) : 시스템 이벤트 로그: 장비 상태에 대한 로그 기록 확인 가능

#### 16. 시스템 업데이트 (System Update) : 펌웨어 업데이트 가능

#### 17. 진단 (Diagnostics) : 제품에 대한 자체 테스트

#### 18. 장치 관리자 OS 설치
- Windows 설치 -> IODD 쉽게 설치 가능
- Dell OS 설치: LifeCycle Controller 사용
- IDRAC과 LifeCycle Controller의 차이점 : 하드웨어 진단: 장비 점검
왼쪽 그림을 누르면 장비 테스트 및 상태 결과 확인 가능

#### 19. Disk 구성

- Boot Manager (F12) -> Launch Setup -> Device Settings -> RAID Controller 1 -> Main Menu -> Physical Disk (디스크 인식 확인)

- Configuration Utility -> Create Virtual Disk (RAID 설정)

※ SSD와 HDD는 RAID를 함께 설정할 수 없음

※ SAS와 SATA도 마찬가지

#### 20. LifeCycle Controller : F10

#### 21. OS 설치 전 Disk 구성하기
- OS Deployment -> Deploy OS -> Next (RAID 구성) -> RAID 클릭 후 Next 클릭 -> Select 체크 후 Next 클릭 ->
디스크 이름 설정 후 Next -> Finish

- 운영 체제 선택 (Select an Operating System)
LCD 모니터 Windows 버전과 일치하도록 설정 -> LCD 모니터에 로딩 표시(...)가 뜨면 Enter 누르기
(HPE OS 설치 방법과 동일) -> 비밀번호 설정 -> CTRL + ALT + DELETE (로그인) -> 장치 관리자
