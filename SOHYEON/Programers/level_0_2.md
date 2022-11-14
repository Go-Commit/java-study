#### 코딩테스트 연습
### 코딩테스트 입문


1. 배열 두 배 만들기
https://school.programmers.co.kr/learn/courses/30/lessons/120809

```
class Solution {
    public int[] solution(int[] numbers) {
        for(int i=0;i<numbers.length;i++)
        {numbers[i] = numbers[i]*2;}
    return numbers;
    }
}
```

2. 짝수는-싫어요
https://school.programmers.co.kr/learn/courses/30/lessons/120813
```
class Solution {
    public int[] solution(int n) {
        int[] answer;
        int k=0;
        if(n%2==0) 
            answer = new int[n/2];
        else 
            answer = new int[n/2+1];
        
        for(int i=0;i<=n;i++)
        { 
            if(i%2 == 1) {answer[k]=i;k++;}          
        }
        return answer;     
    }       
}

```


3.피자 나눠 먹기 (2) 

https://school.programmers.co.kr/learn/courses/30/lessons/120815
```
class Solution {
    public int solution(int n) {
        int m = n;
        int ans = 0;
        while (n != 0) {
            if (n % 6 == 0) {ans = n / 6;break;}
            n += m;
        }
        return ans;
    }
}    

```


4. 중앙값 구하기

https://school.programmers.co.kr/learn/courses/30/lessons/120811
```
import java.util.Arrays;
class Solution {
    public int solution(int[] array) {
        int answer = 0;
        int ans=(array.length/2);
        Arrays.sort(array);
        for (int i : array) {}
        return array[ans];        
    }
}
```


5.옷가게 할인 받기
https://school.programmers.co.kr/learn/courses/30/lessons/120818

```
class Solution {
    public int solution(int price) {
        if (price >= 500000) {
            double d = 0.8; 
            return price = (int) (Double.valueOf(price) * d);
        }         
        else if (price >= 300000) {
            double d = 0.9; 
            return price = (int) (Double.valueOf(price) * d);
        }        
        else if (price >= 100000) {
            double d = 0.95; 
            return price = (int) (Double.valueOf(price) * d);
        } 
        else
            return price;
    }
}
```


6.배열 뒤집기
https://school.programmers.co.kr/learn/courses/30/lessons/120821

```

```


7.직각삼각형 출력하기
https://school.programmers.co.kr/learn/courses/30/lessons/120823

```
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        for (int i = 1; i <= n; i++) {
            for (int j = 0; j < i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```


8.문자 반복 출력하기
https://school.programmers.co.kr/learn/courses/30/lessons/120825

```
public String solution(String my_string, int n) {
        String ans="";
        int su = my_string.length();
        String[] arr = new String[su];
        arr = my_string.split("");
        for (int i = 0; i < su; i++) {
            for (int j = n; j <= n - 1; j++) {
                // System.out.print(arr[i]);
                ans =arr[i];
            }          
        }
        return ans;
    }

```


9.배열 자르기

https://school.programmers.co.kr/learn/courses/30/lessons/120833
```

```


.


```

```
