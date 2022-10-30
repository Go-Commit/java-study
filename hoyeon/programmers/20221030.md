#### 11. 나머지 구하기 (https://school.programmers.co.kr/learn/courses/30/lessons/120810)
```
class Solution {
    public int solution(int num1, int num2) {
        int answer = num1 % num2;
        return answer;
    }
}
```

#### 12. 중앙값 구하기 (https://school.programmers.co.kr/learn/courses/30/lessons/120811)
```
import java.util.*;

class Solution {
    public int solution(int[] array) {
        int answer = 0;
        
        Arrays.sort(array);
        int len = array.length;
        int midCnt = len / 2;
        
        answer = array[midCnt];
        
        return answer;
    }
}
```

#### 13. 최빈값 구하기 (https://school.programmers.co.kr/learn/courses/30/lessons/120812)
```

```

#### 14. 짝수는 싫어요 (https://school.programmers.co.kr/learn/courses/30/lessons/120813)
```
class Solution {
    public int[] solution(int n) {
        int num = (n + 1) / 2;
        int[] answer = new int[num];
        
        int j = 0;
        for(int i=0; i<n; i++) {
            if((i+1)%2 == 1) {
                answer[j] = (i+1);
                j++;
            }
        }
        return answer;
    }
}
```

#### 15. 피자 나눠 먹기 (1) (https://school.programmers.co.kr/learn/courses/30/lessons/120814)
```
class Solution {
    public int solution(int n) {
        int answer = n / 7;
        
        if((n%7) > 0) {
            answer++;
        }
        
        return answer;
    }
}
```

#### 16. 피자 나눠 먹기 (2) (https://school.programmers.co.kr/learn/courses/30/lessons/120815)
```
class Solution {
    public int solution(int n) {
        
        int remainder = 1;
        int cnt = 0;
        while(remainder != 0) {
            remainder = ((cnt+1) * 6) % n;
            cnt++;
        }
        
        return cnt;
    }
}
```

#### 17. 피자 나눠 먹기 (3) (https://school.programmers.co.kr/learn/courses/30/lessons/120816)
```
class Solution {
    public int solution(int slice, int n) {
        int answer = n / slice;
        
        if((n%slice) > 0) {
            answer++;
        }
        
        return answer;
    }
}
```

#### 18. 배열의 평균값 (https://school.programmers.co.kr/learn/courses/30/lessons/120817)
```
class Solution {
    public double solution(int[] numbers) {
        double answer = 0;
        int len = numbers.length;
        
        for(int i=0; i<len; i++) {
            answer += (double)numbers[i];
        }
        
        answer = answer / len;
        
        return answer;
    }
}
```

#### 19. 옷가게 할인 받기 (https://school.programmers.co.kr/learn/courses/30/lessons/120818)
```
class Solution {
    public int solution(int price) {
        int answer = 0;
        
        if(price >= 500000) {
            answer = (int)(price * 0.8);
        }
        else if(price >= 300000) {
            answer = (int)(price * 0.9);
        }
        else if(price >= 100000) {
            answer = (int)(price * 0.95);
        }
        else {
            answer = price;
        }
        
        return answer;
    }
}
```

#### 20. 아이스 아메리카노 (https://school.programmers.co.kr/learn/courses/30/lessons/120819)
```
class Solution {
    public int[] solution(int money) {
        int[] answer = new int[2];
        
        answer[0] = money / 5500;
        answer[1] = money % 5500;
        
        return answer;
    }
}
```
