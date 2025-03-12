## Oracle DataBase 19C Version Install 

### 오라클 설치 파일 다운로드 
1. Google에서 oralce db 19c download 검색
2. https://www.oracle.com/kr/database/technologies/oracle19c-windows-downloads.html 접속 후 WINDOWS.X64_193000_db_home.zip 다운로드

![image](https://github.com/user-attachments/assets/ffd6ed49-b6d5-474f-b76e-e92e900fc523)


3. 설치단계에서 비밀번호 지정, 컨테이너 데이터베이스 생성 박스 체크 해제

![image](https://github.com/user-attachments/assets/92915852-68a3-4eb8-ba4e-a6fb8e2d02ae)

4. CMD 오라클 접속하기
- 명령 프롬포트에서 다음 명령어로 오라클에 접속
- sqlplus "/ as sysdba" 입력


![image](https://github.com/user-attachments/assets/f22bae08-5729-4590-9788-93ab7acb6370)

위와 같이 접속한 유저는 SYS로, 오라클에서 모든 권한을 소유하고 있는 최고 권한 유저이다.
보통은 SYS 유저에서 작ㅇ버하지 않고 일반 유저를 생성해서 사용한다. 

5. 유저 생성하기

![image](https://github.com/user-attachments/assets/414adbfe-1abf-482f-9432-c5aa6ebe5c36)


- 유저 이름 : user, 비밀번호 0000으로 유저 생성
1. SQL> create user admin
  identified by 0000;

2. admin 유저에 dba Role 부여
   SQL> grant dba to admin;

3. admin 유저로 접속
  SQL> connect user/0000

4. 접속한 유저가 admin인지 확인
  SQL> show user 

---

### SQL Developer
1. Google에 oracle sql developer 22.2 downloads 검색


![image](https://github.com/user-attachments/assets/dd228989-59eb-406c-9d1e-c333c60fdcf8)


 2. 다운로드 후 압축 해제 - sqldeveloper.exe 파일 실행


![image](https://github.com/user-attachments/assets/566c3101-da24-48f4-97c0-c90946531d32)


 3. 메뉴 첫 번째 파일 모양 클릭 - 새 갤러리 오픈


![image](https://github.com/user-attachments/assets/ce45cf5e-0bac-4c34-9e42-1a287ebe61fd)


<br>
<br>

![image](https://github.com/user-attachments/assets/aac60847-97d2-4c52-bfb4-693b55f2299c)

- 범주 영역 접속
- 데이터베이스 접속 확인


![image](https://github.com/user-attachments/assets/4619e5a7-4b14-469d-8bcc-80fcff35f93f)

#### 데이터베이스 접속 선택

사용자 이름 

- Name : orcl
- 사용자 이름 : admin (zeluga x)
- 비밀번호 : 0000

세부 정보 

- 호스트 이름 : localhost
- 포트 : 1521
- SID orcl 


![image](https://github.com/user-attachments/assets/93558cfd-e5ec-4ac3-8137-dc934de9acab)


----

1) 오라클 계정으로 접속

SQL> sqlplus system/1234;  --오라클 설치시 설정해두었던 패스워드



다음에 접속됨:

Oracle Database 12c Enterprise Edition Release 12.1.0.2.0 - 64bit Production

With the Partitioning, OLAP, Advanced Analytics and Real Application Testing options



2) test계정 만들어 보기

SQL> create user test identified by test

SP2-0640: 연결되지 않았습니다.
-- 접속을 시켜 보죠.

SQL> conn sys/oracle as sysdba

연결되었습니다.

--접속이 되었네요. 이건 안해도 될듯...;;;



먼가 잘못 되어서 난 에러 입니다. 

삽질 해보니 오라클 12c부터 공통계정 앞에 c##넣어 라고 하네요 번거롭지만 그렇게 하고 해야 하드라구요....



SQL> create user c##test identified by test

User C##TEST1이(가) 생성되었습니다.

권한 까지 줘야 접속이 되요~

SQL> grant connect, resource, dba to c##test; 

SQL> grant connect, dba, resource to c##test; //모든권한 주기 

이렇게 권한 주면 끝 접속 해보죠!!

SQL> conn c##test/test;

연결되었습니다.
