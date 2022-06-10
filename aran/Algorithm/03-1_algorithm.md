# ALGORITHM

### Q1.실습 3-3의 seqSearchSen 메서드를 while문이 아니라 for문으로 바꿔라
```java
static int seqSearchSen(int[] a, int n , int key ) {
    a[n] = key;
    for(int i = 0; i<a.length; i++) {
        if(a[i] == key) {
            return i;
        }
    }
    return -1;
}
```

### Q2.검색 스캐닝 과정을 상세하게 출력하는 프로그램을 작성해라 (2번 잘모르겠음 ㅠㅠ)
```java
```
