# 3주차 - 연산자
- 학습할 것
    ```
    +최우선 연산자
    산술 연산자
    비트 연산자
    관계 연산자
    논리 연산자
    instanceof
    assignment(=) operator
    화살표(->) 연산자
    3항 연산자
    연산자 우선 순위
    (optional) Java 13. switch 연산자
    ```
- 참고링크
    ```
    http://www.tcpschool.com/java/java_lambda_concept
    ```

<br>
<br>
<br> 

# 최우선 연산자
|기호|이름|
|:--:|:--:|
|()|괄호 연산자|
|.|참조 연산자|
|[]|배열 첨자 연산자|


<br>
<br>
<br> 


# 비트 & 논리 & 단항 연산자

<br>
<br>

## 비트 연산자
| 기호                                               | name | 기능 |
|----------------------------------------------------|------|------|
| & |AND| 연산자 좌우 값이 모두 참일 경우=> 참  |
| \| | OR | 연산자좌우값이하나라도참인경우=>참    |
| ^ | XOR | 연산자 좌우 값이 서로 다른 경우 => 참   |

<br>

## 논리 연산자
| 기호 | 예시     | 기능                                                          |
|------|----------|---------------------------------------------------------------|
| &&   | a && b   | a와 b 모두 참일 경우 true / 그렇지 않을 경우 false 반환       |
| \|\| | a \|\| b | a와 b 모두 거짓일 경우 false / 그렇지 않을 경우 true 반환 |

<br>

## shift 연산자
|종류|기호|이름|사용예|기능|
|:--:|:--:|:--:|:--:|:--:|
|Shift 연산자|<<|Left shift| a\<\<b |a를 비트연산 왼쪽 b번 만큼 shfit|
|Shift 연산자|>>|Right shift|a>>b|a를 비트연산 오른쪽 b번 만큼 shfit|
|Shift 연산자|<<<|부호없는 Right shift|a>>>b|부호를 고려하지 않고 R shift|
|Shift 연산자|>>>|부호없는 left shift|a>>>b|부호를 고려하지 않고 L shift|

<br>

## 단항 연산자
- 좌/우 항이 없어도 연산되는
  
|기호|이름|기능|
|:--:|:--:|:--:|
|+/-|부호연산|부호값을 나타냄|
|!|논리 부정|t/f 간에 부정|
|~|비트 부정|숫자 데이터의 비트 부정|
|++a|전위증가||
|a++|후위증가||
|a--|전위감소||
|--a|후위감소||



<br>
<br>
<br> 


# 산술 연산자
|기호|사용예|기능|
|:--:|:--:|:--:|
|*|a * b| 두 수의 곱|
|/|a / b| 나눗셈(몫)|
|%|a % b| 나눗셈(나머지)|
|+|a + b| 두 수의 합|
|-|a – b| 두 수의 차|
- 모든 산술연산에 대하여 배정대입 연산이 가능
  - 예시) +=, -=, *=, /=, %= 
    - a += 2;
    - a -= 3;
    - a *= 7;

<br>
<br>
<br> 

# 관계 연산자
- 비교 관계 연산자라고도 하며 연산의 결과값은 boolean이라는게 특징
  
|기호|사용예시|기능|
|:--:|:--:|:--:|
|==| a==b |같니?|
|!=| a!=b |다르니?|
|>| a > b |크니?|
|>=| a >= b |크거나 같니?|
|<| a < b |작니?|
|<=| a <= b |작거나 같니?|

<br>
<br>
<br> 

#  삼항연산자
- Shift 연산자는 C/C++ 에서 임베디드 프로그래밍에 주로 사용되는 연산자들
- java에서는 거의 써보지 않았지만, 앞으로 쓸일이 있을까? 궁금.. 
  
