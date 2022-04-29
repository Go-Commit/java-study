
# 클래스 (Class)

### 1.객체와 클래스에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (3)하나의 클래스로 하나의 객체만 생성할 수 있다.

### 2.클래스의 구성 멤버가 아닌 것은 무엇입니까?
#### 정답 : (4)로컬변수

### 3.필드, 생성자, 메소드에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (4)클래스는 반드시 필드와 메소드를 가져야 한다.

### 4.필드에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (3)필드는 반드시 생성자 선언 전에 선언되어야 한다.

### 5.생성자에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (1)객체를 생성하려면 생성자 호출이 반드시 필요한 것은 아니다.

### 6.메소드에대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (4)메소드의 이름은 중복해서 선언할 수 없다.

### 7.메소드 오버로딩에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (2)반드시 리턴 타입이 달라야 한다.

### 8.인스턴스 멤버와 정적 멤버에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (2)인스턴스 필드는 생성자 및 정적블록에서 초기화 될 수 있다.

### 9.final 필드와 상수(static final)에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (2)final 필드와 상수는 생성자에서 초기화될 수 있다.

### 10.패키지에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (4)mycompany 패키지에 소속된 클래스는 yourcompany에 옮겨 놓아도 동작한다.

### 11.접근 제한에 대한 설명으로 틀린 것은 무엇입니까?
#### 정답 : (3)default 접근 제한은 해당 클래스 내부에서만 사용을 허가한다.

### 12.필드, 생성자, 메소드 위치 찾기
```java
public class Member {
    private String name; // 필드

    public Member(String name); // 생성자

    public void setName(String name) { } // 메소드
}
```

### 13.Member 클래스 선언
```java
public class Member {
    public String name;
    public String id;
    public String password;
    public int age;
}
```

### 14. 13번 문제에 생성자 추가 (name 필드와 id필드를 외부에서 받은 값으로 초기화하기 위한 생성자 작성)
```java
public class Member {
    public String name;
    public String id;
    public String password;
    public int age;

    public Member(String id, String name){
        this.name = name;
        this.id = id;
    }
}
```

### 15.MemberService 클래스에 login() 메소드와 logout() 메소드 선언.
```java
public class MemberService {
    public boolean login(String id, String password) {
        if("hong".equals(id) && "12345".equals(password))
        {
            return true;
        }
        else {
            return false;
        }
    }

    public void logout(String id) {
        System.out.println("로그아웃 되었습니다.");
    }

}
```

### 16.Printer 클래스에서 println() 메소드 선언.
```java
public class Printer {
    public void println(int x) {
        System.out.println(x);
    }

    public void println(boolean x) {
        System.out.println(x);
    }

    public void println(double x) {
        System.out.println(x);
    }

    public void println(String x) {
        System.out.println(x);
    }
}
```

### 17.Printer 객체를 생성하지 않고 호출하기 위해 Printer 클래스 수정.
```java
public class Printer {
    public static void println(int x) {
        System.out.println(x);
    }

    public static void println(boolean x) {
        System.out.println(x);
    }

    public static void println(double x) {
        System.out.println(x);
    }

    public static void println(String x) {
        System.out.println(x);
    }
}
```

### 18.싱글톤 만들기 
```java
public class shopService{
    private static shopService ss = new shopService();

    private shopService(){}

    static shopService getInstance(){
        return shopservice;
    }
}
```

### 19.account 클래스 만들기 
```java
public class Account{

	private int balance;
	public static final int MIN_BALANCE = 0;
	public static final int MAX_BALANCE = 1000000;

	public void setBal(int balance){
		if(balance>=MIN_BALANCE  && balance <= MAX_BALANCE){
			this.balance = balance;
		}
	}

	public void getBal(){
		return this.balance;
	}
}
```

### 20. bankApplication 클래스의 메소드 작성
```java
import java.util.ArrayList;
import java.util.Scanner;

public class bankApplication {
	
	private static Scanner sc = new Scanner(System.in);
	private static ArrayList<account> arr = new ArrayList<account>();

	//main
	public static void main(String args[]) {
		int num = 0;
		while(num != 5) {
			System.out.println("============================================");
			System.out.println("1. 계좌생성 | 2. 계좌목록 | 3. 예금 | 4. 출금 | 5.종료");
			System.out.println("============================================");
			
			System.out.print("INPUT NUMBER : ");
			num = sc.nextInt();
			
			switch(num) {
			case 1:	createAccount(); break;
			case 2:	accountList(); break;
			case 3: deposit(); break;
			case 4: withdraw(); break;
			case 5: System.exit(0); break;
			}
		}
	}
	
	//찾기
	private static account find(String ano) {
		account acc2 = null;		
		
		for(int i =0; i<arr.size();i++) {
			
			if(arr.get(i).getAno().equals(ano)) {
				acc2 = arr.get(i);
			}			
		}
		return acc2;
	}

	//인출
	private static void withdraw() {
		System.out.print("INPUT ACC NUMBER : ");
		String ano = sc.next();
		
		System.out.print("INPUT ACC BALANCE : ");
		int balance = sc.nextInt();
		
		account acc = find(ano);
		acc.setBalance(acc.getBalance() - balance);	
	}

	//예금
	private static void deposit() {
		System.out.print("INPUT ACC NUMBER : ");
		String ano = sc.next();
		
		System.out.print("INPUT ACC BALANCE : ");
		int balance = sc.nextInt();
		
		account acc = find(ano);
		acc.setBalance(acc.getBalance() + balance);	
	}

	//목록
	private static void accountList() {
		for(int i = 0; i<arr.size(); i++) {
			System.out.println(arr.get(i));
		}
	}

	//생성
	private static void createAccount() {
		System.out.println("=========");
		System.out.println("계좌생성");
		System.out.println("=========");
		
		System.out.print("INPUT ACCOUNT NUMBER : ");
		String ano = sc.next();
		
		System.out.print("INPUT ACCOUNT OWNER : ");
		String owner = sc.next();
		
		System.out.print("INPUT ACCOUNT BALANCE : ");
		int balance = sc.nextInt();
		
		account acc = new account(ano, owner, balance);
        arr.add(acc);	
	}
}
```