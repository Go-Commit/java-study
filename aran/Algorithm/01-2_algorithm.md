# ALGORITHM


### 반복문
-어떤  조건이 성립하는 동안 처리를 반복하며 실행하는 것, 루프(loop) 구조라 한다.

### 01.While문
-실행전에 반복을 계속할지 판단  
-실행전에 판단하는 구조를 사전 판단 반복 구조라 한다.  
-제어식의 평갓값이 0이 아니면 명령문 반복  

##### 실습 1-4
```java
class SumWhile {
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.println("1부터 n까지의 합구하기");
		System.out.print("n : ");
		int n = sc.nextInt();

		int sum = 0;
		int i = 1;

		while(i<=n){
			sum+=i;
			i++;
		}
		System.out.println("sum의 값 : " + sum);
	}
}
```

##### 연습문제6. 실습 1-4에서 while문이 종료될 때 변수 i 값이 n + 1이 됨을 확인하세요
```java
class SumWhile {
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.println("1부터 n까지의 합구하기");
		System.out.print("n : ");
		int n = sc.nextInt();

		int sum = 0;
		int i = 1;

		while(i<=n){
			sum+=i;
			i++;
		}
	 System.out.println("i의 값 : " + i);
	}
}
```

### 02.for문
-하나의 변수를 사용하는 반복문은 while보다 for문이 더 좋다.  
-for(초기화 부분; 제어식; 업데이트 부분) 명령문/실행문  
-초기화 부분은 for문을 실행하기 전 한 번만 실행  
-제어식 값이 true일 때 반복  

##### 실습1-5
```java
class SumWhile {
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.println("1부터 n까지의 합구하기");
		System.out.print("n : ");

		int n = sc.nextInt();
		int sum = 0;

		for(int i=1; i<=n; i++){
			sum+=i;
		}
	 System.out.println("sum의 값 : " + sum);
	}
}
```

##### 연습문제7. 실습 1-5를 참고하여 n이 7이면 1+2+3+4+5+6+7=28 출력하는 프로그램  작성하세요.

```java
class SumWhile {
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.println("1부터 n까지의 합구하기");
		System.out.print("n : ");

		int n = sc.nextInt();
		int sum = 0;
		String str = "";
		for(int i=1; i<=n; i++){
			sum+=i;
			if(i != 7) str+= i+"+";
		}
	 System.out.println(str + "=" + sum);
	}
}
```

##### 연습문제8.1부터 10까지의 합은 (1+10) *5와 같은 방법으로 구할 수 있다. 가우스의 덧셈이라는 방법을 이용하여 1부터 n까지의 정수 합을 구하는 프로그램 작성하세요.
```java
class SumWhile {
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		System.out.println("1부터 n까지의 합구하기");
		System.out.print("n : ");

		int n = sc.nextInt();
		int sum = (1+n)*(n/2);
		System.out.println(str + "=" + sum);
	}
}
```

##### 연습문제9.정수 a,b를 포함하여 그 사이의 모든 정수의 합을 구하여 반환하는 아래 메서드를 작성하시오.
```java
static int sumof(int a, int b)
{
	int max = (a>b)?a:b;
	int min = (a>b)?b:a;

	int sum = 0;

	for(int i=min; i<=max; i++)
		sum+= i;

	return sum;
}
```

### 03.do-while문
-do문 while(제어식);  
-do문은 루프 본문을 한 번 실행 후 계속 반복할 것인지 판단하는 사후판단 반복문  
-for문과의 차이점은 제어식 결과에 따라 실행유무가 다르다 (do-while문은 무조건 한번 실행, for문은 실행하지 않는다)  

##### 실습1-6
```java
class SumForPos {
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		int n;
		System.out.println("1부터 n까지의 합");
		do {
			System.out.print("n의 값:");
			n = sc.nextInt();
		}while(n <= 0);

		int sum = 0;
		for(int i=1; i<=n; i++){
			sum+=i;
		}

		System.out.println("n까지의 합 : " + sum);
	}
}
```

