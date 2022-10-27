### level 0 ###
  
  1. 정수 num1과 num2가 매개변수로 주어집니다. 두 수가 같으면 1 다르면 -1을 retrun하도록 solution 함수를 완성해주세요.
  ```
  class Solution {
    public int solution(int num1, int num2) {
        if(num1 == num2)return 1;            
        else return -1;
    }
}
```

2.정수 num1, num2가 매개변수 주어집니다. num1과 num2를 곱한 값을 return 하도록 solution 함수를 완성해주세요.
```
class Solution {
    public int solution(int num1, int num2) {
        return num1*num2;
    }
}
```

3.정수 num1과 num2가 주어질 때, num1에서 num2를 뺀 값을 return하도록 soltuion 함수를 완성해주세요.
```
class Solution {
    public int solution(int num1, int num2) {
        return num1-num2;
    }
}
```
4.정수 num1과 num2가 주어질 때, num1과 num2의 합을 return하도록 soltuion 함수를 완성해주세요.
```
class Solution {
    public int solution(int num1, int num2) {
    return num1+num2;
    }
}
```
5.정수 num1, num2가 매개변수로 주어질 때, num1을 num2로 나눈 몫을 return 하도록 solution 함수를 완성해주세요.
```
class Solution {
    public int solution(int num1, int num2) {
    return num1/num2;
    }
}
```

6.머쓱이는 40살인 선생님이 몇 년도에 태어났는지 궁금해졌습니다. 나이 age가 주어질 때, 2022년을 기준 출생 연도를 return 하는 solution 함수를 완성해주세요.
```
class Solution {
    public int solution(int age) {        
        int year=2022;
        int born = year-age;
        return born+=1;
        
    }
}
```

7. 나머지값 구하기
```
class Solution {
    public int solution(int num1, int num2) {
    return num1%num2;
    }
}
```

8.각에서 0도 초과 90도 미만은 예각, 90도는 직각, 90도 초과 180도 미만은 둔각 180도는 평각으로 분류합니다. 각 angle이 매개변수로 주어질 때 예각일 때 1, 직각일 때 2, 둔각일 때 3, 평각일 때 4를 return하도록 solution 함수를 완성해주세요.
```
class Solution {
    public int solution(int angle) {
        if(0 < angle && angle < 90) return 1;
        else if(angle == 90) return 2;
        else if(90 < angle && angle < 180) return 3;
        else return 4;
    }
}
```

9.정수 num1과 num2가 매개변수로 주어질 때, num1을 num2로 나눈 값에 1,000을 곱한 후 정수 부분을 return 하도록 soltuion 함수를 완성해주세요.
```
class Solution {
    public int solution(int num1, int num2) {
        double ans = (double)num1/num2;
        ans*=1000;
        return (int)ans;
    }
}
```

10.정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소의 평균값을 return하도록 solution 함수를 완성해주세요.
```
class Solution {
    public double solution(int[] numbers) {
        double num = 0;
        int j =0;
        for(int i=0; i< numbers.length; i++)
        {
            num +=numbers[i];
            j++;
        }        
        num/=j;
        return num;
    }
}
```












