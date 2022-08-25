
# Process Management
<br>

## 1. 프로세스 생성 (Process Creaction)
* 부모 프로세스(Parent Process)가 자식 프로세스(Children Process) 생성
* 프로세스의 트리(계층 구조) 형성
* 프로세스는 자원을 필요로 함
  * 운영체제로 부터 받는다.
  * 부모와 공유한다.
* 자원의 공유
  * 부모와 자식이 모든 자원을 공유하는 모델
  * 일부를 공유하는 모델
  * 전혀 공유하지 않는 모델
* 수행 (Execution)
  * 부모와 자식이 공존하며 수행되는 모델
  * 자식이 종료(terminate) 될 때 까지 부모가 기다리는(wait) 모델
* 프로세스가 마지막 명령을 수행한 후 운영체제에게 이를 알려줌 (exit)
  * 자식이 부모에게 output data를 보냄 (via wait)
  * 프로세스의 각종 자원들이 운영체제에게 반납됨
* 부모 프로세스가 자식의 수행을 종료시킴 (abort)
  * 자식이 할당 자원이 한계치를 넘어섬
  * 자식에게 할당된 태스크가 더 이상 필요하지 않음
  * 부모가 종료(exit)하는 경우
    * 운영체제는 부모 프로세스가 종료하는 경우 자식이 더 이상 수행되도록 두지 않는다.
    * 단계적인 종료
<br>

## 2. fork() 시스템 콜
* A process is created by the fork() system call.
  * creates a new address space that is a duplicate of the caller.

```C
int main()
{
  int pid;
  pid = fork();
  if (pid == 0) /*this is child*/
    printf("\n Hello, I am child! \n");
  else if (pid > 0) /*this is parent*/
    printf("\n Hello, I am parent! \n");
}
```
<br>


## 3. exec() 시스템 콜
* A process can execute a different program by the exec() system call.
  * replaces the memory image of the coller with a new program

```C
int main()
{
  int pid;
  pid = fork();
  if (pid == 0) /*this is child*/
    printf("\n Hello, I am child! Now I'll run date \n");
    // execlp : exec() 시스템 콜을 호출한다.
    execlp("/bin/date", "bin/date", (char *)0);
  else if (pid > 0) /*this is parent*/
    printf("\n Hello, I am parent!\n");
}
```
<br>

예를 들면, cmd 창에서 ls -l을 실행하는 것 처럼
> execlp("ls", "ls", "-l", (char *)0);
<br>

## 4. wait() 시스템 콜
* 프로세스 A가 wait 시스템 콜을 호출하면
  * 커널은 child가 종료될 때 까지 프로세스 A를 sleep 시킨다. (block 상태)
  * Child Process가 종료되면 커널은 프로세스 A를 깨운다. (ready 상태)

```C
main()
{
  int childPID;
  S1;

  childPID = fork();

  if(childPID == 0)
    <code for child process>
  else {
    wait();
  }
  S2;
}
```
vi A
<br>
vi 가 실행 되는 도중에는 다른 command 명령은 수행하지 못한다.
<br>


## 5. exit() 시스템 콜
프로세스의 종료
  * 자발적 종료
    * 마지막 statement 수행 후 exit() 시스템 콜을 통해 프로그램에 명시적으로 적어주지 않아도 main 함수가 리턴되는 위치에 컴파일러가 넣어줌
  * 비자발적 종료
    * 부모 프로세스가 자식 프로세스를 강제 종료 시킴
      * 자식에게 프로세스가 한계치를 넘어서는 자원 요청
      * 자식에게 할당된 태스크가 더 이상 필요하지 않음
    * 키보드로 kill, break 등을 친 경우
    * 부모가 종료하는 경우
      * 부모 프로세스가 종료하기 전에 자식들이 먼저 종료됨
<br>


## 6. 프로세스와 관련한 시스템 콜
* fork() : create a child (copy)
* exec() : overlay new image
* wait() : sleep until child is done
* exit() : frees all the resources, notify parent
<br>


### 7. 프로세스 간 협력
* 독립적 프로세스 (Independent Process)
  * 프로세스는 각자의 주소 공간을 가지고 수행되므로 원칙적으로 하나의 프로세스는 다른 프로세스의 수행에 영향을 미치지 못함
* 협력 프로세스 (Cooperating Process)
  * 프로세스는 협력 메커니즘을 통해 하나의 프로세스가 다른 프로세스의 수행에 영향을 미칠 수 있음
* 프로세스 간 협력 메커니즘 (IPC : InterProcess Communication)
  * 메시지를 전달하는 방법 
    * message passing : 커널을 통해 메시지 전달
  * 주소 공간을 공유하는 방법
    * shared memory : 서로 다른 프로세스 간에도 일부 주소 공간을 공유 하게 하는 shared memonry 메커니즘이 있음
    * thread : thread는 사실상 하나의 프로세스이므로 프로세스 간 협력으로 보기는 어렵지만 동일한 process를 구성하는 thread들 간에는 주소 공간을 공유하므로 협력이 가능

