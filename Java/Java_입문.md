# Java 입문

- [HelloWorld.java](#helloworldjava)
- [변수](#변수)
    - [변수선언](#변수선언)
    - [변수명](#변수명)
    - [선언 위치와 변수 (공부필요)](#선언-위치와-변수-공부-필요)
- [자료형](#자료형)
    - [기본자료형](#기본자료형)
    - [참조자료형 (공부필요)](#참조자료형-공부-필요)
    - [형변환](#형변환-casting)
- [연산자](#연산자)
- [배열](#배열)
    - [1차원 배열](#1차원-배열)
    - [다차원 배열](#다차원-배열)
- [조건문](#조건문)
    - [if문](#if문)
    - [switch문](#switch문)
- [반복문](#반복문)
    - [for문](#for문)
    - [for each문](#for-each문)
    - [while문](#while문)
    - [do while문](#do-while문)

## HelloWorld.java
```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello World!");
  }
}
```

## 변수
### 변수선언
- 변수 선언과 초기화
    ```java
    int i = 0;
    ```

- 변수 선언 후 초기화
    ```java
    int i;
    i = 0;
    ```

### 변수명
- 자바 키워드 사용불가
- 숫자로 시작 불가
- _와 $ 외 특수문자 사용불가

> ### 선언 위치와 변수 (공부 필요)
> - 멤버변수
>    - 선언 위치 : 클래스 영역
>    - 클래스변수
>        - 클래스 내 모든 객체가 공통적으로 똑같은 속성을 가질 때 사용
>        - 일반적으로 앞에 'static'이 붙어있다.
>            ```java
>            static int height = 200;
>                //클래스변수, 높이 200 모든 객체(인스턴스)에 적용
>            String color;
>                //인스턴스변수, 값이 고정되지 않아 객체마다 다른값 가능
>            ```
>    - 인스턴스변수
>        - 각각의 객체(인스턴스)마다 개별적인 속성을 가져야할 때 사용
> - 지역변수
>    - 선언 위치 : 메소드나 생성자 내부
>    - 선언된 지역에서만 사용이 가능한 변수
>    - 메소드가 종료되면 자동으로 소멸됨

## 자료형
### 기본자료형
- 사용하는 메모리가 정해져있는 자료형
- 기본 자료형 변수가 가진 값 => 기본 자료형의 값

    - 정수형
        - byte (1byte)
            - 부호를 가진 8bit 정수 / -128 ~ 127
        - char (2byte)
            - 16bit 유니코드 문자 데이터 / '\u0000' ~ '\uFFFF'
        - short (2byte)
            - 부호를 가진 16bit 정수 / -32,768 ~ +32,767
        - int (4byte)
            - 부호를 가진 32bit 정수 / -2,147,483,638~+2,147,483,647
        - long (8byte)
            - 부호를 가진 64bit 정수 / -9223372036854775808~+9223372036854775807
    - 실수형
        - float(4byte)
            - 부호를 가진 32bit 부동 소수점 / -3.402932347e+38~+3.40292347e+38
        - double(8byte)
            - 부호를 가진 64bit 부동 소수점 / -179769313486231570e+308~1.79769313486231570e+08
    - 논리형
        - boolean (1byte)
            - 참 or 거짓 값 / true or false

> ### 참조자료형 (공부 필요)
> - new 키워드로 생성한 객체
> - String과 배열은 new 없이 생성하는 참조 자료형
> - 임의로 내가 원하는 클래스를 만들어 참조 자료형으로 사용 가능.
> - 참조 자료형 변수가 가진 값 => 변수에 대한 메모리 주소
>
>     - String Type
>       - String
>       ```java
>       String name;
>       String myName = "myungsun";
>       ```
>
>     - Class Type
>       ```java
>       클래스명 객체명 = new 클래스명();
>       ```
>
>     > - Interface Type (공부 필요)
>     >   ```java
>     >   interface name<T>{
>     >       void number(T value);
>     >   }
>     >   ```
>
>     - 배열(Array) Type
>       ```java
>       int[] arr3 = new int[5];
>       int[] arr4 = {1,2,3,4,5};
>       ```
>
>     - 열거(Wrapper) Type
>         - Class 형식으로 기본형 자료를 감싼 형태
>         - 기본자료형은 null 초기화 할 수 없지만 Wrapper Class 는 가능
>
>              |제목|내용|
>              |:---:|:---:|
>              |byte|Byte|
>              |short|Short|
>              |int|Int|
>              |long|Long|
>              |float|Float|
>              |double|Double|
>              |char|Char|
>              |boolean|Boolean|

### 형변환 (Casting)
- 묵시적 형변환
    - 작은 공간의 메모리에서 큰 공간의 메모리로 이동
    ```java
    int i = 100;
    long l = i;    
    ```
- 명시적 형병환
    - 큰 공간의 메모리에서 작은 공간의 메모리로 이동
    ```java
    int a;
    byte b;
    b = (byte) a;
    ```

## 연산자
- 대입연산자 : =
    - 변수에 할당 시 사용 / 일반 수학과 달리 같다는 뜻이 아님.
    ```java
    int a;
    a = 1;
    ```

- 산술연산자
    |연산자|사용법|설명|
    |:---:|:---:|:---:|
    |+|a + b| a 더하기 b|
    |-|a - b| a 빼기 b|
    |*|a * b| a 곱하기 b|
    |/|a / b| a 나누기 b|
    |%|a % b| (a 나누기 b)의 나머지를 구함|

- 논리연산자 : 논리식을 판단해 true 또는 false를 결정
    - && : true && true 일때만 true
    - || : false && false 일때만 false
    - ! : !true 이면 false, !false 이면 true

- 산술대입연산자
    |연산자|사용법|설명|
    |:---:|:---:|:---:|
    |+=|a += b| a의 값은 a 더하기 b|
    |-=|a -= b| a의 값은 a 빼기 b|
    |*=|a *= b| a의 값은 a 곱하기 b|
    |/=|a /= b| a의 값은 a 나누기 b|
    |%=|a %= b| a의 값은 (a 나누기 b)의 나머지|

- 비트연산자
    |연산자|사용법|설명|
    |:---:|:---:|:---:|
    |& (AND)|a & b|1 & 1 일때만 1|
    |\| (OR)|a \| b|0 \| 0 일때만 0 |
    |^ (XOR)|a ^ b| 0 ^ 1 또는 1 ^ 0 일때만 1|
    |~ (NOT)|a ~ b| ~0 은 1, ~1 은 0|

- 시프트연산자
    |연산자|사용법|설명|
    |:---:|:---:|:---:|
    |>>|a >> b| a의 bit값을 오른쪽으로 b만큼 이동|
    |<<|a << b| a의 bit값을 왼쪽으로 b만큼 이동|
    |>>>|a >>> b| a의 bit값을 오른쪽으로 b만큼 이동하면서|
    ||ㄴ|부호와 상관없이 왼쪽에 항상 0으로 채움|

- 비트대입연산자
    |연산자|사용법|설명|
    |:---:|:---:|:---:|
    |&=|a &= b| a의 값은 a & b|
    |\|=|a \|= b| a의 값은 a \| b|
    |^=|a ^= b| a의 값은 a ^ b|
    |>>=|a >>= b| a의 값은 a >> b|
    |<<=|a <<= b| a의 값은 a << b|
    |>>>=|a >>>= b| a의 값은 a >>> b|

- 관계연산자
    |연산자|사용법|설명|
    |:---:|:---:|:---:|
    |>|a > b| a 가 b보다 크면 true, 아니면 false|
    |>=|a >= b| a 가 b보다 크거나 같으면 true, 아니면 false|
    |<|a < b| a 가 b보다 작으면 true, 아니면 false|
    |<=|a <= b| a 가 b보다 작거나 같으면 true, 아니면 false|
    |==|a == b| a 가 b와 같으면 true, 아니면 false|
    |!=|a != b| a 가 b와 다르면 true, 아니면 false|
    |instanceof|a instanceof b| a 가 b의 인스턴스(객체)면 true, 아니면 false|

- 단항연산자
    - 부호연산자 : +a, -a / 양수, 음수
    - 증감연산자
        - 증가연산자
            - a++ : a의 값 반환 후 1 증가
            - ++a : 1 증가 후 a의 값 반환
        - 감소연산자
            - a-- : a의 값 반환 후 1 감소
            - --a : 1 감소 후 a의 값 반환

- 삼항연산자
    - 조건식 ? true일 경우 실행할 수식 : false일 경우 실행할 수식
        ```java
        int a = 10;
        int b = 100;
        int a > b ? a - b : b - a;
        ```

## 배열
- 인덱스를 이용해 같은 자료형의 데이터를 저장하는 기억공간
- 자바에서의 배열은 크기가 정해지면 변경하지 못함
### 1차원 배열
- 배열 선언 후 초기화
    ```java
    //자료형[] 변수명; , 자료형 변수명[];
    int[] numbers;
    String fruits[];

    //변수명 = new 자료형[크기]
    numbers = new int[3]
    fruits = new String[3]
    ```
- 배열 선언과 초기화
    ```java
    int[] ages = new int[10];
    ```
- 배열 선언과 초기화, 대입
    ```java
    char[] arr1 = {'a', 'b', 'c', 'd', 'e'};
    ```

    |내용물||[0]의 주소|'a'|'b'|'c'|'d'|'e'|
    |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
    |접근||arr1|arr1[0]|arr1[1]|arr1[2]|arr1[3]|arr1[4]|

### 다차원 배열
- 2차원 배열 선언 후 초기화
    ```java
    //자료형[][] 변수명; , 자료형 변수명[][];
    int[][] numbers;
    String fruits[][];

    //변수명 = new 자료형[크기][크기]
    numbers = new int[3][5]
    fruits = new String[3][2]
    ```
- 배열 선언과 초기화
    ```java
    int[][] ages = new int[4][2];
    ```
- 배열 선언과 초기화, 대입
    ```java
    char[][] arr1 = {
        {'a', 'b', 'c', 'd', 'e'},
        {'f', 'i', 'j', 'k', 'l'}
        };
    ```

    |내용물 v|'a'|'b'|'c'|'d'|'e'|
    |:---:|:---:|:---:|:---:|:---:|:---:|
    ||arr1[0][0]|arr1[0][1]|arr1[0][2]|arr1[0][3]|arr1[0][4]|
    ||arr1[1][0]|arr1[1][1]|arr1[1][2]|arr1[1][3]|arr1[1][4]|
    |내용물 ^|'f'|'i'|'j'|'k'|'l'|

- 가변배열 : 다차원 배열의 행마다 다른 길이의 배열을 저장할 수 있는 배열
    ```java
    //배열 생성시 두번째 크기 지정 안함
    char[][] arr = new char[3][];
    arr[0] = new char[3];
    arr[1] = new char [5];
    arr[2] = new char [2];

    //선언과 초기화, 대입
    char[][] arr = {
            {'c', 'a', 't'},
            {'a', 'p', 'p', 'l', 'e'},
            {'o', 'h'}
        };
    ```

## 조건문
### if문
- if
    ```java
    if (조건식) {
        조건식의 값이 참일 때 실행될 수식
    }
    ```
- else
    ```java
    if (조건식) {
        조건식의 값이 참일 때 실행될 수식
    }
    else {
        위의 값이 거짓일 때 실행될 수식
    }
    ```
- else if
    ```java
    if (조건식) {
        조건식의 값이 참일 때 실행될 수식
    }
    else if (조건식){
        위의 값이 거짓이고 조건식이 참일 때 실행될 수식
    }
    else {
        위의 값이 거짓일 때 실행될 수식
    }
    ```

### switch문
```java
switch (조건값) {
    case 값1:
        조건값이 값1일 때 실행될 수식;
        break;
    case 값2:
        조건값이 값2일 때 실행될 수식;
        break;
    default:
        아무 조건값에 해당하지 않을 떄 실행될 수식
        break;
}
```
- default와 break문

## 반복문
: 조건이 참일때 수식 반복수행
### for문
- 
    ```java
    for(초기값; 조건식; 증감값)
    {
        반복할 수식;
    }

    //예제
    String[] fruits = {'lemon','cherry','mango'};
    for(int i=0; i<fruits.length; i++) {
        System.out.println(fruits[i]);
    }
    ```
### for each문
- for each는 J2SE 5.0 부터 추가됨
- 조건식 부분이 조금 다름
    ```java
    for (자료형 변수명: iterate) {
        반복할 수식;
    }

    //예제
    String[] fruits = {'lemon','cherry','mango'};
    for (String fruit : fruits) {
        System.out.println(fruit);
    }
    ```
    - iterate : 루프를 돌릴 객체
    - iterate 객체에서 한개씩 순차적으로 var에 대입되어 for문을 수행
    - iterate부분에 들어가는 타입은 루프를 돌릴수 있는 형태인 배열 및 ArrayList등이 가능
### while문
- 
    ```java
    초기값;
    while(조건식){
        반복할 수식;
        증감값;
    }
    ```
### do while문
- do while : 조건식이 false여도 무조건 한번은 수행된다.
    ```java
    do{
        반복할 수식;
        증감값;
    } while(조건식);
    ```