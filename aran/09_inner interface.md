
# 중첩인터페이스 (Inner Interface)

### 1.중첩 멤버 클래스에 대한 설명으로 틀린 것은 무엇입니까?  
###### 정답 : 4)정적 멤버 클래스 내부에는 바깥 클래스의 인스턴스 필드를 사용할 수 있다. -> 사용할 수 없다.

### 2.로컬 클래스에 대한 설명으로 틀린 것은 무엇입니까?  
###### 정답 : 3)로컬 클래스는 static 키워드를 이용해서 정적 클래스로 만들 수 있다. -> 접근 제어자를 사용할 수 없다. 메소드 내부에서 선언된 클래스이기 때문에 접근 제어자를 붙일 수 없다.

### 3.익명 객체에 대한 설명으로 틀린 것은 무엇입니까?  
###### 정답 : 3)익명 객체에는 생성자를 선언할 수 있다. -> 생성자 선언할 수 없다.

### 4.Car 클래스 내부에 Tire와 Engine이 멤버 클래스로 선언되어 있습니다. nestedClassExample에서 멤버 클래스의 객체를 생성하는 코드를 작성하세요.
```java
public class NestedClassExample {
    public static void main(String [] args)
    {
        Car myCar = new Car();
        Car.Tire tire = myCar.new Tire();
        Car.Engine engine = myCar.new Engine();
    }
}
```

### 5.AnonymousExample 클래스의 실행 결과를 보고 Vehicle 인터페이스의 익명 구현 객체를 이용해서 필드, 로컬 변수의 초기값과 메소드의 매개값을 대입하세요.
```java

public class car {
    public void run();
}

public class Anonymous {
    Vehicle field = new Vehicle(){
        @Override
      void run(){
          System.out.println("자전거가 달립니다.");
      }
    };

    void method1() {
        Vehicle localVar = new Vehicle(){
            @Override
            void run() {
                System.out.println("승용차가 달립니다.");
            }
        };
        localVar.run();
    }

    void method2(Vehicle v) {
        v.run();
    }
}

public class AnonymousExample {
    public static void main(String[]args)
    {
        Anonymous anony = new Anonymous();
        anony.field.run();
        anony.method1();
        anony.method2(new Vehicle(){
            @Override
            void run(){
                System.out.println("트럭이 달립니다.");
            }
        });
    }
}

```

### 6.Chatting 클래스는 컴파일 에러가 발생합니다. 원인을 설명하세요.

###### 정답 : 익명 객체 내부에서 사용하는 변수는 final을 선언하지 않더라도 않더라도 final 특성을 가져야하는데 nickName 변수에 null 값으로 정의한 다음 chatId로 다시 정의했기 때문에 final 특성을 무시하였기에 컴파일 에러가 발생한다.