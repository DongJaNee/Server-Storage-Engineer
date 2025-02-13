## CLI 모드의 종류 및 모드 변경 방법
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

  #### CLI 모드의 계층 구조 및 이동 방법 

