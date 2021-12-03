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