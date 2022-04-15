# 이것이자바다 5장 연습문제

## 1.참조 타입에 대한 설명으로 틀린 것은 무엇입니까?  
#### ㅁANSWER 4번 참조 타입은 null 값으로 초기화할 수 없다. -> null 값으로 초기화가 가능하다.

## 2.자바에서 메모리 사용에 대한 설명으로 틀린 것은 무엇입니까?  
#### ㅁANSWER 3.참조되지 않은 객체는 프로그램에서 직접 소멸 코드를 작성하는 것이 좋다. -> 참조 변수에 값이 없다면 가비지 콜렉터가 자동으로 정리해준다.

## 3. String 타입에 대한 설명으로 틀린 것은 무엇입니까?  
#### ㅁANSWER 2.String 타입의 문자열 비교는 ==를 사용해야한다. -> 문자열은 equals 함수를 이용해서 비교한다.

## 4. 배열을 생성하는 방법으로 틀린 것은 무엇입니까?  
#### ㅁANSWER 2번 int[] array; array = {1,2,3};

## 5. 배열의 기본 초기값에 대한 설명으로 틀린 것은 무엇입니까?  
#### ㅁANSWER 3번 boolean 타입 배열 항목의 초기값은 true이다. -> boolean 초기값은 false이다.

## 6. 배열의 길이에 대한 문제입니다. array.length의 값과 array[2].length의 값은 얼마입니까?
```java
int[][] array = {
    {95,86},
    {83,92,96},
    {78,83,93,87,88}
}

array.length -> (3), array[2].length -> (5)
```

## 7. 주어진 배열의 항목에서 최대값을 구해보세요.
```java
public class Exercise07 {
    public static void main(String[]args) {
        int max = 0;
        int[] array = {1,5,3,8,2};

        // ANSWER
        for(int a : array) {
            if(a>max) {
                max = a;
            }
        }

        System.out.println("max:"+max);
    }
}
```


## 8. 주어진 배열의 전체 항목의 합과 평균값을 구해보세요.
```java
public class Exercise08 {
    public static void main(String[]args) {
        int[][] array = {
            {95,86},
            {83,92,96},
            {78,83,93,87,88},
        };

        int sum = 0;
        double avg = 0.0;

        for(int i=0; i<array.length; i++) {
            for(int j=0; j<array[i].length; j++) {
                sum+=array[i][j];
            }
        }

        avg = sum/10;

        System.out.println("SUM:"+sum);
        System.out.println("AVG:"+avg);
    }
}
```
## 9. 다음은 키보드로부터 학생 수와 각 학생들의 점수를 입력받아서 최고 점수 및 평균 점수를 구하는 프로그램입니다. 실행 결과를 보고 알맞게 작성해보세요.
```java
public class Exercise09 {
    public static void main(String[]args) {
        boolean run = true;
        int studentNum = 0;
        int[] scores = null;
        Scanner sc = new Scanner(System.in);

        while(run) {
            System.out.println("-------------------------------------------");
            System.out.println("1.학생수 | 2. 점수입력 | 3.점수리스트 | 4.분석 | 5.종료");
            System.out.println("-------------------------------------------");
            System.out.print("선택 > ");
            
            int selectNo = sc.nextInt();

            if(selectNo == 1) {
                System.out.print("학생수 > ");
                studentNum = sc.nextInt();
                scores = new int[studentNum];
            }else if(selectNo == 2) {
                for(int i = 0; i<studentNum; i++) {
                    System.out.print("scores["+i+"] > ");
                    scores[i] = sc.nextInt();
                }
            } else if(selectNo == 3) {
                for(int i = 0; i<studentNum; i++) {
                    System.out.println("scores["+i+"]:"+scores[i]);
                }
            }else if(selectNo == 4) {
                int sum = 0;
                int max = 0;
                for(int i = 0; i<studentNum; i++) {
                    sum+=scores[i];
                    if(scores[i]>max) {
                        max = scores[i];
                    }
                }
                System.out.println("최고점수 : "+max);
                System.out.println("평균점수 : "+(sum/(double)studentNum));
            }else if(selectNo == 5) {
                run = false;
            }
        }

        System.out.println("시스템종료");
    }
}
```