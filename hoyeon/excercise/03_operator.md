#### 1. 연산자와 연산식에 대한 설명 중 틀린 것은?
* 3 >> 연산자는 하나의 값만 산출한다.  

#### 2. 출력 결과
```
public static void main(String[] args) {
    int x = 10;
    int y = 20;
    int z = (++x) + (y--);
    System.out.println(z);
}
```
* 31 >> 11 + 20

#### 3. 출력 결과
```
public static void main(String[] args) {
    int score = 85;
    String result = (!(score>90))?"가":"나";
    System.out.println(result);
}
```
* 가 >> 85는 90보다 크지 않은 것이 맞으므로 "가"

#### 4. 534자루의 연필을 30명의 학생들에게 똑같은 개수로 나누었을 떄 몫과 나머지
```
public static void main(String[] args) {
    int pencils = 352;
    int students = 30;

    int pencilsPerStudent = ( pencils / students );
    System.out.println(pencilsPerStudent);

    int pencilsLeft = ( pencils % students );
    System.out.println(pencilsLeft);        
}
```

#### 5. 십의 자리 이하를 버리는 코드
```
public static void main(String[] args) {
    int value = 356;
    System.out.println( value - value % 100 );
}
```

#### 6. 사다리꼴 넓이 구하기 (소수점 출력)
```
public static void main(String[] args) {
    int lengthTop = 5;
    int lengthBottom = 10;
    int height = 7;
    double area = ( (double)(lengthTop + lengthBottom) * height / 2 );
    System.out.println(area);
}
```

#### 7. 연산식 출력 결과
```
public static void main(String[] args) {
    int x = 10;
    int y = 5;

    System.out.println( (x>7) && (y<=5) );
    System.out.println( (x%3 == 2) || (y%2 != 1) );
}
```
* true >> 10>7 && 5=5
* false >> 10%3 == 1 && 5%2 == 1

#### 8. % 연산을 수행한 결과값에 10을 더하는 코드, NaN 값 검사
```
public static void main(String[] args) {
    double x = 5.0;
    double y = 0.0;
    
    double z = x % y;
    
    if( Double.isNaN(z) ) {
        System.out.println("0.0으로 나눌 수 없습니다.");
    } else {
        double result = z + 10;
        System.out.println("결과 : " + result);
    }
}
```
