### Q8
```
static int dayOfYear(int y, int m, int d) {
  while (--m != 0) 
    d += mdays[isLeap(y)][m - 1];
  return d;
}
```

### Q9
```
static int leftDayOfYear(int y, int m, int d) {
  while (--m != 0)
    d += mdays[isLeap(y)][m - 1];
  return 365 + isLeap(y) - d;
}
```
