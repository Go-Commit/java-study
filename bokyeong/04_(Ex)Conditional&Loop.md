
# 조건문과 반복문 (Conditional&Loop)
<br>

```JAVA
public class Excercise03 {
    public static void main(String[] args) {
        int sum = 0;
        for(int i=1; i<=100; i++) {
            if(i%3==0) {
                sum += i;
            }
        }

        System.out.println("3의 배수의 합 : " + sum);
    }
}
// --> 3의 배수의 합 : 1683
```

```JAVA
public class Excercise04 {
    public static void main(String[] args) {
        int num1 = 0;
        int num2 = 0;

        while((num1+num2) != 5) {
            num1 = (int)(Math.random()*6)+1;
            num2 = (int)(Math.random()*6)+1;
            System.out.println("("+num1+", "+num2+")");
        }
    }
}
```

```JAVA
public class Excercise05 {
    public static void main(String[] args) {
        int num1;
        int num2;
        for(int i=1; i<=10; i++) {
            for(int j=1; j<=10; j++) {
                num1 = i;
                num2 = j;
                if((4*i)+(5*j)==60) {
                    System.out.println("("+num1+", "+num2+")");
                }
            }
        }
    }
}
// --> (5, 8)
// --> (10, 4)
```

```JAVA
public class Excercise06 {
    public static void main(String[] args) {
        for(int i=1; i<=5; i++) {
            for(int j=1; j<=i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

```JAVA
import java.util.Scanner;

public class Excercise07 {
    public static void main(String[] args) {
        boolean run = true;

        int balance = 0;

        Scanner scanner = new Scanner(System.in);

        while(run) {
            System.out.println("--------------------------------------");
            System.out.println("1. 예금 | 2. 출금 | 3. 잔고 | 4. 종료");
            System.out.println("--------------------------------------");
            System.out.println("선택 > ");

            int num = scanner.nextInt();
            int money = 0;

            if(num == 1) {
                System.out.print("예금액 > ");
                money = scanner.nextInt();
                balance += money;
            } else if (num == 2) {
                System.out.print("출금액 > ");
                money = scanner.nextInt();
                balance -= money;
            } else if (num == 3) {
                System.out.print("잔고 > "+balance);
            } else {
                run = false;
            }
        }

        System.out.println("프로그램 종료");
    }
}
```
