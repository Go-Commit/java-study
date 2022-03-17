# 이것이자바다 3장 연습문제

## 1.연산자와 연산식에 대한 설명 중 틀린 것은 무엇입니까?
#### (1)연산자는 피연산자의 수에 따라 단항, 이항, 삼항 연산자로 구분된다.  
#### (2)비교 연산자와 논리 연산자의 산출 타입은 boolean이다.  
#### (3)연산식은 하나 이상의 값을 산출할 수도 있다. → 연산식은 하나의 값만 산출가능  
#### (4)하나의 값이 올 수 있는 자리라면 연산식도 올 수 있다.  

## 2.다음 코드를 실행했을 때 출력 결과는 무엇입니까?
```java
public class Exercise02 {
	public static void main(String [] args){
		int x = 10;
		int y = 20;
		int z = (++x) + (y--);
		System.out.println(z);
	}
}
```
#### ANSWER : 21

## 3.다음 코드를 실행했을 때 출력 결과는 무엇입니까?  
```java
public class Exercise03 {
	public static void main(String[] args){
		int score = 85;
		String result = (!(score>90))? "가":"나";
		System.out.println(result);
	}
}
```
#### ANSWER : 가

## 4.534자루의 연필을 30명의 학생들에게 똑같은 개수로 나누어 줄 때 학생당 몇 개를 가질 수 있고, 최종적으로 몇 개가 남는지를 구하는 코드이다. 알맞은 코드를 작성하라.
```java
public class Exercise04 {
	public static void main(String[] args){
		int pencils = 534;
		int students = 30;

		//학생 한명이 가지는 연필수
		int pencilsPerStudent = pencils/students;
		System.out.println(pencilsPerStudent);

		//남은 연필수
		int pencilsLeft = pencils%students;
		System.out.println(pencilsLeft);
	}
}
```

## 5.십의 자리 이하를 버리는 코드이다. 변수 value 값이 356이라면 300이 나올 수 있도록 코드를 작성하라.
```java
public class Exercise05 {
	public static void main(String[] args){
		int value = 356;
		System.out.println((356/100)*100);
	}
}
```
#### ANSWER : (356/100)*100

## 6.사다리꼴의 넓이를 구하는 코드에서 소수자릿수가 나올 수 있도록 알맞은 코드를 작성하라.  
```java
public class Exercise06 {
	public static void main(String[] args) {
		int lengthTop = 5;
		int lengthBottom = 10;
		int height = 7;
		double area = ((lengthTop + lengthBottom)*(double)height)/2;
		System.out.println(area);
	}
}
```
#### ANSWER : ((lengthTop + lengthBottom)*(double)height)/2;

## 7.비교 연산자와 논리 연산자의 복합 연산식 코드이다. 출력 결과를 작성하라
```java
public class Excrcise07 {
	public static void main(String[] args){
		int x = 10;
		int y = 5;

		System.out.println( (x>7) && (y<=5) ); -> A
		System.out.println( (x%3 == 2) || (y%2 !=1) ); -> B
	}
}
```
#### ANSWER : A - true, B - false

## 8.%연산을 수행한 결과값에 10을 더하는 코드이다. NaN 값을 검사해서 올바른 결과가 출력될 수 있도록 괄호에 NaN을 검사하는 코드를 작성하라
```java
public class Exercise08 {
	public static void main(String[] args) {
		double x = 5.0;
		double y = 0.0;

		double z = x % y;

		if(y < 1.0) {
			System.out.println("0.0으로 나눌 수 없습니다.");
		}else {
			double result = z + 10;
			System.out.println("결과 :"+result);
		}
	}
}
```
#### ANSWER : y<1.0