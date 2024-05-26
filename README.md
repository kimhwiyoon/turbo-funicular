# 리눅스 명령어의 top, ps, jobs, kill 명령어에 대하여 #

***

## top 명령어란? ##

+ 시스템의 현재 상태를 실시간으로 모니터링할 수 있게 해주는 명령어
+ CPU, 메모리 사용량, 실행 중인 프로세스 등의 정보를 제공

**주요기능**
1. 업타임 (Uptime): 시스템이 얼마나 오랫동안 가동 중인지 표시
2. 사용자 세션 (User sessions): 현재 시스템에 로그인한 사용자 수를 표시
3. 로드 평균 (Load average): 1분, 5분, 15분 동안의 시스템 부하 표시
4. 작업 (Tasks): 현재 실행 중, 대기 중, 중지된 프로세스와 좀비 프로세스의 수 표시
5. CPU 상태 (CPU states): CPU의 사용 상태를 보여줍니다. 사용자 모드, 시스템 모드, 유휴 상태 등의 비율 확인
6. 메모리 사용량 (Memory usage): 물리적 메모리와 스왑 메모리의 사용량 표시
7. 프로세스 목록 (Process list): 실행 중인 프로세스의 목록과 각 프로세스에 대한 상세 정보를 제공, 여기에는 PID, 사용자, 우선순위, 메모리 사용량, CPU 사용률 등이 포함된다.

**top 명령어의 인터랙티브 명령**
- q: top 명령어를 종료
- h: 도움말을 표시
- k: 특정 프로세스를 종료, PID를 입력해야 한다.
- r: 특정 프로세스의 우선순위를 변경, PID와 새로운 우선순위 값을 입력해야 한다.
- s: 화면 갱신 주기를 변경, 기본값은 3초
- f: 출력 포맷을 변경

***

## ps 명령어란? ##

1. 현재 실행 중인 프로세스의 정보를 보여주는 명령어
2. 다양한 옵션을 제공하여, 상세한 정보와 특정 조건을 만족하는 프로세스들만을 필터링하여 표시 가능
3. PID(프로세스 ID), TTY(프로세스가 연결된 터미널), 시간(프로세스가 사용한 CPU 시간), CMD(실행된 명령어) 등의 컬럼으로 구성된다.
4. 사용자는 ps 명령어와 grep 명령어를 사용하여 특정 프로세스를 빠르게 찾을 수 있다.
5. ps 명령어는 시스템 모니터링, 프로세스 관리, 문제 해결 등 다양한 상황에서 유용하게 사용된다.

**ps 명령의 인터랙티브 명령어**

* 현재 사용자의 프로세스 보기: ps
* 모든 실행 중인 프로세스 보기: ps -e 또는 ps aux
   * ps -e는 모든 프로세스를 표시
   * ps aux는 사용자, CPU 사용량, 메모리 사용량 등 더 많은 정보를 표시
* 특정 사용자의 프로세스 보기: ps -u 사용자이름
* 프로세스의 트리 구조 보기: ps -efH 또는 pstree
   * 프로세스 간의 부모-자식 관계를 계층적으로 보여줍니다.
* 특정 프로세스에 대한 정보 검색: ps -C 프로세스이름

***

## jobs 명령어란? ## 

1. 현재 쉘 세션에서 실행 중이거나 중지된 작업의 목록을 표시
   * 사용자가 백그라운드에서 실행 중인 프로세스나 중지된 프로세스를 관리할 때 유용
2. 출력에 작업 번호, 상태(예: 실행 중, 중지됨), 그리고 명령어가 포함된다.
3. 작업 번호는 현재 쉘 세션 내에서 해당 작업을 식별하는 데 사용된다.
   * 이 번호를 사용하여 fg 명령어로 작업을 전경으로 가져오거나, bg 명령어로 백그라운드에서 계속 실행 가능하다.
  
**주요 상태**

* Running: 작업이 실행 중
* Stopped: 작업이 일시 중지, 일반적으로 Ctrl+Z를 통해 작업이 중지
* Terminated: 작업이 종료됌

**jobs 명령의 인터랙티브 명령어**

* l: 프로세스 ID(PID)와 함께 작업을 나열
* n: 이전에 보고되지 않은 작업에 대해서만 보고
* p: 각 작업에 대해 PID만 나열
* r: 실행 중인 작업만 나열
* s: 중지된 작업만 나열