##### 연습문제10.오른쪽과 같이 두 변수 a,b에 정수를 입력하고 b-a를 출력하는 프로그램을 작성하시오.  
```java
class SumForPos {
	public static void main(String[] args){
		Scanner sc = new Scanner(System.in);
		int a,b;

		System.out.print("a의 값 : ");
		a = sc.nextInt();

		do {
			System.out.print("b의 값 : ");
			b = sc.nextInt();

			if(a > b) System.out.println("a 보다 큰수를 입력하세요!");
		}while(a > b);


		System.out.println("b-a는 "+ (b-a) + " 입니다.");
	}
}
```

### 04.구조적 프로그래밍(Structured programming)
-하나의 입구와 하나의 출구를 가진 구성 요소만을 계층적으로 배치하여 프로그램을 구성하는 방법  
-순차, 선택, 반복 3종류의 제어 흐름 사용  

```java
class Digits {
	public static void main(String[]args){
		Scanner stdIn = new Scanner(System.in);
		int no;

		do{
			System.out.print("입력 : ");
			no = sc.nextInt();
		}while(no<10 || no>99);
		System.out.println("변수 no의 값은 " + no + "가 되었습니다.");
	}
}
```

### 05.논리 연산자와 단축평가
-논리곱 : && (조건 모두가 true이면 true)  
-논리합 : || (조건중 하나라도 true이면 true)  
-단축평가(short circuit evaluation) : 논리 연산의 식 전체를 평가한 결과가 왼쪽 피연산자의 평가 결과만으로 정확해지는 경우  

### 06.곱셈표

##### 연습문제12. 오른쪽과 같이 위쪽과 왼쪽에 곱하는 수가 있는 곱셉표를 출력하는 프로그램을 작성하세요.
```java
for(int i=1; i<=9; i++) {
    if(i==1) System.out.print("   | ");
    System.out.print(i+" ");
}
System.out.println();
System.out.println("---+----------------------");

for(int i=1; i<=9; i++) {
    System.out.print(i+"  | ");
    for(int j=1; j<=9; j++) {
        System.out.print((i*j)+" ");
    }
    System.out.println();
}
```

##### 연습문제13. 곱셉이 아니라 덧셈을 출력하는 프로그램 작성
```java
for(int i=1; i<=9; i++) {
    if(i==1) System.out.print("   | ");
    System.out.print(i+" ");
}
System.out.println();
System.out.println("---+----------------------");

for(int i=1; i<=9; i++) {
    System.out.print(i+"  | ");
    for(int j=1; j<=9; j++) {
        System.out.print((i+j)+" ");
    }
    System.out.println();
}
```

##### 연습문제14.입력한 수를 한 변으로 하는 정사각형을 기호로 출력하는 프로그램 작성
```java
Scanner sc= new Scanner(System.in);
System.out.println("사각형을 출력합니다.");
System.out.print("단수 : ");
int num = sc.nextInt();

for(int i=1; i<=num; i++) {
    for(int j=1; j<=num; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

##### 실습1-8.이등변 삼각형 만드는 프로그램 작성
```java
Scanner sc = new Scanner(System.in);
System.out.print(" 변수 : ");
int num = sc.nextInt();
for(int i=1; i<=num; i++) {
    for(int j=1; j<=i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

##### 연습문제15. 직각이등변 삼각형을 출력하는 부분을 아래와 같은 형식의 메서드로 작성하세요.
```java
static void triangleLB(int n) {
    for(int i=1; i<=n; i++) {
        for(int j=1; j<=i; j++)
            System.out.print("*");
        System.out.println();
    }
}
```

##### 연습문제16. n단의 피라미드를 출력하는 메서드를 작성하세요.
```java
static void spria(int n){
  for(int i=1; i<=n; i++) {
      for(int j=1; j<=(n-i); j++) {
          System.out.print(" ");
      }
      for(int j=1; j<=((i-1)*2+1); j++) {
          System.out.print("*");
      }
      System.out.println();
  }
}
```

##### 연습문제17. 오른쪽과 같이 아래를 향한 n단의 숫자 피라미드를 출력하는 메서드 작성하세요.
```java
static void nSpria(int n){
    for(int i=1; i<=n; i++) {
        for(int j=1; j<=(n-i); j++) {
            System.out.print(" ");
        }
        for(int j=1; j<=((i-1)*2+1); j++) {
            System.out.print(i%10);
        }
        System.out.println();
    }
}
```
