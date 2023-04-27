<br>

# Chapter 3. 운영체제

## 0. 운영체제
: 사용자가 컴퓨터를 쉽게 다루게 하는 인터페이스, 한정된 메모리나 시스템 자원을 효율적으로 분배
- 펌웨어 : 운영체제와 유사하지만 소프트웨어 추가 설치 불가능
<br>

## 1. 운영체제와 컴퓨터
### 1.1 운영체제의 역할과 구조
#### 운영체제의 역할
1. CPU 스케줄링 + 프로세스 관리
2. 메모리 관리
3. 디스크 파일 관리
4. I/O 디바이스 관리 

#### 운영체제의 구조
<table>
<tr><td>유저 프로그램</td></tr>
  <tr>
    <td rowspan="4">운영체제</td>
    <td>GUI</td>
  </tr>
  <tr>
    <td>시스템콜</td>
  </tr>
  <tr>
    <td>커널</td>
  </tr>
  <tr>
    <td>드라이버</td>
  </tr>
<tr><td>하드웨어</td></tr>
</table>

- 드라이버 : 하드웨어 제어를 위한 소프트웨어
- 커널 : 모든 컴퓨터 자원에 접근할 수 있는 모드
- 시스템콜 : 운영체제가 커널에 접근하기 위한 인터페이스, I/O 요청으로 trap 발동하면 커널 모드로 변환해줌
    - modebit : user mode와 kernel mode 나타냄

### 1.2 컴퓨터의 요소
: CPU, DMA controller, memory, timer, device controller, ...

#### CPU (Central Processing Unit)
: ALU(Arithmetic Logic Unit) + CU(Control Unit) + Registers, interrupt에 의해 명령어 실행
- ALU : 산술연산과 논리연산 수행하는 디지털 회로
- CU : 프로세스 조작 지시, IO device의 communication 제어, 명령어 해석, 데이터 처리 순서 결정
- Registers : 빠른 임시기억장치
- interrupt : signal에 의해 CPU가 잠깐 정지, interrupt vector에서 interrupt handler 실행
    - hardware interrupt : IO devices에서 발생
    - software interrupt : trap, 프로세스 오류 등으로 프로세스가 시스템콜을 호출

#### DMA (Direct Memory Aceess) controller
: IO device가 메모리에 직접 접근할 수 있도록 하는 하드웨어 장치

#### 메모리 (Memory)
: 전자회로에서 데이터나 상태, 명령어 등을 기록하는 장치, 보통은 RAM

#### Device controller
: IO device의 작은 CPU

## 2. 메모리
### 2.1 메모리 계층
||
|:---:|
|레지스터|
|캐시 (L1, L2, L3)|
|메모리 (RAM) / 주기억장치|
|저장장치 (HDD, SSD) / 보조기억장치|

#### Cache
: 데이터를 미리 복사한 임시 저장소 -> bottleneck 줄임, 메모리와 CPU 사이의 속도 차이를 해결하기 위한 계층을 뜻하기도 함

- 캐시 설정 : locality로 자주 사용하는 데이터 파악
    - temporal locality : 최근 사용한 데이터에 다시 접근
    - spatial locality : 최근 접근한 데이터와 가까운 공간에 접근

#### 캐시히트와 캐시미스
- Cache hit: 원하는 데이터를 캐시에서 찾음
- Cache miss : 원하는 데이터가 캐시에 없어 주메모리로 가서 데이터를 찾아오는 것
- Cache mapping : 히트되기 위해 매핑하는 방법
    - Directed mapping : 순서를 일치시킴, 처리가 빠르지만 충돌이 잦음
    - Associative mapping : 순서 일치 X, 충돌이 적지만 느림
    - Set associative mapping : 순서는 일치시키지만 집합은 둬서 저장