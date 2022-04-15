#### 참조 타입에 대한 설명으로 틀린 것은?
* 2 >> 메모리는 힙에 저장

#### 2. 자바에서 메모리 사용에 대한 설명으로 틀린 것은?
* 3 >> 참조되지 않는 객체는 garbage collector에서 자동으로 제거

#### 3. String 타입에 대한 설명으로 틀린 것은?
* 2 >> ==가 아닌 .equals()를 사용

#### 4. 배열을 생성하는 방법으로 틀린 것은?
* 2

#### 5. 배열의 기본 초기값에 대한 설명으로 틀린 것은?
* 3 >> false

#### 6. array.length의 값과 array[2].length의 값은?
```
int[][] array = {
  {95, 86},
  {83, 92, 96},
  {78, 83, 93, 87, 88}
};
```
* array.length = 3;
* array[2].length = 5;

#### 7. 주어진 배열의 항목에서 최대값은? (for문 사용)
```
public static void main(String[] args) {
    int max = 0;
    int[] array = {1, 5, 3, 8, 2};
    
    for(int i=0; i<array.length; i++) {
        if(max < array[i])
          max = array[i];
    }
    System.out.println("max: " + max);    
}
```

#### 8. 주어진 배열의 전체 항목 합과 평균값은? (중첩 for문 사용)
```
public static void main(String[] args) {
    int[][] array = {
      {95, 86},
      {83, 92, 96},
      {78, 83, 93, 87, 88}
    };    
    
    int sum = 0;
    double avg = 0.0;
    
    int cnt = 0;
    
    for(int i=0; i<array.length; i++) {
        for(int j=0; j<array[i].length; j++) {
            sum += array[i][j];
            cnt++;
        }
    }
    
    avg = (double)sum / cnt;
    
    System.out.println("sum: "+sum);
    System.out.println("avg: "+avg);
}
```

#### 9. 키보드로부터 학생 수와 각 학생들의 점수를 입력 받아서, 최고 점수 및 평균 점수를 구하는 프로그램
```
public static void main(String[] args) {
    Scanner scan = new Scanner(System.in);
    int studentCnt = 0;
    int[] score = null;
    boolean flag = true;
    
    while(flag) {
    
        System.out.println("1. 학생수 | 2. 점수입력 | 3. 점수리스트 | 4. 분석 | 5. 종료");
        System.out.print("선택> ");

        int sel = scan.nextInt();

        if(sel == 1) {
            System.out.print("학생수> ");
            studentCnt = scan.nextInt();
            score = new int[studentCnt];
        }
        else if(sel == 2) {
            for(int i=0; i<studentCnt; i++) {
                System.out.print("score["+i+"]> ");
                score[i] = scan.nextInt();
            }
        }
        else if(sel == 3) {
            for(int i=0; i<studentCnt; i++) {
                System.out.println("score["+i+"]: " + score[i]);
            }            
        }
        else if(sel == 4) {
            int maxScore = 0;
            int totalScore = 0;
            for(int i=0; i<studentCnt; i++) {
                if(maxScore<score[i]) {
                    maxScore = score[i];
                }
                totalScore += score[i];
            }  
            double avgScore = (double)totalScore / studentCnt;
            System.out.println("최고 점수: " + maxScore);
            System.out.println("평균 점수: " + avgScore);            
        }
        else if(sel == 5) {
            System.out.println("프로그램 종료");  
            flag = false;
        }        
    }
}
```
