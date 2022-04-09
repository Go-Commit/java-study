# ALGORITHM

### 실습 1-1
### 입력한 3개의 정수중 제일 큰 수 구하기
```java

import java.util.Scanner;
public class Max {
	public static void main(String []args)
	 {
		 Scanner sc = new Scanner(System.in);

		 System.out.print("첫번째 값 : "); int one_num = sc.nextInt();
		 System.out.print("두번째 값 : "); int two_num = sc.nextInt();
		 System.out.print("세번째 값 : "); int three_num = sc.nextInt();

		 int max = one_num;
		 if(two_num > max) {
			 max = two_num;
		 }
		 if(three_num > max) {
			 max = three_num;
		 }

		 System.out.println("최고 값 : " + max);
	 }
}
```
##### 여러 문장이 순차적으로 실행되는 구조를 순차적(concatenation)구조
##### if 조건에 따라 프로그램의 흐름을 변경하는 if문을 선택(selection) 구조
##### 변수를 만드는 시점에 값을 넣는 것은 '초기화', 이미 만들어진 변수에 값을 넣는 것은 '대입'

### 실습 1-2
### 최대값 리턴하는 함수 만들기
```java
public class Max {
	static int max3(int a, int b, int c) {
        int max = a;
        if(b>max) max=b;
        if(c>max) max=c;
        return max;
    }
    public static void main(String[] args) {
        int result = max3(1,2,3);
        System.out.println("최고값 : "+result);
    }
}
```
##### 메서드를 정의할 때 전달되는 값은 매개변수, 호출할 때 전달되는 값은 실인수, 인자값


### 연습 1-1
### 네 값의 최댓값을 구하는 max4 메서드 작성
```java
static int max4(int a, int b, int c, int d) {
	int max = a;
	if(b>max) max=b;
	if(c>max) max=c;
	if(d>max) max=d;

	return max;
}
```

### 연습 1-2
### 세 값의 최솟값을 구하는 min3 메서드 작성
```java
static int min3(int a, int b, int c) {
	int min=a;
	if(min>b) min = b;
	if(min>c) min = c;

	return min;
}
```

### 연습 1-3
### 네 값의 최솟값을 구하는 min4 메서드 작성
```java
static int min4(int a, int b, int c, int d) {
	int min=a;
	if(min>b) min = b;
	if(min>c) min = c;
	if(min>d) min = d;

	return min;
}
```

### 실습 1C-1
### 세 숫자의 중앙 값을 구하는 메서드 작성
```java
static int mid(int a, int b, int c) {
	if(a>=b) {
		if(b>=c) {
			return b;
		}
		else if(c>=a) {
			return a;
		}
		else {
			return c;
		}
	}
	else if(a>c) {
		return a;
	}
	else if(c>b) {
		return b;
	}
	else {
		return c;
	}
}

public static void main(String[] args) {
	int result = mid(3,10,6);
	System.out.println("결과 : "+ result);
}
```

### 연습 1-4  
### 세 값의 대소 관계 13종류의 모든 조합에 대해 중앙값 구하는 프로그램 
```java
static int mid(int a, int b, int c) {
	if(a>=b) { 
		if(b>=c)
			return b;
		else if(a>=c)
			return c;
		else
			return a;
	}
	else if(a>=c) {
		return a;
	}
	else if(b<=c) {
		return b;
	}
	else {
		return c;
	}
}
```

### 연습 1-5
### 중앙값을 구하는 메서드는 다음과 같이 작성할 수도 있습니다. 그러나 실습 1C-1의 med3 메서드에 비해 효율이 떨어지는데 그 이유를 설명하라 
```java
static int med3 (int a, int b, int c) {
	if((b>=a&&c<=a>) || (b<=a&&c>=a)){
		return a;
	}
	else if( (a>b && c<b) || (a<b&&c>b) )
	{
		return b;
	}
	return c;
}

첫번째 if문의 조건을 성립한 경우 두번째 if에서도 같은 판단을 수행하므로 효율이 나쁘다.
```

### 연습 1-3  
### 입력한 정숫값의 부호 판단
```java
public static void main(String[] args) {
	Scanner sc = new Scanner(System.in);
	System.out.print("정수를 입력하세요 > ");
	int num = sc.nextInt();

	if(num>0) {
		System.out.println(num+ "은 정수입니다.");
	}
	else if(num<0) {
		System.out.println(num+"은 음수입니다.");
	}
	else
	{
		System.out.println(num+"은 0입니다.");
	}
}
```