|종류|기호|이름|사용예|기능|
|:--:|:--:|:--:|:--:|:--:|
|Shift 연산자|<<|Left shift| a\<\<b |a를 비트연산 왼쪽 b번 만큼 shfit|
|Shift 연산자|>>|Right shift|a>>b|a를 비트연산 오른쪽 b번 만큼 shfit|
|Shift 연산자|<<<|부호없는 Right shift|a>>>b|부호를 고려하지 않고 shift|
|삼항연산자|조건 ? 선택1:선택2;|삼항연산자|a>b ? A:B;|a와 b의 결과에 따라 참이면 A가 실행, 거짓이면 B가 실행|
||||||
||||||
||||||

### 삼항연산자 예제코드
```java
public static void main(String[] args) {
  int a = 7;
  int b = 9;

  int c = (a < b ) ? a : b;
  int d = (a < b ) ? 0 : 1;
}
```
- 위 예제코드에서 각각
  - c = 9
  - d = 1
- 이 들어가는데 그 이유는 아래와 같은 구조이기 때문
```java
int temp = ([변수1] [연산자] [변수2]) ? 참일떄 : 거짓일때;
```
- 참고로 if-else 문으로 비숫하게 구현할 수 있으나 바이트코드상 차이는 거의 없다
- 대신, 코드 가독성이나, 한두줄정도는 라인수를 줄일 수 있는 숏코딩이 가능하다!


<br>
<br>
<br> 


# 연산자 instanceof 
- 자바야 이거 형변환 가능한거임? 물어보는 연산자
- 특히 객체의 형 변환시 자주 사용됨
- 너무 당연하게도 프리미티브 타입 변수에는 해당 연산자를 사용할 수 없다(java Object 를 상속받지 않았으므로)
- 예시
  - A instanceof B : B라는 객체가 A와 같은 타입인지 확인하는 부분
  - 부모 instanceof 자식 : 자식 클래스에 부모가 접근 가능하면 T를 반환
  - 참조변수 instanceof 타입(클래스)

- 인스턴스오브 예제코드
```JAVA
public static void main(String[] args) {
  String s = "hello";
  boolean check = s instanceof java.lang.String;
}
```

### instanceof 예제
```java
Sytem.out.printf(null instanceof Object);
//false 출력됨

Object obj = new int[] {1,2,3};
System.out.println(obj instanceof int[]);
//true 출력

System.out.println(obj instanceof byte[]);
//false 출력

System.out.println(obj instanceof Object);
//true 출력

```


```
```


<br>
<br>
<br> 

# assignment(=) operator


```java
public static void main(String[] args) {
  int a = 2;
  a += a;

}
```


<br>
<br>
<br> 

# 화살표(->) 연산자 : lambda expression (람다 표현식)
- 람다 표현식이란, 메서드(맴버함수)를 한줄로 짧게 표현하는 기능
- 예를들어 
  - 메소드는 아래와 같이 만들지만
  ```java
  int min(int x, int y) {

      return x < y ? x : y;

  }
  ```
  - 람다 표현식은 이렇게 한즐로 만들수 있습니다
  ```java
  (x, y) -> x < y ? x : y;
  ```
### 화살표 연산자 예제코드
- 출처 : 오라클 람다 ->> https://www.oracle.com/technical-resources/articles/java/architect-lambdas-part1.html

```java
public class Lambdas {
  public static void main(String[] args) {
    Runnable myR = new Runnable();
    public void run() {
      System.out.println("Hello world!!");
    }
  };
  r.run();
}
```

```java
public static void main(String[] args) {
  Runnable r = () -> System.out.println("Hello world!!");
  r.run();
}
```
- 위의 두 예제코드는 완전히 동일하게 동작하는데
- 참고로, 바이트코드를 뜯어보면 invoke special 이라는 기능으로 이루어져 있다.
### 모르지만 넘어가는 부분
- invoke special
- invoke dynamic

- 이 람다 표현식을 사용하는 이유는
  - 코드를 간결하고 직관적이게
  - 코드 가독성 up!
