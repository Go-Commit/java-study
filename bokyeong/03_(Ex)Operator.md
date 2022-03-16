
# 연산자 (Operator)
<br>

## 1. 컬랙션 프레임워크
자료 구조(Data Sturcture)를 바탕으로 객체들을 효율적으로 추가, 삭제, 검색할 수 있도록 java.util 패키지에 컬렉션과 관련된 인터페이스와 클래스들을 포함시킨 것의 총칭
<br>
- Collection : 객체를 수집해서 저장
- Framework : 사용 방법을 미리 정해놓은 라이브러리

|인터페이스|분류|특징|구현클래스|
|------|---|---|-----|
|Collection|List|- 순서를 유지하고 저장 <br> - 중복 저장 가능|ArrayList, Vector, LinkedList|
||Set|- 순서를 유지하지 않고 저장 <br> - 중복 저장 안 됨|HashSet, TreeSet|
|Map||- 키와 값의 쌍으로 저장 <br> - 키는 중복으로 저장 안 됨|HashMap, Hashtable, TreeMap, Properties|
<br>

## 2. List 컬렉션
- 객체를 저장하면 자동으로 인덱스 부여
  - 인덱스로 객체를 검색, 삭제할 수 있는 기능 제공
- 객체 자체를 저장하는 것이 아니라, 객체의 번지를 참조함

#### ArrayList
- 배열은 생성할 때 크기가 고정되고 사용 중에 크기를 변경할 수 없지만, ArrayList는 저장 용량을 초과한 객체가 들어오면 자동적으로 저장 용량이 늘어남
- 특정 인텍스의 객체를 제거하면 바로 뒤의 인덱스부터 마지막 인덱스까지 모두 앞으로 당겨짐
  - 빈번한 객체의 삭제와 삽입이 일어나는 곳에서는 사용하지 않는 것이 좋음
```JAVA
List<String> list = new ArrayList<String>(); // 컬렉션 생성
list.add("홍길동");                          // 컬렉션에 객체를 추가
String nmw = list.get(0);                    // 컬렉션에서 객체를 얻음
```

#### Vector
- ArrayList와 다르게 동기화된 메소드로 구성되어 있기 때문에 멀티스레드가 동시에 이 메소드들을 실행할 수 없고, 하나의 스레드가 실행을 완료해야만 다른 스레드를 실행할 수 있음

#### LinkedList
- ArrayList는 내부 배열에 객체를 저장해서 인덱스로 관리하지만, LinkedList는 인접 참조를 링크해서 체인처럼 관리함
  - 빈번한 객체 삭제와 삽입이 일어나는 곳에서 사용하기 좋음 
<br>

## 3. Set 컬렉션
- List 컬렉션은 저장 순서를 유지하지만, Set 컬렉션은 저장 순서가 유지되지 않음
- 객체를 중복해서 저장할 수 없고, 하나의 null만 저장할 수 있음
- 인덱스로 객체를 검색해서 가져오는 메소드가 없어서 반복자(Iterator 인터페이스를 구현한 객체)를 제공함
```JAVA
Set<String> set = ...;
Iterator<String> iterator = set.iterator();
```

#### HashSet
- 객체를 저장하기 전에 먼저 객체의 hashCode() 메소드를 호출해서 해시코드를 얻어 저장되어 있는 객체들의 해시코드와 비교<br>
=> 동일한 해시코드가 있다면 다시 equals() 메소드로 두 객체를 비교해서 ture가 나오면 동일한 객체로 판단하고 중복 저장을 하지 않음
<br>

## 4. Map 컬랙션
- 키(key)와 값(value)으로 구성된 Entry 객체를 저장하는 구조
- 키는 중복으로 저장될 수 없지만 값은 중복으로 저장될 수 있음
- 기존에 저장된 키와 동일한 키로 값을 저장 시 기존의 값은 없어지고 새로운 값으로 대치

#### HashMap
- 키로 String 타입을 사용하고 값으로 Integer 타입을 사용하는 경우
```JAVA
Map<String, Integer> map = new HashMap<String, Integer>();
```
#### HashTable
- 메소드로 구성되어 있기 때문에 멀티스레드가 동시에 이 메소드를 실행할 수 없고, 하나의 스레드가 실행을 완료해야만 다른 스레드를 실행할 수 있음
  - 멀티스레드 환경에서 안전하게 객체를 추가, 삭제할 수 있음

#### Properties
- HashTable의 하위 클래스
  - HashTable은 키와 값을 다양한 타입으로 지정할 수 있지만, Properties는 키와 값은 String으로 제한한 컬렉션임
<br>

## 5. 검색 기능을 강화시킨 컬렉션
- Set 컬렉션 : TreeSet
- Map 컬렉션 : TreeMap

#### 이진 트리 구조 (binary tree)
- 여러 개의 노드(node)가 트리형태로 연결된 구조
- 루트노드 -> 부모노드 -> 자식노드

#### TreeSet
- 이진 트리를 기반으로 한 Set 컬렉션
- TreeSet 객체 저장 시 자동 정렬
  - 부모 값과 비교해서 낮은 것은 왼쪽 자식 노드에, 높은 것은 오른쪽 자식 노드에 저장

#### TreeMap
- 이진 트리를 기반으로 한 Map 컬렉션
- TreeMap 객체 저장 시 자동 정렬
  - 부모 키값과 비교해서 낮은 것은 왼쪽 자식 노드에, 높은 것은 오른쪽 자식 노드에 Map.Entry 객체 저장

#### Comparable 과 Comparator
- TreeSet 객체와 TreeMap의 키는 저장과 동시에 자동으로 오름차순 정렬
- 사용자 정의 클래스도 Comparable을 구현하여 자동 정렬 가능
  - 사용자 정의 클래스에서 Comparable의 compareTo() 메소드를 오버라이딩하여 리턴 값을 만들어 내야 함
<br>

## 6. LIFO와 FIFO 컬렉션
- 후입선출(LIFO; Last In First Out)
  - 나중에 넣은 객체가 먼저 빠져나가는 자료구조
 
- 선입선출(FIFO; First In Frist Out)
  - 먼저 넣은 객체가 먼저 빠져나가는 자료구조

#### Strack
- LIFO 자료구조를 구현한 클래스

#### Queue
- FIFO 자료구조를 구현한 클래스
<br>

## 7. 동기화된 컬렉션
- 싱글 스레드 환경에서 사용하다가 멀티 스레드 환경으로 전달하는 경우
- 비동기화 된 메소드를 동기화된 메소드로 래핑하는 컬렉션
  - synchronizedList();
  - synchronizedSet();
  - synchronizedMap();
<br>

## 8. 병렬 처리를 위한 컬렉션
- ConcurrentHashMap
  - 부분 잠금을 사용하여 처리하는 요소가 포함된 부분만 잠금하고 나머지 부분은 스레드가 변경할 수 있도록 함
- ConcurrentLinkedQueue
  - 락-프리(lock-free) 알고리즘 구현
  - 여러 개의 스레드가 동시에 접근할 경우, 잠금을 사용하지 않고도 최소한 하나의 스레드가 안전하게 요소를 저장하거나 얻도록 해줌
