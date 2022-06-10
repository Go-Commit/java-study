## 10

#### 6
```
public class TryCatchFinallyExample {
	public static void main(String[] args){
    	String[] strArray = { "10" , "2a" };
        int value = 0;
        for(int i = 0; i <= 2; i++ ){
        	try{
            	value = Integer.parseInt(strArray[i]);
            } catch(ArrayIndexOutOfBoundException e){
            	System.out.println("인덱스를 초과했음");
            } catch(NumberFormatException e) {
            	System.out.println("숫자로 변환할 수 없음");
            } finally {
            	System.out.println(value);
            }
        }
    }
}
```
10
숫자로 변환할 수 없음
10
인덱스를 초과했음
10

#### 7
```
public class NotExistIDException extends Exception{
	public NotExistIDException() {}
	public NotExistIDException(String message) {
		super(message);
	}
}
```

```
public class WrongPasswordException extends Exception{
	public WrongPasswordException() {}
	public WrongPasswordException(String message) {
		super(message);
	}
}
```

```
public class LoginExample {
	public static void main(String[] args) {
		try {
			login("white", "12345");
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}
		try {
			login("blue", "54321");
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}
	}
	public static void login(String id, String password) throws NotExistIDException, WrongPasswordException{
		if(!id.equals("blue")) {
			throw new NotExistIDException("아이디 없음");
		}
		if(!password.equals("12345")) {
			throw new WrongPasswordException("패스워드 불일치");
		}
	}
}
```

## 11

#### 3
```
public class Student {
    private String studentNum;
    
    public Student(String studentNum) {
        this.studentNum = studentNum;
    }
    
    public String getStudentNum() {
        return studentNum;
    }
    
    @Override
    public boolean equals(Object o) {
        if (o instanceof Student) {
            Student student = (Student) o;
            if (studentNum.equals(student.studentNum)) {
                return true;
            }
        }
        return false;
    }
  
    @Override
    public int hashCode() {
        return studentNum.hashCode();
    }
}
```
```
public class StudentExample {
    public static void main(String[] args) {
        HashMap<Student, String> hashMap = new HashMap<Student, String>();
        hashMap.put(new Student("1"), "95");
        
        String score = hashMap.get(new Student("1"));
        System.out.println("1번 학생의 총점 : "+score);
 
    }
 
}
```

#### 4
```
public class Member {
    private String id;
    private String name;
    
    public Member(String id, String name) {
        this.id = id;
        this.name = name;
    }
    
    @Override
    public String toString() {
        return id + " : " + name;
    }
}
```

#### 5
```
public class Member {
    private String id;
    private String name;
    
    public Member(String id, String name) {
        this.id = id;
        this.name = name;
    }
    
    @Override
    public String toString() {
        return id + " : " + name;
    }
}

public class MemberExample {
 
    public static void main(String[] args) {
        Member member = new Member("blue", "이파란");
        System.out.println(member);
    }
}
```

#### 6
```
public class BytesToStringExample {

    public static void main(String[] args) {
        byte[] bytes = {73, 32, 108, 111, 118, 101, 32, 121, 111, 117};
        String str = new String(bytes);
        System.out.println(str);
    }
}
```

#### 8
```
public class SplitExample {
 
    public static void main(String[] args) {
        String str = "아이디, 이름, 패스워드";
        
        String[] str1 = str.split(",");
        for (int i = 0 ; i < str1.length; i++) {
            System.out.println(str1[i]);
        }
    }
}

```

#### 10
```
public class PatternMatcherExample {
 
    public static void main(String[] args) {
        String id = "5Angel1004";
        String regExp = "[a-zA-Z][a-zA-Z0-9]{7,11}";
        boolean isMatch = Pattern.matches(regExp, id);
        if (isMatch) {
            System.out.println("ID로 사용할 수 있습니다.");
        } else {
            System.out.println("ID로 사용할 수 없다.");
        }
    }
}
```

#### 11
```
public class IntegerCompareExample {
 
    public static void main(String[] args) {
        Integer obj1 = 100;
        Integer obj2 = 100;
        Integer obj3 = 300;
        Integer obj4 = 300;
        
        System.out.println(obj1 == obj2);
        System.out.println(obj3 == obj4);
    }
}
```
