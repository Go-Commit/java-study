### 프로그래머스###
# level_0 #

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

4.

```
```

5.

```
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






