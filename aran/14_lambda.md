# 람다식(Lambda)
##### 1.람다식 의미  
###### - 익명함수를 생성하기 위한 표현방법  
###### - 간결한 표현으로 익명 구현 객체 코드를 간결하게 표현할 수 있다.  
```
Runnable runnable = new Runnable() {
    public void run() { }
}

Runnable runnable = () -> { };
```

##### 2. 람다식 표현방법  
```
(타입 매개변수, …) -> { 실행문 }
(int a) -> { System.out.print(a); }
(a) -> { System.out.print(a); }
a -> System.out.print(a);

(x,y) -> { return x+y; } = (x,y) -> x+y;
```
###### -괄호는 실행블록을 실행하기 위한 매개변수 역할  
###### - ‘->’는 매개변수를 이용해 실행블록을 실행한다는 의미  
###### -매개변수의 타입은 런타임 시 입력값에 따라 자동으로 인식되기 때문에 람다식에서는 타입을 생략.  
###### -괄호와 중괄호도 생략 가능  
###### -return문도 생략 가능  

##### 3. 람다식과 인터페이스
###### -인터페이스 객체에 람다식을 대입할 경우, 해당 인터페이스를 람다식의 타겟 타입이라고 부름  
###### -두개 이상의 추상메서드가 선언된 인터페이스는 람다식을 이용할 수 없음  
###### -하나의 추상 메서드가 선언된 인터페이스만 람다식을 이용할 수 있는데, 그런 인터페이스를 함수적 인터페이스라고 부름  
###### (@FunctionalInterface 어노테이션을 붙이면 하나의 추상 메서드만 구현하도록 컴파일러가 체킹)  

##### 3. 람다식의 멤버
###### -보통 익명 객체 내부에서 사용하는 this는 익명 객체의 참조지만, 람다식에서 this는 람다식을 실행한 객체의 참조  
###### -람다식은 보통 메소드 내부에서 작성되는데 메소드의 있는 매개(또는 로컬)변수를 사용할 경우 이 두 변수는 final 특성을 가져야 함 (final 특성으로 인해 변수 값 수정 불가)  
```
// 인터페이스
public interface MyFunctionalInterface {
	public void method();
}

// 구현 클래스
public class UsingThis {
	public int ouuterField = 10;

	class Inner {
		int innerField = 20;
		
		void method = () {
			MyFunctionalInterface fi = ()->{
				System.out.println(“ouuterField :”+ouuterField);
				// outterField를 사용하기 위해 클래스명.this 사용
				System.out.println(“ouuterField :”+UsingThis.this.outterField);

				System.out.println(“innerField :”+innerField);
				// 람다식 내부에서 this는 Inner 객체 참조
				System.out.println(“innerField :”+this.innerField);
            };
            fi.method();
        }
    }
}

// 실행 클래스
public class UsingThisExample {
	public static void main(String [] args) {
		UsingThis ut = new UsingThis();
		UsingThis.Inner inner = usingThis.new Inner();
		inner.method();
    }
}
```

##### 4. 람다식 API 함수적 인터페이스
###### -자바8부터는 빈번하게 사용되는 함수적 인터페이스를 java.util.function 표준 API로 제공  
###### -함수적 인터페이스 안에는 각 인터페이스마다 지원하는 내장함수가 다름  

| 인터페이스 | 매개값 & 리턴값 |
| ------ | ------ |
| Consumer | 매개값 O / 리턴값 X |
| Supplier | 매개값 X / 리턴값 X |
| Function | 매개값 O / 리턴값 O 주로 매개값을 리턴값으로 매핑 |
| Operator | 매개값 O / 리턴값 O 주로 매개값을 연산하여 결과값을 리턴 |
| Predicate | 매개값 O / 리턴 타입 boolean, 매개값을 조사하여 true, false를 리턴 |

```
Consumer<String> consumer = t -> { t를 소비하는 실행문 };
Consumer<String> consumer = t -> System.out.print(t + “8”);
consumer.accept(“java”); // java8 출력
```

##### 5. 람다식 참조
###### -매개변수, 리턴 타입을 통해 람다식에서 불필요한 매개 변수를 제거
###### -정적, 인스턴스 메소드, 생성자 참조가 가능
###### -참조 방법은 클래스 이름 뒤에 :: 기호 붙이고 정적 메서드 이름 기술

```
클래스or참조변수 :: 메소드

// 정적 메소드
public class Calcul {
    public static int staticMethod(int x, int y) {
        return x+y;
    }
}

// 정적 메서드 참조
public class MethodReference {
	public static void main(String[]args){
		IntBinaryOperator op;
		op = (x,y) -> Calcul.staticMethod(x,y);
		System.out.print(“결과1:”+ op.applyAsInt(1,2)); *applyint - 내장 함수
	
		op = Calcul :: staticMethod; // 정적 메서드 참조
		System.out.print(“결과2:”+ op.applyAsInt(3,4));
    }
}
```

##### 6. 생성자 참조  
###### -객체 생성 후 리턴하는 람다식은 참조로 대치 가능  
###### -생성자 참조 방법은 클래스 이름 뒤에 :: 기호 붙이고 new 연산자 기술  
```
클래스 :: new

// 생성자 참조 클래스
public class ConstructorReference {
	public static void main(String[] args) {
		Function<String, Member> function1 = Member :: new;
		Member member1 = function1.apply(“aran”); // Member(String id) 실행
	}
}

// 참조할 생성자 클래스
public class Member {
	private String name;

    public Member() {
        System.out.println(“Member() 실행”);
    }	

	public Member(String id) {
		System.out.println(“Member(String id) 실행”);
	}
}
```



