# 프로그래머스
#### level_0 

1.특정 문자 제거하기
https://school.programmers.co.kr/learn/courses/30/lessons/120826
```
class Solution {
    public String solution(String my_string, String letter) {
        String answer = my_string.replaceAll(letter, "");
        return answer;
    }
}
```

2. 문자 반복 출력하기
https://school.programmers.co.kr/learn/courses/30/lessons/120825
```
class Solution {
    public String solution(String my_string, int n) {
        String answer = "";
        char[] arr = my_string.toCharArray();
        for(int i=0; i<arr.length;i++)
        {
            for(int j=0; j<n;j++) answer+=arr[i];
        }
        return answer;
    }
}
```

3.문자열 뒤집기

https://school.programmers.co.kr/learn/courses/30/lessons/120822
```
class Solution {
    public String solution(String my_string) {
        String ans ="";
        char[] arr = my_string.toCharArray();
        for (int i = arr.length - 1, j = 0; i >= 0; i--, j++) {
            ans += arr[i];
        }
        return ans;

    }
}
```

4.배열 자르기
https://school.programmers.co.kr/learn/courses/30/lessons/120833

```
import java.util.Arrays;

class Solution {
    public int[] solution(int[] numbers, int num1, int num2) {
        int[] answer = {};
        answer = Arrays.copyOfRange(numbers, num1, num2+1);
        return answer;
    }
}
```

5.외계행성의 나이
https://school.programmers.co.kr/learn/courses/30/lessons/120834
```
import java.util.stream.Stream;
class Solution {
    public String solution(int age) {
        String answer = "";
        String arr[] = {"a","b","c","d","e","f","g","h","i","j"};
        int[] agenum = Stream.of(String.valueOf(age).split("")).mapToInt(Integer::parseInt).toArray();
        for (int i = 0; i < agenum.length; i++) {
            answer+=arr[agenum[i]];
        }
        return answer;
    }
}
```

6.

```
```

7.

```
```

8.

```
```

9.

```
```

10.

```
```






