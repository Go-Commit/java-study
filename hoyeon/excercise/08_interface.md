#### 1
```
3 >> 인터페이스는 상수 필드와 메소드 필드만을 가질 수 있다.
```

#### 2
```
4 >> 자동 타입 변환되기 때문에 강제 타입 변환할 필요 없다.
```

#### 3
```
public class Cat implements Soundable{
    @Override
    public String sound(){
    	return "야옹";
    }
}

public class Dog implements Soundable{
    @Override
    public String sound(){
    	return "멍멍";
    }
}
```

#### 4
*DataAccessObject
```
public interface DataAccessObject {
	void select();
	void insert();
	void update();
	void delete();
}
```
*OraleDao
```
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
*MySqlDao
```
public class MySqlDao implements DataAccessObject{
    @Override
    public void select() {
        System.out.println("mysql에서 검색");
    }

    @Override
    public void insert() {
        System.out.println("mysql에서 삽입");
    }

    @Override
    public void update() {
        System.out.println("mysql에서 수정");
    }

    @Override
    public void delete() {
        System.out.println("mysql에서 삭제");
    }
}
```

#### 5
```
public class ActionExample{
    public static void main(String[] args){
        Action action = new Action() {
          @Override
          public void work() {
            System.out.println("복사를 합니다.");
          }
		    };
        action.work();
    }
}
```
