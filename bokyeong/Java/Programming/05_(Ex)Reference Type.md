
# 참조타입 (Reference Type)
<br>

```JAVA
public class Excercise07 {
	public static void main(String[] args) {
		int max = 0;
		int[] array = { 1,5,3,8,2 };
		
		for (int i=0; i<array.length; i++) {
			if(max < array[i]){
				max = array[i];
			}
		}
		
		System.out.println("max: "+ max);
	}
}
/*
max: 8
*/
```

```JAVA
public class Exercise08 {
   public static void main(String[] args) {
    int[][] array = {
   		{95,86},
   		{83,92,96},
   		{78,83,93,87,88}		
   	};
   	
   	int sum = 0;
   	double avg = 0.0;
   	
    int cnt = 0;
    
   	for (int i=0; i<array.length; i++) {
   		for (int j=0; j<array[i].length; j++) {
   			sum += array[i][j];
            cnt++;
   		}
   	}
       
    avg = (double)sum / cnt;
       
   	System.out.println("sum: "+ sum);
   	System.out.println("avg: "+ avg);
   	
   }
}
/*
sum: 881
avg: 88.1
*/
```

```JAVA
import java.util.Scanner;

public class Excercise09 {
   public static void main(String[] args) {
   	
    boolean run = true;
    int studentNum = 0;
    int[] score = null;
    Scanner sca = new Scanner(System.in);
   
    while (run) {
   	    System.out.println("----------------------------------------");
   	    System.out.println("1.학생수 / 2.점수입력 /3.점수리스트 / 4.분석 / 5.종료");
   	    System.out.println("----------------------------------------");
   	    System.out.print("선택> ");
   	
   	    int selectNo = sca.nextInt();
   	
   	    if (selectNo == 1) {
   		    System.out.print("학생수> ");
   		    studentNum = sca.nextInt();
   		    score = new int[studentNum];
   	    } else if (selectNo == 2) {
   		    for (int i=0; i<studentNum; i++) {
   			    System.out.print("score["+i+"]> ");
   			    score[i] = sca.nextInt();
   		    }
   	    } else if (selectNo == 3) {
   		    for (int i=0; i<studentNum; i++) {
   			    System.out.println("score["+i+"]: "+ score[i]);
   		    }		
   	    } else if (selectNo == 4) {
   		    int max = 0;
   		    int sum = 0;
   		    double avg = 0.0;
   		    for (int i = 0; i < studentNum; i++) {
   			    if (score[i] > max) {
   				    max += score[i];
   			    }
   			    sum += score[i];
   		    }
   		    avg = (double) sum / studentNum;
   		    System.out.println("최고 점수: "+ sum);
   		    System.out.println("평균 점수: "+ avg);
   	    } else if (selectNo == 5) {
   		    run = false;
   	    }
    }
    
    System.out.println("프로그램 종료");
   }
}
```