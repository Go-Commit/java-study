#### 13
```
public class Member {
  String name;
  String id;
  String password;
  int age;
}
```

#### 14
```
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

#### 15
```
public class MemberService {
  boolean login(String id, String password) {
    if(id.equals("hong") && password.equals("12345"))
      return true;
    return false;
  }
  void logout(String id) {
    System.out.println("로그아웃");
  }
}
```

#### 16
```
public class Printer {
  void println(int value) {
    System.out.println(value);
  }
  void println(boolean value) {
    System.out.println(value);
  }
  void println(double value) {
    System.out.println(value);
  }
  void println(String value) {
    System.out.println(value);
  }
}
```

#### 17
```
public class Printer {
  static void println(int value) {
    System.out.println(value);
  }
  static void println(boolean value) {
    System.out.println(value);
  }
  static void println(double value) {
    System.out.println(value);
  }
  static void println(String value) {
    System.out.println(value);
  }
}
```

#### 18
```
public class ShopService {
  private ShopService() {}
  private static ShopService obj = new ShopService();
  static ShopService getInstance() {
    return obj;
  }
}
```

#### 19
```
public class Account {
  static final int MIN_BALANCE = 0;
  static final int MAX_BALANCE = 1000000;
  private int balance;

  int getBalance() {
    return balance;
  }

  void setBalance(int balance) {
    if(balance >= MIN_BALANCE && balance <= MAX_BALANCE)
      this.balance = balance;
  }
}
```

#### 20
```
// 계좌 만들기
private static void createAccount() {
	System.out.print("계좌 번호: ");
	String ano = scanner.next();
	System.out.print("계좌주: ");
	String owner = scanner.next();
	System.out.print("초기입금액: ");
	int balance = scanner.nextInt();
	
	ExAccount newAccount = new ExAccount(ano, owner, balance);
	
	for(int i = 0; i < accountArray.length; i++) {
		if(accountArray[i] == null) {
			accountArray[i] = newAccount;
			System.out.println("계좌 생성 완료");
			break;
		}
	}
}

// 계좌 목록
private static void accountList() {
	System.out.println("계좌 목록");
	for(int i = 0; i < accountArray.length; i++) {
		if(accountArray[i] != null) {
			System.out.printf("%s\t\t%s\t%d\n", accountArray[i].getAno(), accountArray[i].getOwner(), accountArray[i].getBalance());
		}
	}
}

// 예금하기
private static void deposit() {
	System.out.println("예금");
	System.out.print("계좌번호: ");
	String ano = scanner.next();
	System.out.print("예금액: ");
	int money = scanner.nextInt();
	ExAccount newAccount = findAccount(ano);
	if(ano == null) {
		System.out.println("계좌 없음");
	} else {
		newAccount.setBalance((newAccount.getBalance()+money));
		System.out.println("예금 성공");
	}
}

// 출금하기
private static void withdraw() {
	System.out.println("출금");
	System.out.print("계좌번호: ");
	String ano = scanner.next();
	System.out.print("출금액: ");
	int money = scanner.nextInt();
	ExAccount newAccount = findAccount(ano);
	if(ano == null) {
		System.out.println("계좌 없음");
	} else {
		newAccount.setBalance((newAccount.getBalance()-money));
		System.out.println("출금 성공");
	}
}

private static ExAccount findAccount(String ano) {
	for(int i = 0; i < accountArray.length; i++) {
		if(ano.equals(accountArray[i].getAno()))
			return accountArray[i];
	}
	return null;
}
```
