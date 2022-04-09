#### 실습 1-1. 3개의 정숫값을 입력하고 최댓값 구하기
```
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("a의 값 : ");
    int a = stdIn.nextInt();
    System.out.print("b의 값 : ");
    int b = stdIn.nextInt();
    System.out.print("c의 값 : ");
    int c = stdIn.nextInt();
    
    int max = a;
    if(max < b)    max = b;
    if(max < c)    max = c;
    
    System.out.println(max);
}
```

#### 실습 1-2. 3개의 정숫값 가운데 최댓값 구하여 출력
```
static int max3(int a, int b, int c) {
    int max = a;
    if(max < b)    max = b;
    if(max < c)    max = c;
    
    return max;
}

public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("a의 값 : ");
    int a = stdIn.nextInt();
    System.out.print("b의 값 : ");
    int b = stdIn.nextInt();
    System.out.print("c의 값 : ");
    int c = stdIn.nextInt();
    
    int max = max3(a, b, c);
    
    System.out.println(max);
}
```

#### 연습 1. 네 값의 최댓값을 구하는 max4 메서드 작성
````
static int max4(int a, int b, int c, int d) {
    int max = a;
    if(max < b)    max = b;
    if(max < c)    max = c;
    if(max < d)    max = d;
    
    return max;
}
````

#### 연습 2. 세 값의 최솟값을 구하는 min3 메서드 작성
````
static int min3(int a, int b, int c) {
    int min = a;
    if(min > b)    min = b;
    if(min > c)    min = c;
    
    return min;
}
````

#### 연습 3. 네 값의 최솟값을 구하는 min4 메서드 작성
````
static int min4(int a, int b, int c, int d) {
    int min = a;
    if(min > b)    min = b;
    if(min > c)    min = c;
    if(min > d)    min = d;
    
    return min;
}
````

#### 실습 1C-1. 3개의 정숫값을 입력하고 중앙값을 구한 다음 출력
```
static int mid3(int a, int b, int c) {
    
    if(a >= b) {
        if(b >= c)    return b;
        else if(a <= c)    return a;
        else    return c;
    }
    else if(a > c)    return a;
    else if(b > c)    return c;
    else    return b;
    
}

public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("a의 값 : ");
    int a = stdIn.nextInt();
    System.out.print("b의 값 : ");
    int b = stdIn.nextInt();
    System.out.print("c의 값 : ");
    int c = stdIn.nextInt();
    
    int mid = mid3(a, b, c);
    
    System.out.println(mid);
}
```

#### 연습 4. 세 값의 대소 관계 13종류의 모든 조합에 대해 중앙값을 구해 출력
```
static int mid3(int a, int b, int c) {
    
    if(a >= b) {
        if(b >= c)    return b;
        else if(a <= c)    return a;
        else    return c;
    }
    else if(a > c)    return a;
    else if(b > c)    return c;
    else    return b;
    
}
```

#### 연습 5. 중앙값을 구하는 메서드는 다음과 같이 작성할 수도 있지만, 실습 1C-1의 med3 메서드에 비해 효율이 떨어지는 이유는?
```
static int mid3(int a, int b, int c) {
    if( (b>=a && c<=a) || (b>=a && c<=a) )
      return a;
    else if( (a>b && c<b) || (a>b && c<b) )
      return b;
    return c;
}
```
* if 안에 중첩된 조건이 들어가 있어서 효율이 떨어진다

#### 실습 1-3. 입력한 정숫값이 양수인지 음수인지 0인지 판단한다.
````
public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);
    
    System.out.print("정수 : ");
    int n = stdIn.nextInt();
    
    if(n > 0)
        System.out.print("양수");
    else if(n < 0)
        System.out.print("음수");
    else
        System.out.print("0");
}
````
