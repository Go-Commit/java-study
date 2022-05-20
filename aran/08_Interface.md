
# 인터페이스 (Interface)

### 1.인터페이스에 대한 설명으로 틀린 것은 무엇입니까?
##### 답 : (3)인터페이스는 인스턴스 필드를 가질 수 있다. -> 인터페이스는 상수와 메소드만을 가질 수 있다.

### 2.인터페이스의 다형성과 거리가 먼 것은?
##### 답 : (4)구현 객체를 인터페이스 타입으로 변환하려면 강제 타입 변환을 해야한다.->자동 타입변환이 된다.

### 3.Cat과 Dog 클래스 작성하기
```java
public class Cat implements Soundable {
    String sound() {
        String catSound = "야옹";
        return catSound;
    }
}

public class Dog implements Soundable {
    String sound() {
        String dogSound ="멍멍";
        return dogSound;
    }
}
```

### 4.OracleDao, MySqlDao 구현 클래스 작성하기
```java
public class OracleDao implements DataAccessObject{
    @Override
    public void select() {
        System.out.println("Oracle DB에서 검색");
    }
    @Override
    public void insert() {
        System.out.println("Oracle DB에서 삽입");
    }
    @Override
    public void update() {
        System.out.println("Oracle DB에서 수정");
    }
    @Override
    public void delete() {
        System.out.println("Oracle DB에서 삭제");
    }
}
```

```java
public class MySqlDao implements DataAccessObject{
    @Override
    public void select() {
        System.out.println("MySql DB에서 검색");
    }
    @Override
    public void insert() {
        System.out.println("MySql DB에서 삽입");
    }
    @Override
    public void update() {
        System.out.println("MySql DB에서 수정");
    }
    @Override
    public void delete() {
        System.out.println("MySql DB에서 삭제");
    }
}
```

### 5.ActionExample 클래스 코드 완성하기
```java
public class ActionExample {
    public static void main(String [] args) {
        Action action = new Action() {
            public void work() {
                System.out.println("복사를 합니다.");
            }
        };
        action.work();
    }
}
```