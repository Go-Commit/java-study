## 멀티 스레드 개념

#### 프로세스와 스레드
- 하나의 스레드는 하나의 코드 실행 흐름  
- 한 프로세스 내에 두 개 이상의 작업을 처리하는 데 필요한 것이 멀티 스레드  
- 하나의 프로세스 내부에서 생성되기 떄문에 하나의 스레드가 예외를 발생시키면 프로세스 자체가 종료될 수 있어 다른 스레드에게 영향을 미칠 수 있다.

#### 메인 스레드
- 메인 스레드는 필요에 따라 작업 스레드들을 만들어 병렬로 코드를 실핼할 수 있다.
- 멀티스레드는 메인 스레드가 종료되어도 실행중인 스레드가 하나라도 있다면 프로세스는 종료되지 않는다.  

## 작업 스레드 생성과 실행

#### Thread 클래스로부터 직접 생성
```
Thread thread = new Thread(new Runnable() {
  public void run() {
    스레드가 실행할 코드;
  }
});
```
작업 스레드는 생성되는 즉시 실행하는 것이 아니라, start() 메소드를 다음과 같이 호출해야 실행된다.
```
thread.start();
```

#### Thread 하위 클래스로부터 생성
```
Thread thread = new Thread() {
  public void run() {
    스레드가 실행할 코드;
  }
};
````

#### 스레드의 이름
* 메인스레드의 이름은 "main"
* 직접 생성한 스레드는 자동적으로 "Thread-n"
* 다른 이름으로 설정하고 싶다면  
```thread.setName("스레드 이름");```
* 스레드 이름을 알고싶다면   
```thread.getName();```
* setName()와 getName()은 Thread의 인스턴스 메소드이므로 스레드 객체의 참조가 필요하다  
```Thread thread = Thread.currentThread();```

#### 스레드 우선순위
스레드의 개수가 코어의 수보다 많을 경우, 스레드를 어떤 순서에 의해 동시성으로 실행할 것인가를 결정해야 하는데, 이를 스레드 스케줄링이라고 한다.   
* 우선순위 방식
  * 우선순위는 1부터 10까지 부여
  * 1이 가장 낮고, 10이 가장 높다. 우선순위를 부여하지 않으면 기본적으로 5의 우선순위를 할당받는다.
  * 우선순위를 변경하고 싶다면 ```thread.setPriority(우선순위);```
* 순환 할당 방식
  * 시간 할당량를 정해서 각 스레드를 정해진 시간만큼 실행한 뒤에 다음 스레드를 실행
  * JVM에 의해 실행되기 때문에 코드로 제어할 수 없다.


## 동기화 메소드와 동기화 블록

#### 공유 객체를 사용할 떄의 주의할 점
멀티 스레드 프로그램에서는 스레드들이 객체를 공유해서 작업  
스레드 A를 사용하던 객체가 스레드 B에 의해 상태가 변경될 수 있다.

#### 동기화 메소드 및 동기화 블록
스레드가 사용 중인 객체를 다른 스레드가 변경할 수 없도록 하려면 스레드 작업이 끝날 떄까지 객체에 잠금을 걸어서 다른 스레드가 사용할 수 없도록 해야한다.  
스레드가 객체 내부의 동기화 메소드 또는 블록에 들어가면 즉시 객체에 잠금을 걸어 다른 스레드가 임계 영역 코드를 실행하지 못하도록 한다.  
```
public synchronized void method() {
  임계 영역; // 단 하나의 스레드만 실행
}
```

## 스레드 상태 제어

#### 주어진 시간동안 일시 정지
```
try {
  Thread.sleep(1000);
} catch(InterruptedException e) {
  // interrupt() 메소드가 호출되면 실행
}
```

#### 다른 스레드에게 실행 양보
```
public void run() {
  while(true) {
   if(work) {
    System.out.println("ThreadA 작업 내용");
   }
  }
}
```

#### 다른 스레드의 종료를 기다림
```threadB.join();```

#### 스레드 간 협업
```wait(), notify(), notifyAll()```

#### 스레드의 안전한 종료
```
public class XXXThread extends Thread {
  private boolean stop;
  
