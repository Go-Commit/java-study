# ALGORITHM

### Q8. 메서드 dayOfYear를 변수 i와 days 없이 구현하세요. while문을 사용하세요.
```java
static int dayOfYear(int y, int m, int d){
    while(m>=1){
        d+= mdays[isLeap(y)][m-1];
        m--;
    }
    return d;
}
```

### Q9. y년 m월 d일의 그해 남은 일수를 구하는 아래 메서드를 작성하세요.
```java
static int leftDayOfYear(int y, int m, int d){
	int total_day = 0;
	while(m>=1){
		d += mdays[isLeap(y)][m-1];
		m--;
	}

	return (365 - d) + isLeap(y);
}
```