#### 1. 조건문과 반복문의 종류
* 조건문: if, switch
* 반복문: for, while, do-while

#### 2. 조건문과 반복문을 설명한 것 중 틀린 것은?
* 2 >> switch문에서 사용하는 변수타입은 정수 타입 뿐만 아니라 String 타입도 가능하다.

#### 3. for문 이용, 1부터 100까지의 정수 중에서 3의 배수의 총합을 구하는 코드
```
public static void main(String[] args) {
    int sum = 0;
    for(int i=0; i<100; i++) {
        int numb = i + 1;
        
        if(numb % 3 == 0) {
            sum += numb;
        }
    }
    System.out.println(sum);
}
```

#### 4. while문과 Math.random() 메소드를 이용해 두 개의 주사위를 던졌을 떄 나오는 눈을 (눈1, 눈2) 형태로 출력하고, 눈의 합이 5가 아니면 계속 주사위를 던지고, 눈의 합이 5이면 실행을 멈추는 코드 작성
```
public static void main(String[] args) {
    int x = 0;
    int y = 0;
    
    while(x+y != 5) {
        x = (int) (Math.random() * 6) + 1;
        y = (int) (Math.random() * 6) + 1;
        System.out.println("("+x+", "+y+")");
    }
}
```

#### 5. 중첩 for문 사용, 4x + 5y = 60의 모든 해를 구해서 (x, y) 형태로 출력 (x와 y는 10 이하의 자연수)
```
public static void main(String[] args) {
    for(int x=1; x<=10; x++) {
        for(int y=1; y<=10; y++) {
            if((4*x) + (5*y) == 60) {
                System.out.println("("+x+", "+y+")");
            }
        }
    }
}
```

#### 6. for문 이용해 삼각형 출력
```
public static void main(String[] args) {
    for(int i=1; i<=5; i++) {
        for(int j=1; j<=i; j++) {
            System.out.print("*");
        }
        System.out.println("");
    }
}
```

#### 7. while문과 Scanner를 이용해 키보드로부터 입력된 데이터로 예금, 출금, 조회, 종료 기능을 제공하는 코드 작성
```
public static void main(String[] args) {
    boolean run = true;
    int money = 0;
    
    Scanner scanner = new Scanner(System.in);
    
    while(run) {
        System.out.println("1. 예금 | 2. 출금 | 3. 잔고 | 4. 종료");
        System.out.print("선택> ");
        
        int selNum = scanner.nextInt();
        
        if(selNum == 1) {
            System.out.print("예금액> ");
            money += scanner.nextInt();
            System.out.println();
        } 
        else if(selNum == 2) {
            System.out.print("출금액> ");
            money -= scanner.nextInt();
            System.out.println();
        }
        else if(selNum == 3) {
            System.out.println("잔고> "+money);
            System.out.println();
        }
        else if(selNum == 4) {
            System.out.println("프로그램 종료");
            run = false;
        }
    }
}
```