  public void run() {
    while( !stop ) {
      스레드가 반복 실행하는 코드;
    }
    // 스레드가 사용한 자원 정리
  }
}
```

## 데몬 스레드
데몬 스레드는 주 스레드의 작업을 돕는 보조적인 역할을 수행하는 스레드  
```
public static void main(String[] args) {
  AutoSaveThread thread = new AutoSaveThread();
  thread.setDaemon(true);
  thread.start();
  ...
}
```

## 스레드 그룹
관련된 스레드를 묶어서 관리할 목적으로 이용

#### 스레드 그룹 이름 얻기
```
ThreadGroup group = Thread.currentThread().getThreadGroup();
String groupName = group.getName();
```

#### 스레드 그룹 생성
명시적으로 스레드 그룹을 만들고 싶다면 ThreadGroup 객체를 만들면 된다.
```
ThreadGroup tg = new ThreadGroup(String name);
ThreadGroup tg = new ThreadGroup(ThreadGroup parent, String name);
```

#### 스레드 그룹의 일괄 interrupt()
스레드를 스레드 그룹에 포함시키면 각 스레드에서 interrupt()메소드를 10번 호출할수도 있지만, 스레드 그룹의 interrupt() 메소드를 한번만 호출해주면 된다.

## 스레드풀
갑작스런 병열 작업의 폭증으로 인한 스레드의 폭증을 막으려면 스레드풀을 사용해야 한다.  
스레드풀은 작업 처리에 사용되는 스레드를 제한된 개수만큼 정해 놓고 작업 큐에 들어오는 작업들을 하나씩 스레드르 맡아 처리한다.  
작업 처리가 끝난 스레드는 다시 작업큐에서 새로운 작업을 가져와 처리한다.  
그러미로 작업 처리 요청이 폭증되어도 스레드의 전체 개수가 늘어나지 않아서 애플리케이션의 성능이 급격히 저하되지 않는다.

#### 스레드풀 생성 및 종료
* 스레드풀 생성
```ExecutorService executorService = Executors.newCachedThreadPool();```
* 스레드풀 종료
```executorService.shurdown();```

#### 작업 생성과 처리 요청
* 작업 생성
  하나의 작업은 Runnable 또는 Callble 구현 클래스로 표현된다.
  Runnable의 run() 메소드는 리턴값이 없고, Callable의 call() 메소드는 리턴값이 있다.
* 작업 처리 요청
  작업 처리 요청이란 ExecutorService의 작업 큐에 Runnable 또는 Callable 객체를 넣는 행위를 말한다.

#### 블로킹 방식의 작업 완료 통보
ExecutorService의 submit() 메소드는 매개값으로 준 Runnable 또는 Callable 작업을 스레드풀의 작업 큐에 저장하고 즉시 Future 객체 리턴한다.  
Future 객체는 작업 결과가 아니라 작업이 완료될 떄까지 기다렸다가 최종 결과를 얻는데 사용된다.  
Future의 get() 메소드를 호출하면 스레드가 작업을 완료할 떄까지 블로킹 되었다가 작업을 완료하면 처리 결과를 리턴한다.

* 리턴값이 없는 작업 완료 통보
```
Runnable task = new Runnable() {
  @Override
  public void run() {
    // 스레드가 처리할 작업 내용
  }
}
```
```Future future = executorService.submit(task);```

* 리턴값이 있는 작업 완료 통보
```
Runnable task = new Runnable() {
  @Override
  public void run() {
    // 스레드가 처리할 작업 내용
    return T;
  }
}
```
```Future<T> future = executorService.submit(task);```

* 작업 처리 결과를 외부 객체에 저장
```
Result result = ~;
Runnable task = new Task(result);
Future<Result> future = executorService.submit(task, result);
result = future.get();
```

* 작업 완료 순으로 통보
CompletionService 객체는 처리 완료된 작업을 가져오는 .poll() 메소드와 .take() 메소드를 제공한다.

#### 콜백 방식의 작업 완료 통보
콜백이란 애플리케이션이 스레드에게 작업처리를 요청한 후, 스레드가 작업을 완료하면 특정 메소드를 자동 실행하는 기법  
콜백 메소드를 가진 클래스가 필요  
직접 정의하거나, java.nio.channels.CompletionHandler를 이용  
정상종료를 위한 .completed() 메소드와, 예외처리를 위한 .failed() 메소드가 존재
