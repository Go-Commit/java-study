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

6.개미 군단
https://school.programmers.co.kr/learn/courses/30/lessons/120837
```
class Solution {
    public int solution(int hp) {
        int answer = 0;
        while (hp >= 0) {

            if (hp >= 5) {
                hp -= 5;
                answer++;
            } else if (hp >= 3) {
                hp -= 3;
                answer++;
            } else if (hp >= 1) {
                hp -= 1;
                answer++;
            } else if (hp == 0) {
                break;
            }
        }
        
        return answer;
    }
}
```

7.모스부호 (1)
https://school.programmers.co.kr/learn/courses/30/lessons/120838

```
import java.util.HashMap;
class Solution {
    public String solution(String letter) {
        String answer = "";
        HashMap <String, String> map = new HashMap<>();
        map.put(".-","a");
        map.put("-...", "b"); map.put("-.-.","c");map.put("-..","d");
        map.put(".","e");map.put("..-.","f");map.put("--.","g");
        map.put("....","h");map.put("..","i");map.put(".---","j");map.put("-.-","k");
        map.put(".-..","l");map.put("--","m");
        map.put("-.","n");map.put("---","o");map.put(".--.","p");
        map.put("--.-","q");map.put(".-.","r");
        map.put("...","s");map.put("-","t");map.put("..-","u");map.put("...-","v");
        map.put(".--","w");
        map.put("-..-","x");map.put("-.--","y");map.put("--..","z");

        String[] letterArr = letter.split(" ");
        for (String arr : letterArr) {
            answer += map.get(arr);
        }
        return answer;
    }
}
```

8. 가위바위보
https://school.programmers.co.kr/learn/courses/30/lessons/120839
```
class Solution {
    public String solution(String rsp) {
        String answer = "";
        for (int i = 0; i < rsp.length(); i++) {
            if (rsp.charAt(i) == '5') answer += '2'; 
            else if (rsp.charAt(i) == '2') answer += '0';
            else if (rsp.charAt(i) == '0') answer += '5';
        }    
        return answer;
    }
}
```

9.

```
```

10.

```
```






