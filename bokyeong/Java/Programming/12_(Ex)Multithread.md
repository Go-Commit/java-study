
# 멀티 스레드(Multithread)
<br>

```JAVA
// 2.
public class ThreadExample {
 
    public static void main(String[] args) {
        Thread thread1 = new MovieThread();
        thread1.start();
        
        Thread thread2 = new Thread(new MusicRunnalbe());
        thread2.start();
    }
}

public class MovieThread extends Thread {
    @Override
    public void run() {
        for (int i = 0 ; i < 3; i++) {
            System.out.println("동영상을 재생합니다.");
        }
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
        }
    }
}

public class MusicRunnalbe implement Runnalbe{
    @Override
    public void run() {
        for (int i = 0 ; i < 3;i++) {
            System.out.println("음악을 재생합니다.");
        }
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
        }
    }
}

```

```JAVA
// 8.
public class ThreadExample {
 
    public static void main(String[] args) {
        Thread thread = new MovieThread();
        thread.start();
        
        try { Thread.sleep(1000); } catch (InterruptedException e) {}

        thread.interrupt();
    }
}

public class MovieThread extends Thread {
    @Override
    public void run() {
        for (int i = 0 ; i < 3; i++) {
            System.out.println("동영상을 재생합니다.");
            if (Thread.interrupted()) {
                break;
            }
        }
    }
}
```

```JAVA
// 10.
public class ThreadExample {
 
    public static void main(String[] args) {
        Thread thread = new MovieThread();
        thread.setDaemon(true);
        thread.start();
        
        try { Thread.sleep(3000); } catch (InterruptedException e) {}
    }
}
```