## 스트림 소개
스트림은 컬렉션(배열 포함)의 저장 요소를 하나씩 참조해서 람다식으로 처리할 수 있도록 해주는 반복자

#### 반복자 스트림

```
List<String> list = Arrays.asList("홍길동", "김자바");
Stream<String> stream = list.stream();
stream.forEach( name -> System.out.println(name));
```

#### 스트림의 특징
* 람다식으로 요소 처리 코드를 제공한다.
* 내부 반복자를 사용하므로 병렬 처리가 쉽다.
  * 하나씩 처리하는 순차적 외부 반복자 보다는 효율적으로 요소 반복 
* 중간 처리와 최종 처리를 할 수 있다.

## 스트림의 종류
![streamType](StreamType.png)

## 스트림 파이프라인

#### 중간 처리 메소드와 최종 처리 메소드
![stream2](streamMidFinalMethod.png)

## 병렬처리
* 하나의 작업을 분할해서 각각의 코어가 병렬적 처리
* 작업 처리 시간을 줄일 수 있다

#### 동시성과 병렬성
* 동시성: 멀티 작업을 위해 멀티 스레드가 번갈아가며 실행하는 성질
* 병렬성: 멀티 작업을 위해 멀티 코어를 이용해서 동시에 실행하는 성질

#### 병렬 스트림 생성
* parallelSTream() 메소드는 컬렉션으로부터 병렬 스트림을 바로 리턴
* parallel() 메소드는 순차 처리 스트림 병렬 처리 스트림으로 변환해서 리턴

#### 병렬 처리 성능
* 요소 수가 적고 요소당 처리 시간 짧으면 순차 처리가 빠름
* 스트림 소스의 종류에 따라 영향을 미침
  * ArrayList, 배열은 인덱스로 요소를 관리하여 병렬 처리가 빠름
  * HashSet, TreeSet은 요소분리가 쉽지 않아 순차 처리가 빠름
* 싱글 코어의 경우 순차 처리가 빠름