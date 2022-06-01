
# 예외처리 (Exception Handling)

### 1.예외에 대한 설명 중 틀린 것은 무엇입니까?
###### 4)자바 표준 예외만 프로그램에서 처리할 수 있다. -> 사용자가 정의한 예외도 처리할 수 있다.


### 2. try-catch-finally 블록에 대한 설명 중 틀린 것은 무엇입니까?
###### 3) try {} 블록에서 return문을 사용하면 finally {} 블록은 실행되지 않는다. -> return 을 사용하더라도 finally는 무조건 실행된다.


### 3. throws에 대한 설명으로 틀린 것은 무엇입니까?
###### 4) 새로운 예외를 발생시키기 위해 사용된다. -> 예외 발생시키기 위해서는 throw를 사용한다.


### 4. throw에 대한 설명으로 틀린 것은 무엇입니까?
###### 2) 예외를 호출한 곳으로 떠넘기기 위해 메소드 선언부에 작성된다. -> 메소드 선언부에 작성되는 키워드는 throws, thorw - 예외 발생

### 5.다음과 같은 메소드가 있을 때 예외를 잘못 처리한 것은 무엇입니까?
```java
public void method() throws NumberFormatException, ClassNotFoundException {}
```
###### 3) try { method(); } catch(Exception e) {} catch (ClassnotFoundException e) {} -> 모든 예외는 상위 클래스인 Exception을 상속받기 때문에 첫 catch 블록에 Exception을 두면 모두 그 로직을 타기 때문에 상위 클래스는 아래쪽에 위치해야 한다.


### 6.다음 코드가 실행되었을 때 출력 결과는 무엇입니까?
```java
public class TryCatchFinallyExample {
    public static void main(String[] args) {
        String[] strArray = {"10","2a"};
        int value = 0;

        for(int i=0; i<=2; i++) {
            try {
                value = Integer.parseInt(strArray[i]);
            }catch(ArrayIndexOutOfBoundsException e) {
                System.out.println("인덱스를 초과했음");
            }catch(NumberFormatException e){
                System.out.println("숫자로 변환할 수 없음");
            } finally {
                System.out.println(value);
            }
        }
    }
}
```

###### 10  
###### 숫자로 변환할 수 없음  
###### 10  
###### 인덱스를 초과했음  
###### 10


### 7.Member 클래스의 login() 메소드 구현시 존재하지 않는 ID 입력했을 경우 NotExistIDException을 발생시키고 잘못된 패스워드를 입력했을 경우 WrongPasswordException을 발생시켜라

```java
// 사용자 정의 예외 클래스 1
public class NotExistIDException extends Exception {
    public NotExistIDException() {}

    public NotExistIDException(String message) {
        super(message);
    }
}

// 사용자 정의 예외 클래스 2
public class WrongPasswordException extends Exception {
    public WrongPasswordException() {}

    public WrongPasswordException(String message) {
        super(message);
    }
}

public class LoginExample {
    public static void main(String[] args) {
        try {
            login("white", "12345");
        }catch(Exception e) {
            System.out.println(e.getMessage());
        }

         try {
            login("blue", "54321");
        }catch(Exception e) {
            System.out.println(e.getMessage());
        }

        public static void login(String id, String password) throws NotExistIDException, WrongPasswordException {
            if(id.equals("blue")) {
                throw new NotExistIDException("아이디가 존재하지 않습니다.");
            }

            if(password.equals("12345")) {
                throw new NotExistIDException("패스워드가 틀립니다.");
            }
        }
    }
}


```