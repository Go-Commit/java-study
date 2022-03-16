
# 연산자 (Operator)
<br>

```JAVA
public class Excercise02 {
    public static void main(String[] args) {
        int x = 10;
        int y = 20;
        int z = (++x) + (y--);
        System.out.println(z);
    }
}
// --> 31
```

```JAVA
public class Excercise03 {
    public static void main(String[] args) {
        int score = 85;
        String result = (!(score>90)) ? "가":"나";
        System.out.println(result);
    }
}
// --> 가
```

```JAVA
public class Excercise04 {
    public static void main(String[] args) {
        int pencils = 534;
        int students = 30;
        
        // 학생 한 명이 가지는 연필 수
        int pencilsPerStudent = pencils/students;
        System.out.println(pencilsPerStudent);
        
        // 남은 연필 수
        int pencilsLeft = pencils%students;
        System.out.println(pencilsLeft);
    }
}
// --> 17
// --> 24
```

```JAVA
public class Excercise05 {
    public static void main(String[] args) {
        int value = 356;
        System.out.println((value / 10) * 10);
    }
}
// --> 350
```

```JAVA
public class Excercise06 {
    public static void main(String[] args) {
        int lengthTop = 5;
        int lengthBottom = 10;
        int height = 7;
        double area = ( (lengthTop + lengthBottom) * height / 2 );
        System.out.println(area);
    }
}
// --> 52.0
```

```JAVA
public class Excercise07 {
    public static void main(String[] args) {
        int x = 10;
        int y = 5;
        
        System.out.println( (x>7) && (y<=5) );
        System.out.println( (x%3 == 2) || (y%2 != 1) );
    }
}
// --> ture
// --> false
```

```JAVA
public class Excercise08 {
    public static void main(String[] args) {
        double x = 5.0;
        double y = 0.0;
        
        double z = x%y;
        
        if( Double.isInfinite(z) || Double.isNaN(z) ) // NaN 값 검사
        {
            System.out.println("0.0으로 나눌 수 없습니다.");
        }
        else
        {
            double result = z + 10;
            System.out.println("결과: "+result);
        }
    }
}
//--> 0.0으로 나눌 수 없습니다.
```
