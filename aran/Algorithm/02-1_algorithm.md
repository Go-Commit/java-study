# ALGORITHM

### Q1) 키뿐만 아니라 사람 수도 난수로 생성하도록 실습 2-5를 수정하여 프로그램을 작성하세요.
```java
import java.util.Random;
import java.util.Scanner;

class Algorithm {
    static int maxOf(int[] a) {
        int max = a[0];
        for(int i=1; i < a.length; i++) {
            if(a[i]>max) max = a[i];
        }
        return max;
    }

    public static void main(String[] args) {
        Random rand = new Random();
        Scanner sc = new Scanner(System.in);

        System.out.println("키의 최댓값을 구합니다.");
        System.out.print("사람 수 : ");
        int num = rand.nextInt(100);

        int[] height = new int[num];

        System.out.println("키 값은 아래와 같습니다.");
        for(int i=0; i< num; i++) {
            height[i] = 100 + rand.nextInt(90);
            System.out.println("height["+i+"]:"+height[i]);
        }

        System.out.println("최댓값은 "+maxOf(height)+"입니다.");
    }
}
```

### Q2) 오른쪽처럼 배열 요소를 역순으로 정렬하는 과정을 하나 하나 나타내는 프로그램을 작성하세요.
```java
static void swap(int[] a, int idx1, int idx2) {
	int t = a[idx1];
	a[idx1] = a[idx2];
	a[idx2] = t;
	System.out.println("a["+idx1+"]과(와) "+"a["+idx2+"]를 교환합니다.");
	for(int i=0; i<a.length; i++) {
		System.out.print(a[i]+"\t");
	}
	System.out.println();
	
}

static void reverse(int[] a) {
	for(int i = 0; i <a.length/2; i++){
		swap(a,i,a.length - i - 1);
	}
}

public static void main(String[] args) {
	Scanner sc = new Scanner(System.in);

	System.out.print("요솟수 : ");
	int num = sc.nextInt();
	int[] x = new int[num];

	for(int i=0; i<num; i++) {
		System.out.print("x["+i+"] : ");
		x[i] = sc.nextInt();
	}

	reverse(x);

	System.out.println("역순 정렬을 마쳤습니다.");
}
```

### Q3) 배열 a의 모든 요소의 합계를 구하여 반환하는 메서드를 작성하세요.
```java
static int sumOf(int[] a) {
	int sum = 0;
	for(int i=0; i<a.length; i++) {
		sum += a[i];
	}
	return sum;
}
```

### Q4) 배열 b의 모든 요소를 배열 a에 복사하는 메서드 copy를 작성하세요.
```java
static void copy(int[] a, int[] b) {
	for(int i=0; i<b.length; i++) {
		a[i] = b[i];
	}
}
```

### Q5) 배열 b의 모든 요소를 배열 a에 역순으로 복사하는 메서드 rcopy를 작성하세요.
```java
static void rcopy(int[] a, int[] b) {
	int idx = b.length-1;
	for(int i=0; i<b.length; i++) {
		a[i] = b[idx--];
	}
}
```