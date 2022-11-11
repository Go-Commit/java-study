
### level_0_1 ###
## 프로그래머스 ##



1.짝수의 합
```
int solution(int n) {
    int answer = 0;
    for(int i=0;i<=n;i++)
    {if(i%2 == 0) answer += i;}
     return answer;
}
```

2.중복된 숫자 개수
```
int solution(vector<int> array, int n) {
  int ans= 0;
    for(int i=0;i<vector.length;i++)
    { if(vector[i]==n) ans+=1; }
    return ans;
}
```


3.두 수의 나눗셈
```
class Solution {
    public int solution(int num1, int num2) {
        double ans = (double)num1/num2;
        ans*=1000;
        return (int)ans;
    }
}
```


4.머쓱이보다 키 큰 사람
https://school.programmers.co.kr/learn/courses/30/lessons/120585
```
class Solution {
    public int solution(int[] array, int height) {
        int answer = 0;
        for(int i=0;i<array.length;i++)
        { if(array[i] >height) answer++;}
        return answer;
    }
}
```


5.양꼬치
https://school.programmers.co.kr/learn/courses/30/lessons/120830
```
class Solution {
    public int solution(int n, int k) {
        int ans = 0;
        ans= n/10;        
        if(ans > 0) k-=ans;
        return ans=(n*12000)+(k*2000);
    }
}
```


6.편지
https://school.programmers.co.kr/learn/courses/30/lessons/120898
```
class Solution {
    public int solution(String message) {
        int answer = message.length();
        return answer*2;
    }
}
```


7.짝수 홀수 개수
https://school.programmers.co.kr/learn/courses/30/lessons/120824
```
class Solution {
    public int[] solution(int[] num_list) {
        int[] ans;
        ans = new int[2];        
        for(int i=0; i<num_list.length; i++)
        {if(num_list[i]%2==0)ans[0]++;
        else if(num_list[i]%2==1)ans[1]++;}    
        return ans;
    }
}
```


8.피자 나눠 먹기 (3)
https://school.programmers.co.kr/learn/courses/30/lessons/120816
```
class Solution {
    public int solution(int slice, int n) {
        int ans=0;
        while(n>0)
        {
            n-=slice;
            ans++;
            if(n<slice&&n>0){ans++;break;}
        }
        return ans;
    }
}
```


9.아이스 아메리카노
https://school.programmers.co.kr/learn/courses/30/lessons/120819
```
class Solution {
    public int[] solution(int money) {
        int[] ans = new int[2];
        while(money>=0)
        {
            if(money<5500){ans[1]=money; break;} 
            money-=5500;ans[0]++;
        }
        return ans;
    }
}
```


10.피자 나눠 먹기 (1)
https://school.programmers.co.kr/learn/courses/30/lessons/120814
```
class Solution {
    public int solution(int n) {
        int ans = 0;
        while(n>=0)
        {            
            if(n<=7){ans++; break;}
            n-=7;ans++;
        }
        return ans;
    }
}
```







