# 이것이자바다 4장 연습문제

## 1.조건문과 반복문의 종류를 괄호 속에 넣어보세요.
#### ㅁANSWER  
#### 반복문 : for, do-while, while / 조건문 : switch, if

## 2.조건문과 반복문을 설명한 것 중 틀린 것은 무엇입니까?
#### 1)if문은 조건식의 결과에 따라 실행 흐름을 달리할 수 있다.  
#### 2)switch문에서 사용할 수 있는 변수의 타입은 int, double이 될 수 있다.  
#### 3)for문은 카운터 변수로 지정한 횟수만큼 반복시킬 때 사용할 수 있다.
#### 4)break문은 switch문, for문, while문을 종료할 때 사용할 수 있다.
#### ㅁANSWER  
#### 2번 switch문에서 사용할 수 있는 변수타입은 byte, char, short, int, long이 있다.

## 3.for문을 이용해 1부터 100까지 정수 중에서 3의 배수의 총합을 구하는 코드를 작성해보세요.
```java
public class Example {
    public static void main(String[] args)
    {
        int result = 0;
		for(int i=1; i<=100; i++) {
			if(i%3 == 0) {
				result+=i;
			}
		}
        System.out.println(result);
    }
}
```

## 4.while문과 Math.random() 메소드를 이용해서 두 개의 주사위를 던졌을 때 나오는 눈을 (눈1,눈2) 형태로 출력하고, 눈의 합이 5가 아니면 계속 주사위를 던지고, 눈의 합이 5이면 실행을 멈추는 코드를 작성해보세요.
```java
public class Example {
	public static void main(String[] args){
		while(true){
            int num1 = (int)(Math.random()*6)+1;
            int num2 = (int)(Math.random()*6)+1;
            System.out.println("num1:"+num1+"/num2:"+num2);
            if((num1+num2) == 5) break;
		}
	}
}
```

## 5.중첩 for문을 이용하여 방정식 4x + 5y = 60의 모든 해를 구해서 (x,y) 형태로 출력해보세요. 단 x와 y는 10이하의 자연수입니다.
```java
public class Example {
	public static void main(String[] args) {
		for(int x=1; x<=10; x++) {
			for(int y=1; y<=10; y++) {
				if(4*x + 5*y == 60) System.out.println("("+x+","+y+")");
			}
		}
	}
}
```

## 6.for문을 이용해서 실행 결과와 같은 삼각형을 출력하는 코드를 작성해보세요.
```java
public class Example {
	public static void main(String[] args) {
		for(int x=1; x<=5; x++) {
			for(int y=1; y<=5; y++) {
                if(x>=y) System.out.print("*");
			}
            System.out.println();
		}
	}
}
```

## 7.while문과 Scanner를 이용해서 키보드로부터 입력된 데이터로 예금, 출금, 조회, 종료 기능을 제공하는 코드를 작성해보세요.
```java
import java.util.Scanner;

public class Example {
	public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int tradeMoney = 0;
        boolean flag = true;
		while(flag)
        {
            System.out.println("---------------------------");
            System.out.println("1.예금|2.출금|3.잔고|4.종료");
            System.out.println("---------------------------");
            System.out.print("선택 > ");
            int choseNum = sc.nextInt();

            switch(choseNum) {
                case 1: System.out.print("예금액>");
                        int inMoney = sc.nextInt();
                        tradeMoney += inMoney;
                        break;
                case 2: System.out.print("출금액>");
                        int outMoney = sc.nextInt();
                        if(tradeMoney>=outMoney) {
                            tradeMoney -= outMoney;
                        }else {
                            System.out.println("잔고가 부족합니다.");
                            System.out.println("현재잔고>"+tradeMoney);
                        }
                        break;
                case 3: System.out.println("잔고>"+tradeMoney);
                        break;
                case 4: flag = false;
                        break;
                default : System.out.println("적합하지 않은 메뉴입니다.");
            }
        }
        System.out.println("프로그램 종료");
		sc.close();
	}
}
```