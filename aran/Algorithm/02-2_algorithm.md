# ALGORITHM

### Q6)배열의 앞쪽에 아랫자리가 아니라 윗자리를 넣어두는 메서드를 작성하세요.

```JAVA
static int cardConv(int x, int r, char[] d) {
    int digits = 0;
    String dchar = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    char[] temp = new char[32];

    do {
        temp[digits++]=dchar.charAt(x%y);
        x/=y;
    }while(x!=0);

    for(int i=0; i<digits; i++){
        d[i] = temp[digits-i-1];
    }

    return digits;
}
```

### Q7)오른쪽처럼 기수 변환 과정을 자세히 나타내는 프로그램을 작성하세요.
```java
public class example07 {
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        System.out.println("10진수를 기수변환합니다.");
        System.out.print("변환하는 음이 아닌 정수 : ");
        int num = sc.nextInt();
        System.out.print("어떤 진수로 변환할까요?(2~36)");
        int cd = sc.nextInt();

        char[] cno = new char[32];
        int result = CardConv(num, cd,cno);
        for(int i=0; i<result; i++) {
            System.out.print(cno[i]);
        }
    }

    static int CardConv(int num, int cd, char[] cno) {
        int digits = 0;
        String dchar = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        do {
            if(digits == 0 ){
                System.out.printf("%d|%6d\n",cd,num);
                System.out.println(" +-----------");
            }else if(x/y != 0) {
                System.out.printf("%d|%6d ... %d\n",cd,num,num%cd);
                System.out.println(" +-----------");
            }
            else {
                System.out.printf("%8d ...%d\n",cd,num%cd);
            }

            x/=y;
        }while(x!=0);

        for(int i = 0; i<digits; i++){
            char temp = d[i];
            cno[i] = d[digits-i-1];
            cno[digits-i-1] = temp;
        }
        return digits;
    }
}
```