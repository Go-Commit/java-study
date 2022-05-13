
# 인터페이스 (Interface)
<br>

```JAVA
// 3.
public interface Soundable { 
	String sound(); 
}

public class SoundableExample {
	private static void printSound(Soundable soundable) {
		System.out.println(soundable.sound());
	}

	public static void main(String[] args) {
		printSound(new Cat());
		printSound(new Dog());
	}
}

public class Cat implements Soundable { 
	@Override 
	public String sound() { 
		String catSound = "야옹"; return catSound; 
	} 
}

public class Dog implements Soundable { 
	@Override 
	public String sound() { 
		String dogSound = "멍멍"; return dogSound; 
	} 
}
```

```JAVA
// 4.
public class DabExample {
	public static void dbWork(DataAccessObject dao) { 
		dao.select(); 
		dao.insert(); 
		dao.update(); 
		dao.delete(); 
	}

	public static void main(String[] args) {
		dbWork(new OracleDao());
		dbWork(new MysqlDao());
	}
}

public interface DataAccessObject { 
	void select(); 
	void insert(); 
	void update(); 
	void delete();
}

public class OracleDao implements DataAccessObject { 
	@Override 
	public void select() { 
		System.out.println("Oracle DB에서 검색"); 
	} 
	
	@Override 
	public void insert() { 
		System.out.println("Oracle DB에 삽입"); 
	} 
	
	@Override 
	public void update() { 
		System.out.println("Oracle DB를 수정"); 
	} 
	
	@Override 
	public void delete() { 
		System.out.println("Oracle DB에서 삭제"); 
	} 
}

public class MySqlDao implements DataAccessObject { 
	@Override 
	public void select() { 
		System.out.println("MySqlDao에서 검색"); 
	} 
	
	@Override 
	public void insert() { 
		System.out.println("MySqlDao에서 삽입"); 
	} 
	
	@Override 
	public void update() { 
		System.out.println("MySqlDao에서 수정"); 
	} 
	
	@Override 
	public void delete() { 
		System.out.println("MySqlDao에서 삭제"); 
	} 
}
```


```JAVA
// 5.
public interface Action { 
	void work(); 
}

public class ActionExample { 
	public static void main(String[] args) { 
		Action action = new Action() { 
			public void work() { 
				System.out.println("복사를 합니다."); 
			} 
		}; 
		action.work(); 
	} 
}
```
