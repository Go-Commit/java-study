# ALGORITHM

### Q10. 시력 분포를 오른쪽처럼 그래프로 출력하도록 바꾸어 프로그램을 작성하세요. 기호 문자 *를 사람 수만큼 반복하여 나타내세요.
```java
for(int i = 0; i < VMAX; i++) {
	System.out.printf("%3.1f ~ :", i/10.0);
	for(int j = 0; j < VMAX; j++) {
		System.out.print("*");
	}
	System.out.println();
}
```

### Q11. 오른족처럼 서기 년월일을 필드로 갖는 클래스를 만드세요. 다음과 같이 생성자와 메서드를 정의해야 합니다.
```java
class YMD {
	int y;	//년
	int m;	//월(1~12)
	int d;	//요일(1~31)

	YMD(int y, int m, int d) {
		this.y = y;
		this.m = m;
		this.d = d;
	}

	static int[][] mdays = {
		{31,28,31,30,31,30,31,31,30,31,30,31}, // 평년
		{31,29,31,30,31,30,31,31,30,31,30,31}, // 윤년
	}

	static int isLeap(int y) {
		return (y % 4 == 0 && y % 100 != 0 || y % 400 == 0 ) ? 1:0;
	}

	// n일 뒤에 날짜 반환
	static int afterYMD(int n) {
		YMD result = new YMD(this.y, this.m, this.d);
		
		if(n > 0)
		{
			result.d += n;

			while(result.d>mdays[isLeap(result.y)][result.m-1]) {
				result.d-=mdays[isLeap(result.y)][result.m-1];
				result.m++;
				
				// 12월이 넘을 경우 다음해로 넘어감
				if(result.m > 12)
				{
					result.y++;
					result.m = 1;
				}
			}
		}
		return result;
	}

	// n일 앞의 날짜 반환
	static int beforeYMD(int n) {
		YMD result = new YMD(this.y, this.m, this.d);

		if(n > 0) {
			result.d -= n;

			while(0 > result.d) {
				result.d += mdays[isLeap(result.y)][result.m-1];
				result.m--;

				if(0 > result.m ) {
					result.y--;
					result.m = 12;
				}
			}
		}
		return result;
	}
}
```