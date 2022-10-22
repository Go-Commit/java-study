
# CPU Scheduling
<br>

## 1. CPU-burst Time의 분포

* 프로세스의 특성 분류 *bursts : 연속적으로 쓰는 시간
  * I/O bound job
    * CPU를 잡고 계산하는 시간보다 I/O에 많은 시간이 필요한 job (many short CPU bursts)
  * CPU bound job
    * 계산 위주의 job (few very long CPU bursts)
<br>

> I/O bound job은 사람하고 소통하기 때문에, 예를 들어 키보드를 입력했는데 바로 안나온다면 답답해서 못쓴다. 그래서 I/O bound job은 빠른 응답이 필요하다.
<br>

* 여러 종류의 job(process)이 섞여 있기 때문에 CPU 스케줄링이 필요하다.
  * Interacive job에게 적절한 response 제공 요망
  * CPU와 I/O장치 등 시스템 자원을 골고루 효율적으로 사용
<br>


## 2. CPU Scheduler & Dispatcher
* CPU Scheduler
  * Ready 상태의 프로세스 중에서 이번에 CPU를 줄 프로세스를 고른다.
* Dispatcher
  * CPU의 제어권을 CPU scheduler에 의해 선택된 프로세스에게 넘긴다.
  * 이 과정을 context switch(문맥 교환)라고 한다.
<br>

* CPU 스케줄링이 필요한 경우는 프로세스에게 다음과 같은 상태 변화가 있는 경우이다.
  1. Running > Blocked (예: I/O 요청하는 시스템 콜)
  2. Running > Ready (예: 할당시간 만료로 timer interrupt)
  3. Blocked > Ready (예: I/O 완료 후 인터럽트)
  4. Terminate
* 1, 4에서의 스케줄링은 nonpreemptive (=강제로 빼앗지 않고 자진 반납)
* All other scheduilng is preemptive(=강제로 빼앗음)
<br>

### 3. Scheduling Algorithms
* FCFS (First-Come First-Served)
* SJF (Shortes-Job-First)
* SRTF (Shortest-Remaining-Time-First)
* Priority Scheduling
* RR (Round Robin)
* Multilevel Queue
* Mulitlevel Feedback Queue
<br>

### 4. Scheduling Criteria (Performance Index=Performance Measure=성능 척도)
* CPU utilization(이용률)
  * keep the CPU as busy as possible
* Throughput (처리량)
  * of process that complete their execution per time unit
* Turnaround time (소요시간, 반환시간)
  * amount of time to execute a paricular precess
* Waiting time (대기 시간)
  * amount of time a process has been waiting in the ready queue
* Response time (응답 시간)
  * amount of time it takes from when a request was submitted until the first response is produced, not output (for time-sharing environment)

> Turnaround time, Waiting time, Response time 고객의 입장에서 본다면 어떤 시간이든 빠른 시간이 좋은 것으로 생각하면 된다.


