#### 실습2-1
```
public static void main(String[] args) {
    int[] a = new int[5];
    
    a[1] = 37;
    a[2] = 51;
    a[4] = a[1] * 2;
    
    for(int i=0; i<a.length; i++) {
        System.out.println("a[" + i + "] = " + a[i]);
    }
}
```

#### 실습 2-2
```
public static void main(String[] args) {
    int[] a = {1, 2, 3, 4, 5};
    
    for(int i=0; i<a.length; i++){
      System.out.println("a[" + i + "] = " + a[i]);
    }
}
```

#### 실습 2-3
```
public static void main(String[] args) {
    int[] a = {1, 2, 3, 4, 5};
    int[] b = a.clone();
    
    b[3] = 0;
    
    System.out.print("a = ");
        
    for(int i=0; i<a.length; i++){
      System.out.print(" " + a[i]);
    }
    
    System.out.print("\nb = ");
    
    for(int i=0; i<b.length; i++){
      System.out.print(" " + b[i]);
    }
}
```

#### 실습 2-4
```
class MaxOfArray {
  static int maxOf(int[] a) {
    int max = a[0];
    for(int i=0; i<a.length; i++)
      if(a[i] > max)
        max = a[i];
      return max;
  }
  
  public static void main(String[] args) {
      Scanner stdIn = new Scanner(System.in);

      System.out.print("사람 수 : ");
      int num = stdIn.nextInt();

      int[] height = new int[num];

      for(int i=0; i<num; i++) {
        System.out.print("height[" + i + "] : ");
        height[i] = stdIn.nextInt();
      }

      System.out.println("최댓값: "+ maxOf(height));
    }
  }
}
```

#### 실습 2-5
```
class MaxOfArrayRand {
  static int maxOf(int[] a) {
    int max = a[0];
    for(int i=0; i<a.length; i++)
      if(a[i] > max)
        max = a[i];
    return max;
  }

  public static void main(String[] args) {
    Random rand = new Random();
    Scanner stdIn = new Scanner(System.in);

    System.out.print("사람 수 : ");
    int num = stdIn.nextInt();

    int[] height = new int[num];

    for(int i=0; i<num; i++) {
      height[i] = 100 + rand.nextInt(90);
      System.out.print("height[" + i + "] : " + height[i]);
    }

    System.out.println("최댓값 : "+ maxOf(height));
  }
}
```


#### Q1
```
class MaxOfArrayRand {
  static int maxOf(int[] a) {
    int max = a[0];
    for(int i=0; i<a.length; i++)
      if(a[i] > max)
        max = a[i];
    return max;
  }

  public static void main(String[] args) {
    Random rand = new Random();

    System.out.print("사람 수 : ");
    int num = rand.nextInt(100);

    int[] height = new int[num];

    for(int i=0; i<num; i++) {
      height[i] = 100 + rand.nextInt(90);
      System.out.print("height[" + i + "] : " + height[i]);
    }

    System.out.println("최댓값 : "+ maxOf(height));
  }
}
```

#### 실습 2-6
```
class ReverseArray {
  static void swap(int[] a, int idx1, int idx2) {
    int t = a[idx1]; a[idx1] = a[idx2]; a[idx2] = t;
  }

  static void reverse(int[] a) {
    for (int i=0; i<a.length/2; i++)
      swap(a, i, a.length - i - 1);
  }
  
  public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);

    int num = stdIn.nextIn();

    int[] x = new int[num];

    for(int i=0; i<num; i++) {
      System.out.print("x[" + i + "] : ");
      x[i] = stdIn.nextInt();
    }

    reverse(x);

    for (int i=0; i<num; i++)
      System.out.println("x[" + i + "] = " + x[i]);
  }
}
```

#### Q2
```
class ReverseArray {
  static void swap(int[] a, int idx1, int idx2) {
    System.out.println("a[" + idx1 + "]와 a[" + idx1 + "] 교환함");
    int t = a[idx1]; a[idx1] = a[idx2]; a[idx2] = t;
  }

  static void reverse(int[] a) {
    for (int i=0; i<a.length/2; i++) {
      System.out.print(a[i] + " ");
      System.out.println("");
      swap(a, i, a.length - i - 1);
    }
  }
  
  public static void main(String[] args) {
    Scanner stdIn = new Scanner(System.in);

    int num = stdIn.nextInt();

    int[] x = new int[num];

    for(int i=0; i<num; i++) {
      System.out.print("x[" + i + "] : ");
      x[i] = stdIn.nextInt();
    }

    reverse(x);

    for (int i=0; i<num; i++) {
      System.out.print(x[i] + " ");
    }
    System.out.print("\n역순정렬 끝");
  }
}
```

#### Q3
```
static int sumOf(int[] a) {
  int rlst = 0;
  for(int i=0; i<a.length; i++) {
    rlst += a[i];
  }
  return rlst;
}
```
