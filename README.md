# java-for-
## for문 효율적 사용 종류

1. 기본 적으로 사용하는 for 문<br>
|형태|예시|
|:---|---:|
|for(변수; 조건식; 증감식;)|for(int i = 0; i<array.size(); i++)|

->위의 형태와 같이 조건식에 array 길이만큼의 size()를 불러오게 되어있다.
허나 이것은 매번 반복문이 돌때 마다 size 메소드를 호출한다는 의미<br>
즉, 단순히 데이터가 작을 때는 크게 문제가 되지 않지만 데이터가 많아질 경우에는 그만큼 메모리 문제가 생길 수 있다.

-문제 해결 방법-<br>
|형태|
|:---:|
|for(int i = 0,size=array.size(); i<size; i++)|

->미리 초기값에 크기를 세팅하여 매번 array.size 크기를 불러오는 딜레이를 줄일 수 있다.<br>

2. 또 다른 문제점 찾기<br>

```C
  for(int i=0,size=array.size(); i<size; i++)
  {  
    System.out.println(array.get(i));
    System.out.println(array.get(i));
  } 
  
  ->두번 호출하게 될 경우 list를 두번 호출 하는 셈이 되기 때문에 이 또한 딜레이 현상이 발생하게 된다.
  
  @문제 해결 방법
  for(int i=0,size=array.size(); i<size; i++)
  { 
    String value = array.get(i);
    System.out.println(value)
    System.out.println(value)
  }
  위 방법은 value 값을 고정으로 선언하므로서 한번의 선언으로 list를 호출하게 된다.
  
  @또 다른 해결 방법 
  -foreach를 이용하는 것
  for( String value : array)
  {
     System.out.println(value);
     System.out.println(value);
  }
  array.size를 부를 필요 없이 바로 해당 값을 들고 오기 때문에 딜레이 걱정이 없다.
```

