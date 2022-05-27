
# 중첩 클래스와 인터페이스 (Nested Class&Interface)
<br>

```JAVA
// 4.
public class Car {
	class Tire { }
	static class Engine { }
}

public class NestedClassExample {
	public static void main(String[] args) {
		Car myCar = new Car();

		Car.Tire tire = myCar.new Tire();
		Car.Engine engine = new Car.Engine();
	}
}
```

```JAVA
// 5.
public interface Vehicle {
	public void run();
} 

public Class Anoymous {
	Vehicle field = new Vehicle() {
        @Override
        public void run(){
        	System.out.println("자전거가 달립니다.");
        }
    };

	void method1() {
		Vehicle localVar = new Vehicle() {
            @Override
            public void run(){
            	System.out.println("승용차가 달립니다.");
            }
        };

		localVar.run();
	}

	void method2(Vehicle v) {
		v.run();
	}
}

public class AnoymousExample {
	public static void main(String[] args) {
		Anoymous anony = new Anonymous();
		anony.field.run();
		anony.method();
		anony.method(new Vehicle() {
            @Override
            public void run() {
            	System.out.println("트럭이 달립니다.");
            }
		});
	}
}
```
