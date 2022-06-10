
# 기본API 클래스 (API Class)

### 1번  
###### 1번 답 : 4번 -> toString() 메소드로 객체의 필드값을 문자열로 리턴하려면 따로 toString 메소드를 재정의 해주어야 한다.

### 2번
###### 2번 답 : hashCode() , equals()

### 3번
###### 3번 답
```java
public class StudentExample {
	public static void main(String[] args)
	{
		HashMap<Student, String> hashMap = new HashMap<Student, String>();

		hashMap.put(new Student("1"), "95");

		String score = hashMap.get(new Student("1"));

		System.out.println("1번 학생의 총점: " + score);
	}
}

public class Student {
	private String studentNum;
	public Student(String studentNum) {
		this.studentNum = studentNum;
	}

	public String getStudentNum() {
		return studentNum;
	}

	@Override
	public boolean equals(Object obj) {
		if(obj instanceof Student)
		{
			Student student = (Student)obj;
			if(studentNum.equals(student.getStudentNum()))
				return true;
		}
		return false;
	}

	@Override
	public int hashCode() {
		return studentNum.hashCode();
	}
}
```

### 4번
###### 4번 답
```java
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

### 5번
###### 5번 답 : 4 -> newInstance() 메소드의 리턴타입은 Object이므로 원래 클래스 타입으로 변환해야만 메소드를 사용할 수 있다.

### 6번 
###### 6번 답 : 
```java
public class BytesToStringExample {
	public static void main(String[] args) {
		byte[] bytes = {73,32,108,111,118,101,32,121,111,117 };
		String str = new String(bytes);
		System.out.println(str);
	}
}
```

### 7번
###### 7번 답
```java
public class FindAndReplaceExample {
	public static void main(String[] args) {
		String str = "모든 프로그램은 자바 언어로 개발될 수 있다.";
		int index = str.indexOf("자바");
		if(index == -1)
			System.out.println("자바 문자열이 포함되어 있지 않습니다.");
		else
		{
			System.out.println("자바 문자열이 포함되어 있습니다.");
			str = str.replace("자바", "Java");
			System.out.println("-->" + str);
		}
	}
}
```

### 8번
###### 8번 답
```java
import java.util.StringTokenizer;

public class SplitExample {
	public static void main(String[] args) {
		String str = "아이디,이름,패스워드";

		String[] str1 = str.split(",");
		for (String s : str1)
			System.out.println(s);

		System.out.println();
		
		StringTokenizer str2 = new StringTokenizer("아이디,이름,패스워드", ",");
		while (str2.hasMoreTokens()) {
			String s = str2.nextToken();
			System.out.println(s);
		}
	}
}
```

### 9번
###### 9번 답
```java
public class StringBuilderExample {
    public static void main(String[] args) {
        String str = "";
        for (int i = 0 ; i <= 100; i++) {
            str += i;
        }
        System.out.println(str);
        
        StringBuilder sb = new StringBuilder();
        for (int i = 0 ; i <= 100; i++) {
            sb.append(i);
        }
        System.out.println(sb);
    }
}
```

### 10번
###### 10번 답
```java
import java.util.regex.Pattern;
 
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

### 11번
###### 11번 답
```java
public class IntegerCompareExample {
    public static void main(String[] args) {
        Integer obj1 = 100;
        Integer obj2 = 100;
        Integer obj3 = 300;
        Integer obj4 = 300;
        
        System.out.println( obj1 == obj2);
        System.out.println( obj3 == obj4);
    }
}
```

### 12번
###### 12번 답
```java
public class StringConvertExample {
    public static void main(String[] args) {
        String strData1 = "200";
        int intData1 = Integer.parseInt(strData1);
        
        int intData2 = 150;
        String strData2 = Integer.toString(150);
    }
}
```

### 13번
###### 13번 답
```java
import java.text.SimpleDateFormat;
import java.util.Date;
 
public class DatePrintExample {
 
    public static void main(String[] args) {
        Date now = new Date();
        System.out.println(now);
        SimpleDateFormat sdf = new SimpleDateFormat("YYYY년 MM월 DD일 E요일 k시 m분");
        System.out.println(sdf.format(now));
    }
}
```