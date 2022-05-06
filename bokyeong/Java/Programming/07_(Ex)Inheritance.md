
# 상속 (Inheritance)
<br>

```JAVA
// 5.
public class Parent {
    public String name;

    public Parent(String name) {
        this.name = name;
    }
}

public class Child extends Parent {
    private int studentNo;

    public Child(String name, int studentNo) {
        this.name = name;
        this.studentNo = studentNo;
    }
}
```
자식클래스에서 부모클래스를 호출하지를 않았기 때문에


```JAVA
// 6.
public class Parent {
	public String nation;

	public Parent() {
		this("대한민국");
		System.out.println("Parent() call");
	}

	public Parent(String nation) {
		this.nation = nation;
		System.out.println("Parent(String nation) call");
	}
}

public class Child extends Parent {
	private String name;

	public Child() {
		this("홍길동");
		System.out.println("Child() call");
	}

	public Child(String name) {
		this.name = name;
		System.out.println("Child(String name) call");
	}
}

public class ChildExample {
	public static void main(String[] args) {
		Child child = new Child();
	}
}
```
Parent(String nation) call
Parent() call
Child(String name) call
Child() call


```JAVA
// 7.
public class Tire{
    public void run(){
    	System.out.println("일반 타이어가 굴러갑니다.");
    }
}


public class SnowTire extends Tire{
    @Override
    public void run(){
        System.out.println("스노우 타이어가 굴러갑니다.");
    }
}

public class SnowTireExample{
    public static void main(String[] args){
    	SnowTire snowTire = new SnowTire();
        Tire tire = snowTire;
        
        snowTire.run();
        tire.run();
    }
}
```
"스노우 타이어가 굴러갑니다."
"스노우 타이어가 굴러갑니다."
