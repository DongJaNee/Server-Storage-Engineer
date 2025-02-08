**## 메모리**

- 메모리는 **CPU 컴퓨팅 데이터를 임시로 저장**하고 하드 디스크와 같은 외부 저장 장치와 데이터를
  교환하는 데 사용됩니다. 메모리 성능은 **모든 컴퓨터 프로그램 작동이 메모리에서 구현**되기 때문에
  컴퓨터 성능에 큰 영향을 미칩니다.

---

#### DRAM 분류 
1) SDRAM
- 동기식 동적 랜덤 엑세스 메모리 (**메인스트림 메모리 칩**)
2) SGRAM
- 동기식 그래픽 랜덤 엑세스 메모리 (비디오 카드에서 사용)
3) VRAM
- 비디오 RAM, 컴퓨터 이미지 데이터를 저장하기 위한 DRAM(비디오 카드에서 사용)
4) MDRAM
- Multbank DRAM a high-performance VRAM (비디오 카드에서 사용)
5) WRAM
- Window RAM, 고성능 dual-port VRAM (비디오 카드에서 사용)
6) EDRAM
- 향상된 DRAM (일반적으로 통합 비디오 카드에 사용되는 프로세서의 온칩 DRAM)

---
#### DRAM in System
- 초기에는 메모리가 메모리 버스를 통해 노스브리지(메모리 컨트롤러 허브 MCH0에 연겨되었고, 노스브리지는
  프론트엔드 버스를 통해 CPU와 통신했습니다. Intel Nehalem 이후 노스브리지는 CPU에 통합되고
  메모리는 메모리 버스를 통해 CPU에 직접 연결됩니다.

- 메모리 성능 기준 : DDR4 > DDR3 > DDR2 > DDR1 > SDRAM

---
#### DIMM(Dual Inline Memory Module)의 구성 
- DIMM은 메모리 칩, 회로 기판 및 에지 커넥터로 구성됩니다.

 ![DIMM](https://github.com/user-attachments/assets/e250a8f9-fc9b-4252-85eb-baf5e1620b5a)


DDR1 = 대형 칩 + 원형 노치
DDR2 = 작은 칩 + 둥근 노치 
DDR3 = 작은 칩 + 정사각형 노치 
DDR4 = 소형 칩 + 정사각형 노치 

- DDER4 엣지 커넥터는 중간이 약간 돌출되어 있고 두 끝이 더 짧습니다. (이 설계는 주로 DDR4 메모리
  모듈을 설치하는 동안 인쇄회로 기판(PCB)의 삽입을 용이하게 하고 압력을 줄이는 데 사용됩니다.

---
#### DIMM Type(메모리 모듈)
1) UDIMM(버퍼링되지 않은 DIMM)
- 차이점 : 버퍼가 없습니다.
- Application : 저가형 CPU 플랫폼 
2) RDIMM(레지스터드 DIMM or 버퍼링 메모리) 
- 차이점 : RDIMM에는 메모리와 메모리 컨트롤러 사이에 온보드 메모리 레지스터가 있습니다.
- Application : 주 시나리오
3) LRDIMM(Load-reduce DIMM or 부하 감소DIMM)
- 차이점 : 데이터 및 주소 제어 신호는 모두 레지스터를 통과합니다.
- Application : 대용량 시나리오 

※메인스트림 CPU 플랫폼에서 사용자가 4GB, 8GB, 16GB 및 32GB RDIMM 또는 64B 및 128GB LRDIMM을
사용하여 시스템의 전체 메모리 용량을 개선하도록 안내합니다. 

볼륨 기준 
- DIMM, Mini-DIMM, SO-DIMM(소형 DIMM), MicroDIMM, VLP(매우 낮은 프로파일), ULP(매우 낮은 프로파일)

---
#### NVDIMM Introduction
- 공통 메모리 외에도 일종의 비휘발성 DIMM(NVDIMM)이 있ㅅ브니다. NVDIMM은 JEDEC 솔리드 스트레이트 기술 협회
  (JEDEC Solid State Technology Association)에서 정의합니다.
- DDR4 표준을 준수합니다.
- 표준 DIMM 슬롯과 호환됩니다.
- 이 모듈에는 DRAM과 NAND 스토리지가 포함되어 있습니다. 시스템이 실행 중일 때
  NVDIMM은 DRAM과 같은 계산을 수행합니다.
- 시스템의 전원 공급이 중단되면(갑작스러운 정전 또는 정상적인 전원 끄기로 인해 가능)
  NVDIMM은 슈퍼 커패시터에 의해 전원이 공급되고 DRAM 데이터를 NAND 스토리지에 다시 씁니다.
  전원 공급 장치가 복원되면 데이터가 DRAM으로 다시 이동됩니다.  

![NVDIMM](https://github.com/user-attachments/assets/b675fa0c-504c-4249-8bdc-0e04e84f1556)
![NVDIMM Type](https://github.com/user-attachments/assets/0fafc5e1-8908-40a6-9252-f4d22b20f417)