- 제한사항으로는 Java 1.8 버전 이상부터 
- 익명 클래스 기법이라고 호칭할수 있는데,
  - 단 하나의 객체만을 생성할 수 있는 클래스를 
  - 자바에서는 클래스의 선언과 동시에 객체를 생성
  - 자바에서 람다 표현식은 익명 클래스와 동일
  - 클래스를 작성하고 객체를 생성하는 번거로운 작업 없이 메소드 사용가능

- 람다 표현식
```
(x, y) -> x < y ? x : y;
```

- 익명 클래스
```
new Object() {

    int min(int x, int y) {

        return x < y ? x : y;

    }

}
```

- 해당 기능 쓰고싶으면 Functional Interface 를 사용

> 아직은 람다를 정확히 이해하고 쓸수는 없다. 나중에 더 정리할 예정

<br>
<br>
<br> 

# 연산자 우선 순위
- 주의사항
  - 연산자마다 연산의 대상이 되는 자료형이 정해져 있음
  - 범위를 넘는 연산에 대해서는 에러가 일어나지 않고, 연산결과에 이상한 값이 들어가게 됨(=버그 발생 원인 가능성)
  - 0으로 나누거나 나머지를 구할 때 자바에서의 연산에러가 발생함


|우선순위|예시|분류|
|:--:|:--:|:--:|:--:|
|1||최우선 연산자|
|2||단항,증감,cast,instance of|
|3||산술|
|4||shift|
|5||비교 관계|
|6||비트|
|7||논리|
|8||삼항|
|9||배정대입|
|10||전,후위 증감|
|11||컴마연산|

<br>
<br>
<br> 

# (optional) Java 13. switch 연산자

- C언어 계열 언어들이 그렇듯이 Switch-case 구문을 쓰는데, 사실 C언어에서 switch 구문을 컴파일해서 어셈블리로 까보면 다중 if-else문으로 구현되어 있어서 가독성 빼고 성능상의 장점은 없었다.
- 자바 13버전 이상에서의 switch연산자는 이전의 switch-case 문과 확실히 다른데,
- 최적화에 좋은 문법임
- 예제코드를 돌려보며 바이트코드를 확인해 보면서 진짜 그런지 확인 ㄱ ㄱ

### 먼저 스위치 키워드를 사용했을때
```java
public static void main(String[] args) {
  int a = 5;
  switch (a) {
    case 1:
      a = 4;
      break;
    case 5:
      a = 3;
      break;
    default:
      a = 7;
  }
}
```
- 바이트코드
  - 출처 : https://whereishq.blogspot.com/2020/11/3.html
```
stack=1, locals=2, args_size=1
 0: iconst_5
 1: istore_1
 2: iload_1
 3: lookupswitch  { // 2
     1: 28
     5: 33
     default: 38
 }
28: iconst_4
29: istore_1
30: goto          41
33: iconst_3
34: istore_1
35: goto          41
38: bipush        7
40: istore_1
41: return
```
- lookupswitch는 키를 사용하여 테이블에서 대상 주소를 조회하고 해당 주소의 명령어에서 계속 실행하는 방식으로 동작한다.

### 두번째로, if-elseif-else 문법을 사용할때
```java
public static void main(String[] args) {
  int a = 5;
  if (a == 4) {
    a = 4;
  } else if (a == 5) {
    a = 3;
  } else {
    a = 7;
  }
}
```

```
stack=2, locals=2, args_size=1
 0: iconst_5
 1: istore_1
 2: iload_1
 3: iconst_4
 4: if_icmpne     12
 7: iconst_4
 8: istore_1
 9: goto          25
12: iload_1
13: iconst_5
14: if_icmpne     22
17: iconst_3
18: istore_1
19: goto          25
22: bipush        7
24: istore_1
25: return
```

- 동일한 기능을 하는 스위치문, 그리고 이프문 두가지 방식을 바이트코드로 분석한 결과
  - if 방식에서 stack 공간을 하나 더 사용함
  - 실행해야 할 명령이 많아졌다(성능이 조금 더 구림)


<br>
<br>
<br> 

# 끝

<br> 

#
<br> 

#
