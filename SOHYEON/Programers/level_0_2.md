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


.


```

```


.


```

```


.


```

```


.


```

```


.


```

```
