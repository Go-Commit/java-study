#### 1. 중복된 숫자 개수 (https://school.programmers.co.kr/learn/courses/30/lessons/120583)
```
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

// array_len은 배열 array의 길이입니다.
int solution(int array[], size_t array_len, int n) {
    int answer = 0;
    
    for(int i=0; i<array_len; i++) {
        if(n == array[i]) {
            answer++;
        }
    }
    return answer;
}
```

#### 2. 머쓱이보다 키 큰 사람 (https://school.programmers.co.kr/learn/courses/30/lessons/120585)
```
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

// array_len은 배열 array의 길이입니다.
int solution(int array[], size_t array_len, int height) {
    int answer = 0;
    
    for(int i=0; i<array_len; i++) {
        if(array[i] > height) {
            answer++;
        }
    }
    
    return answer;
}
```

#### 3. 두 수의 합 (https://school.programmers.co.kr/learn/courses/30/lessons/120802)
```
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int num1, int num2) {
    int answer = num1 + num2;
    
    return answer;
}
```

#### 4. 두 수의 차 (https://school.programmers.co.kr/learn/courses/30/lessons/120803)
```
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int num1, int num2) {
    int answer = num1 - num2;
    return answer;
}
```

#### 5. 두 수의 곱 (https://school.programmers.co.kr/learn/courses/30/lessons/120804)
```
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int num1, int num2) {
    int answer = num1 * num2;
    return answer;
}
```

#### 6. 몫 구하기 (https://school.programmers.co.kr/learn/courses/30/lessons/120805)
```
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int num1, int num2) {
    int answer = num1 / num2;
    return answer;
}
```

#### 7. 두 수의 나눗셈 (https://school.programmers.co.kr/learn/courses/30/lessons/120806)
```
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int num1, int num2) {
    int answer = (double) num1 / (double) num2 * 1000;
    
    return answer;
}
```

#### 8. 숫자 비교하기 (https://school.programmers.co.kr/learn/courses/30/lessons/120807)
```
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int num1, int num2) {
    int answer = 0;
    
    if(num1 == num2) {
        answer = 1;
    }
    else {
        answer = -1;
    }
    
    return answer;
}
```

#### 9. 분수의 덧셈 (https://school.programmers.co.kr/learn/courses/30/lessons/120808)
```
class Solution {
    public int[] solution(int denum1, int num1, int denum2, int num2) {
        int[] answer = new int [2];
        
        // 분모의 최소공배수 구해준다.
        int denominator = lcm(num1, num2);
        // 분모에 따른 분자의 합 구해준다.
        int numerator = (denum1 * (denominator / num1)) + (denum2 * (denominator / num2));
        
        // 나온 결과값이 기약분수가 되도록 분모와 분자의 최대공약수 구해준다.
        int fraction_gcd = gcd(denominator, numerator);
        
        answer[0] = numerator / fraction_gcd;
        answer[1] = denominator / fraction_gcd;
        
        return answer;
    }
    
    // 최대공약수 (유클리드 호제법: 2개의 자연수 또는 정식의 최대공약수를 구하는 알고리즘)
    // "2개의 자연수 a, b(a > b)에 대해서 a를 b로 나눈 나머지가 r일 때, a와 b의 최대공약수는 b와 r의 최대공약수와 같다."
    public int gcd(int num1, int num2) {
        int greater = 0;
        int less = 0;
        
        if(num1 > num2) {
            greater = num1;
            less = num2;
        }
        else {
            greater = num2;
            less = num1;
        }
        
        // 큰 수를 작은 숫자로 나눈 나머지
        int remainder = greater % less;
        
        // 나머지가 0이면 작은 숫자가 최대공약수
        if(remainder == 0) {
            return less;
        }
        // 나머지가 0 이상이면 재귀형태로 호출
        else {
            return gcd(less, remainder);
        }
    }
    
    // 최소공배수
    // 두 수 a와 b의 최소공배수는 a와 b의 곱을 a와 b의 최대공약수를 나눈 것과 같다. 
    public int lcm(int num1, int num2) {
        return (num1 * num2) / gcd(num1, num2);
    }
}
```

#### 10. 배열 두 배 만들기 (https://school.programmers.co.kr/learn/courses/30/lessons/120809)
```
class Solution {
    public int[] solution(int[] numbers) {
        int[] answer = new int [numbers.length];
        
        for(int i=0; i<numbers.length; i++) {
            answer[i] = numbers[i] * 2;
        }
        
        return answer;
    }
}
```
