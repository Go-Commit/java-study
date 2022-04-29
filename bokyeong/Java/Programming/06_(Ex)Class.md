
# 클래스 (Class))
<br>

```JAVA
// 13.
public class Member {
	String name;
	String id;
	String password;
	int age;
}
```

```JAVA
// 14.
public class Member {
	String name;
	String id;
	String password;
	int age;

	Member(String name, String id) {
		this.name = name;
		this.id = id;
	}
}
```

```JAVA
// 15.
public class MemberServiceExample {
	public static void main(String[] args) {
		MemberService memberService = new MemberService();
		boolean result = memberService.login("hong", "12345");
		if(result) {
			System.out.println("로그인 되었습니다.");
			memberService.logout("hong");
		} else {
			System.out.println("id 또는 password가 올바르지 않습니다.");
		}
	}
}

public class MemberService {
	boolean login(String id, String password) {
		if("hong".equals(id) && "12345".equals(password))
			return true;
		else
			return false;
	}

	void logout(String id) {
		System.out.println("로그아웃 되었습니다.");
	}
}
```

```JAVA
// 16.
public class PrinterExample {
	public static void main(String[] args) {
		Printer printer = new Printer();
		printer.println(10);
		printer.println(true);
		printer.println(5.7);
		printer.println("홍길동");
	}
}

public class Printer {
	void println(int x) {
		System.out.println(x);
	}

	void println(boolean x) {
		System.out.println(x);
	}

	void println(double x) {
		System.out.println(x);
	}

	void println(String x) {
		System.out.println(x);
	}			
}
```

```JAVA
// 17.
public class PrinterExample {
	public static void main(String[] args) {
		Printer printer = new Printer();
		printer.println(10);
		printer.println(true);
		printer.println(5.7);
		printer.println("홍길동");
	}
}

public class Printer {
	static void println(int x) {
		System.out.println(x);
	}

	static void println(boolean x) {
		System.out.println(x);
	}

	static void println(double x) {
		System.out.println(x);
	}

	static void println(String x) {
		System.out.println(x);
	}			
}
```

```JAVA
// 18.
public class ShopServiceExample {
	public static void main(String[] args) {
		ShopService obj1 = ShopService.getInstance();
		ShopService obj2 = ShopService.getInstance();
		
		if(obj1 == obj2) {
			System.out.println("같은 ShopService 객체 입니다.");
		} else {
			System.out.println("다른 ShopService 객체 입니다.");
		}
	}
}

public class ShopService {
	private static ShopService shopservice = new ShopService();

	private ShopService() {}
	static ShopService getInstance() {
		return shopservice;
	}			
}
```

```JAVA
// 19.
public class AccountExample {
	public static void main(String[] args) {
		Account account = new Account();
		
		account.setBalance(10000);
		System.out.println("현재 잔고: " + account.getBalance());
		
		account,setBalance(-100);
		System.out.println("현재 잔고: " + account.getBalance());
		
		account.setBalance(2000000);
		System.out.println("현재 잔고: " + account.getBalance());
		
		account.setBalance(300000);
		System.out.println("현재 잔고: " + account.getBalance());
	}
}

public class Account {
	static final int min_balance = 0;
	static final int max_balance = 1000000;

	private int balance = 0;

	public void setBalance(int balance) {
		if(balance >= MIN_BALANCE && balance <= MAX_BALANCE) {
			this.balance = balance;
		}
	}

	public int getBalance() {
		return this.balance;
	}
}
```

```JAVA
// 20.
public class Account {
	private String ano;
	private String owner;
	private int balance;
	
	public Account(String ano, String owner, int balance) {
		this.ano = ano;
		this.owner = owner;
		this.balance = balance;
	}

	public String getAno() {
		return ano;
	}

	public void setAno(String ano) {
		this.ano = ano;
	}

	public String getOwner() {
		return owner;
	}

	public void setOwner(String owner) {
		this.owner = owner;
	}

	public int getBalance() {
		return balance;
	}

	public void setBalance(int balance) {
		this.balance = balance;
	}
}

import java.util.Scanner;
public class BankApplication {
	private static Account[] accountArray = new Account[100];
	private static Scanner scanner = new Scanner(System.in);
		
	public static void main(String [] args) {
		boolean run = true;
		while(run) {
			System.out.println("--------------------------------------------");
			System.out.println("1. 계좌생성 | 2. 계좌목록 | 3. 예금 | 4. 출금 | 5. 종료");
			System.out.println("--------------------------------------------");
			System.out.print("선택 > ");
			
			int selectNo = scanner.nextInt();
			
			if(selectNo == 1) {
				createAccount();
			} else if(selectNo == 2) {
				accountList();
			} else if(selectNo == 3) {
				deposit();
			} else if(selectNo == 4) {
				withdraw();
			} else if(selectNo == 5) {
				run = false;
			}
		}
		System.out.println("프로그램 종료");
	}

	// 계좌 생성하기
	private static void createAccount() {
		System.out.println("---------------");
		System.out.println("계좌생성");
		System.out.println("---------------");

		System.out.print("계좌번호 : ");
		Sring accountNo = scanner.next();
		System.out.print("계좌주 : ");
		Sring accountOwner = scanner.next();
		System.out.print("초기입금액 : ");
		Sring accountMoney = scanner.next();

		Account newAccount = new Account(accountNo, accountOwner, accountMoney);
	}
	
	// 계좌 목록 보기
	private static void accountList() {

	}
	
	// 예금하기
	private static void deposit() {

	}
	
	// 출금하기
	private static void withdraw() {

	}
	
	// Account 배열에서 ano와 동일한 Account 객체 찾기
	private static Account findAccount(String ano) {

	}
}
```