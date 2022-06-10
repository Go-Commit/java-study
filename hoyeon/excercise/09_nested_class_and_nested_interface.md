#### 4
```
public class NestedClassExample {
	public static void main(String[] args) {
		Car myCar = new Car();
		Car.Tire tire = myCar.new Tire();
		Car.Engine engine = new Car.Engine();
	}
}
```

#### 5
```
public class Anonymous {
	Vehicle field = new Vehicle() {
		@Override
		public void run()
		{
			System.out.println("자전거가 달립니다.");
		}
	};
	void method1() {
		Vehicle localVar = new Vehicle() {
			@Override
			public void run()
			{
				System.out.println("승용차가 달립니다.");
			}
		};
		localVar.run();
	}
	
	void method2(Vehicle v) {
		v.run();
	}
}
```
```
public class AnonymousExample {
	public static void main(String[] args) {
		Anonymous anony = new Anonymous();
		anony.field.run();
		anony.method1();
		anony.method2(new Vehicle() {
			@Override
			public void run() {
				System.out.println("트럭이 달립니다.");
			}
		});
	}
}
```
