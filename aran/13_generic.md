# 제네릭(Generic)
#### 01. 제네릭 타입
###### -타입을 파라미터로 갖는 클래스와 인터페이스
###### -클래스와 인터페이스 이름뒤에 "<>", 그 안에 파라미터 입력

#### 02. 제네릭을 사용하는 이유
##### 02-1) 신텍스 타입체크
###### - 컴파일 시 타입 체크 에러가 발생하기 때문에 실행 전에 미리 신텍스 체크를 할 수 있다.
##### 02-2) 불필요한 타입 변환 제거
```
List list = new ArrayList();
list.add("hello");
String str = (String)list.get(0); // 강제 형변환을 해야 꺼낼 수 있다.

List<String> list = new ArrayList<String>();
list.add("hello");
String str = list.get(0);
```
###### - List에 문자열을 저장후 꺼내올 때 강제로 String 타입으로 강제 형변환을 해줘야한다.  
###### - 제네릭 코드로 수정시 List에 저장되는 요소를 String으로만 제한하기 때문에 불필요한 타입 변환을 없앴다.  

#### 03. 세가지 타입  
##### 03-1)멀티타입  
###### - 제네릭은 두개 이상 멀티 타입 파라미터로 사용 가능  
###### - 두개 이상 사용시 , (콤마)로 구분  

##### 03-2)최상위타입  
###### - 제네릭타입 파라미터를 이용하여 타입 제한을 할 수 있음  

```
// 사용방법
public <T extends 상위타입>리턴타입 메소드(매개변수, ... ) { }

// number 하위 타입만 사용할 수 있는 제네릭 타입 설정
public <T extends Number> int compare(T t1, T t2) { }
```

##### 03-3)와일드카드 타입  
###### - 제네릭타입<?> : 모든 클래스나 인터페이스 타입  
###### - 제네릭타입<? extends 상위타입> : 상위 타입 또는 하위 타입  
###### - 제네릭타입<? super 하위타입> : 상위 타입 또는 하위 타입  

###### -Example<?> : 모든타입 (Person, Worker, Student, HightStudent)  
###### -Example<? extends Student> : Student와 HightStudent  
###### -Example<? super Worker> : Person과 Worker
