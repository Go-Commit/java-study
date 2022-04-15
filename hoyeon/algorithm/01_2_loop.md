#### 실습 1-4. 1부터 n까지의 정수 합 구하기
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("n의 값 : ");
    int n = stdIn.nextInt();
    
    int sum = 0;
    int i=1;
    
    while(i<=n) {
        sum += i;
        i++;
    }
    System.out.println(sum);
}
```

#### Q6. 실습 1-4에서 while문이 종료될 떄 변수 i의 값이 n+1이 됨을 확인 
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("n의 값 : ");
    int n = stdIn.nextInt();
    
    int sum = 0;
    int i=1;
    
    while(i<=n) {
        sum += i;
        i++;
    }
    System.out.println(i);
}
```

#### 실습 1-5. 1부터 n까지 정수의 합을 for문으로 구하기
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("n의 값 : ");
    int n = stdIn.nextInt();
    
    int sum = 0;
    
    for(int i=1; i<=n; i++) {
        sum+=i;
    }
    System.out.println(sum);
}
```

#### Q7. n이 3이면 '1+2+3=6'으로 출력하는 프로그램 작성
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("n의 값 : ");
    int n = stdIn.nextInt();
    
    int sum = 0;
    String result = "";
    
    for(int i=1; i<=n; i++) {
        sum+=i;
        if(i != n)
            result += i + "+";
        else
            result += i + "=" + sum;
    }
    System.out.println(result);
}
```

#### Q8. 가우스의 덧셈으로 1~n 합 구하기
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("n의 값 : ");
    int n = stdIn.nextInt();
    
    int sum = (1+n)*n/2;
    System.out.println(sum);
}
```

#### Q9. 정수 a, b를 포함하여 그 사이의 모든 정수의 합을 구하여 반환하는 메서드 작성
```
static int sumof(int a, int b) {
    int cnt = Math.abs(b-a) + 1;
    int sum = (a+b)*cnt/2;
    
    return sum;
}
```

#### 실습 1-6. 양수만 입력하기
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    int n;
    
    do {
        System.out.print("n : ");
        n = stdIn.nextInt();
    } while (n <= 0);
    
    int sum = 0;
    
    for(int i=1; i<=n; i++) {
        sum += i;
    }
    
    System.out.println(sum);
}
```

#### Q10. b-a 출력
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    int x, y;
    
    do {
        System.out.print("a의 값 : ");
        x = stdIn.nextInt();        
    }while(x <= 0);
    
    do {
        System.out.print("b의 값 : ");
        y = stdIn.nextInt();
    
        if(x>=y) {
            System.out.println("a보다 큰 값 입력");
        }
    }while(y <= 0);  
   
    System.out.println(y-x);
}
```

#### Q11. 양의 정수를 입력하고 자릿수를 출력
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    int n;
    
    do {
        System.out.print("n의 값 : ");
        n = stdIn.nextInt();      
    }while(n <= 0);
    
    int cnt = 1;
    do {
        n = n / 10;
        cnt++;
    }while(n >= 10);
   
    System.out.println(cnt);
}
```

#### 1C-2. 입력한 값을 2자리 양수로 제한
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    int n;
    
    System.out.println("2자리 정수 입력");
    
    do {
        System.out.print("입력 : ");
        n = stdIn.nextInt();      
    }while(n < 10 || n > 99);
   
    System.out.println(n);
}
```

#### 실습 1-7. 곱셈표 출력
```
public static void main(String[] args) {
    for(int i=1; i<=9; i++) {
        for(int j=1; j<=9; j++) {
            System.out.printf("%3d", i*j);
        }
        System.out.println("");
    }
}
```

#### Q12. 위쪽과 왼쪾에 곱하는 수가 있는 곱셈표 출력
```
public static void main(String[] args) {
    for(int i=1; i<=9; i++) {
        if(i==1) {
            System.out.print("   |");
            for(int x=1; x<=9; x++) {
                System.out.printf("%3d", x);
            }
            System.out.println("");
            System.out.println("---+----------------------------");
        }
        System.out.printf("%3d", i);
        System.out.print("|");
        for(int j=1; j<=9; j++) {
            System.out.printf("%3d", i*j);
        }
        System.out.println("");
    }
}
```

#### Q13. 곱셈이 아니라 덧셈을 출력
```
public static void main(String[] args) {
    for(int i=1; i<=9; i++) {
        if(i==1) {
            System.out.print("   |");
            for(int x=1; x<=9; x++) {
                System.out.printf("%3d", x);
            }
            System.out.println("");
            System.out.println("---+----------------------------");
        }
        System.out.printf("%3d", i);
        System.out.print("|");
        for(int j=1; j<=9; j++) {
            System.out.printf("%3d", i+j);
        }
        System.out.println("");
    }
}
```

#### Q14. 입력한 수를 한 변으로 하는 정사각형을 * 기호로 출력
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    System.out.print("입력 : ");
    int n = stdIn.nextInt();
    
    for(int i=0; i<n; i++) {
        for(int j=0; j<n; j++) {
            System.out.print("*");
        }
        System.out.println("");
    }
}
```

#### 실습 1-8. 직각 이등변 삼각형 출력
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    int n;
    
    do {
        System.out.print("입력 : ");
        n = stdIn.nextInt();
    } while(n <= 0);
    
    for(int i=1; i<=n; i++) {
        for(int j=1; j<=i; j++) {
            System.out.print("*");
        }
        System.out.println();
    }
}
```

#### Q15. 왼쪽 아래가 직각인 이등변 삼각형 출력
```
static void triangleLB(int n) {
    
    for(int i=1; i<=n; i++) {
        for(int j=1; j<=i; j++) {
            System.out.print("*");
        }
        System.out.println();
    }
}
```
