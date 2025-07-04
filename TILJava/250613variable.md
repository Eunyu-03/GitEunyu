## 2025-06-13

# 주석 처리

- 한 줄 주석 (CTRL + /)
1. 소스코드에 설명글을 작성할 때 사용
2. 지금 당장은 사용하지 않는 코드에 사용
- 범위 주석 (CTRL + SHIFT + /, CTRL + SHIFT + \\)
1. 코드 중간에 있는 부분을 주석 처리할 때 사용

만들어 본 코드

```java
package printTest;

public class PrintTest {
	public static void main(String[] args) {
//		주석(CTRL + /)
//		1. 소스코드에 설명글을 작성할 때
//		2. 지금 당장 사용하지 않는 코드를 번역하고 싶지 않을 때
		
//		범위 주석(CTRL+ SHIFT + /, CTRL + SHIFT + \)
		/*
		 코드 중간에 있는 부분을 주석 처리할 때 사용한다.
		 */
		
//		이름을 출력하는 부분
		System.out.println("한동석");
//		나이를 출력하는 부분
		System.out.println("20살");
	}
}
```

# 출력 메소드

- 종류
1. print(): 마지막에 자동으로 줄바꿈되지 않고 아래 문장과 이어서 출력된다.
2. println(): 마지막에 자동으로 줄바꿈된다.
(syso 입력+CTRL+스페이스 바)->System.out.println();
3. printf(): 자동 줄바꿈 불가, 서식 문자 활용이 가능하다.

- 제어 문자(반드시 따옴표 안에서 작성한다.)

\n: new line<-, 줄바꿈, 개행 문자

\t: tab, 위 아래 줄 간격 맞춰 띄기

\": 큰 따옴표 표현

\': 작은 따옴표 표현

\\: \표현

		
- 서식 문자(반드시 따옴표 안에서 작성한다.)

%d: decimal 10진수 정수

%o: octal 8진수 정수

%x hexadecimal 16진수 정수

%f: float 실수

%c: char 문자

%s: String 문자열

- 출력 메소드를 사용하는 이유

오류를 구체화하기 위해서

예)

A 코드

B 코드

C 코드

D 코드

-> 오류 발생 시 어떤 라인에서 발생했는지 알 수 없다.

A 코드

System.out.println("A")

B 코드

System.out.println("B")

C 코드

System.out.println("C")

D 코드

System.out.println("D")

-> "C"가 콘솔에 출력되었다면, 위에서 아래로 번역되기 때문에 D 코드에 문제가 발생한 것으로 판단된다.

# 변수

- 변수는 RAM에 생성되는 저장공간이다.

# 자료형 (type)

-자료형은 저장공간의 종류이다.


	자료형		type		byte		값

	정수형		byte		1		1, 4, 1, -120, 100, ...
			short		2		123, 9, 150, -55, ...
			int(기본형)	4		-2147483648 ~ 2147483647
			long		8		30L, 8L -154616978L, ...
	실수형		float		4		3.12F, 2.59F, -123.5145F, 2.0F, ...
			double(기본형)	8		3.12, 2.59, -123.5145, 2.0, ...
	문자형		char		2		'a', 'b', '3', ...
	문자열		String		???		"ABC", "0.0", "123.3213", "A", "안녕", ...
	*문자열은 class다.

# 변수의 선언

- 자료형 변수명=초기값;

  예)
  
  int x=10;
  
  -> x라는 이름의 저장공간이 int형으로 할당(allocation)되고 그 안에 10이 들어간다.

만들어 본 코드
```java
package variableTest;

public class VariableTest {

	public static void main(String[] args) {

//		정수형, 변수명은 a, 값은 10, 단, 기본형으로 선언한다.
//		실수형, 변수명은 b, 값은 10.1563, 단, float형으로 선언한다.
//		실수형, 변수명은 c, 값은 10.1563, 단, double형으로 선언한다.
//		문자형, 변수명은 d, 값은 A
//		문자열, 변수명은 e, 값은 ABC
		
		int a=10;
		float b=10.1563F;
		double c=10.1563;
		char d='A';
		String e="ABC";
		
//		각 변수를 사용하여 출력 메소드로 출력해본다.
		
		System.out.println(a);
		System.out.println(b);
		System.out.println(c);
		System.out.println(d);
		System.out.println(e);
	}

}
```

# 주소

- int x=10;

x라는 이름의 저장공간이 int형으로 RAM에 할당되면, 고유한 값인 주소값이 부여된다.

계속 실행되거나 종료되는 프로그램이 있기 때문에, 주소가 이동될 수는 있으나 중복은 없다.

# 변수의 사용

-변수는 사용한 부분 통째로를 반드시 값으로 본다.

-자료형이 앞에 있거나 대입 연산자가 뒤에 있으면 선언으로 쓰임.

# 변수 선언 시 주의사항

1. 같은 이름의 변수로 선언할 수 없다.
2. 초기화를 해 준다.

정수: 0

실수: 0.0

문자: ' '

문자열: "", null

3. 되도록 선언부에 한꺼번에 선언한다(영역 상단).->가독성이 좋아짐

# 변수명 주의사항

1. 문자로 시작해야 한다.
3. 특수문자를 사용할 수 없다. 단, _는 허용한다.
4. 공백을 사용할 수 없다.
5. 되도록 한글을 사용하지 않는다.

good boy (X)

good_boy (O): 언더바 표기법

goodBoy (O): 카멜 표기법

6. 뜻이 있는 단어를 사용한다.

a, b, c, d, e, f, ... (X)

number, num, data, data1, ... (O)

만들어 본 코드
```java
package variableTest;

public class VariableTack {

	public static void main(String[] args) {
//		각 정보를 담을 변수를 자료형에 맞게 선언 및 값 지정
		String name="정은유";
		int age=23;
		double height=162.0;
		String hobby="베이스 연주";

//		출력력
		System.out.println(name);
		System.out.println(age);
		System.out.println(height);
		System.out.println(hobby);

	}

}
```

# 변수를 사용하는 이유

1. 반복되는 값을 쉽게 관리하기 위해서
2. 의미 없는 값을 하나의 정보로 만들기 위해서

# 형변환

-자동 형변환

정수+정수=정수

정수+실수=실수

정수+문자=정수

-강제 형변환

(자료형)값

(double)3=3.0

만들어 본 코드
```java
package castingTest;

public class CastingTest01 {

	public static void main(String[] args) {
//		자동 형변환
		System.out.println(5/2);
		System.out.println(5/2.0);
		
//		강제 형변환
		System.out.println(5/(double)2);
		System.out.println((int)2.9+5);

//		소수점 뒤를 날린 후 정수+정수 형태로 연산하기기
		double num1=8.43;
		double num2=2.59;
		int result=(int)num1+(int)num2;
		
		System.out.println(num1+"+"+num2+"="+result);
	}

}
```

- 문자열 형변환

1. 다른 자료형을 문자열로

문자열과 다른 일반 자료형을 연결하면 결과는 문자열이 된다.

2. 문자열을 다른 자료형으로

일반 자료형은 일반 자료형끼리만 형변환이 가능하다.

문자열 타입은 클래스 타입이므로, 일반 자료형의 클래스 타입의 도움을 받아야 한다.

Integer.parseInt("")->전달한 문자열에서 변환(추출)된 정수

Double.parseDouble("")->전달한 문자열에서 변환(추출)된 실수

```java
package castingTest;

public class CastingTest02 {
	public static void main(String[] arg) {
		System.out.println(""+3+8);
		
		System.out.println(3+8+"");

		int result=4;
		System.out.println("1+3="+result);
	}
}
```

# 상수

- 항상 그대로인 수
- 값을 변경할 수 없도록 한다.
- 값에 의미부여를 하기 위해 사용한다.

final 자료형 상수명=값;

만들어 본 코드
```java
package constantTest;

public class ConstantTest {
	public static void main(String[] args) {

		final int ON = 187568;
		final int OFF = 187455;
      
		System.out.println(ON);
		System.out.println(OFF);
      
//		로그인 실패: 0
//		로그인 성공: 1
//		관리자: 2
		final int LOGIN_SUCCESS_STATUS = 0;
		final int LOGIN_FAIL_STATUS = 1;
		final int LOGIN_ADMIN_STATUS = 2;
      
		System.out.println(LOGIN_SUCCESS_STATUS);
		System.out.println(LOGIN_FAIL_STATUS);
		System.out.println(LOGIN_ADMIN_STATUS);
      
	   }
}
```

# 입력

- 커서가 깜빡이고 있는 상태를 입력 상태라고 한다.
- 입력하기 전에 출력을 통해 어떤 값을 입력해야 할지 사용자에게 알려주어야 한다.

- 입력 클래스: Scanner sc=new Scanner(System.in)
- Scanner: 자료형, sc: 변수명, Scanner(System.in): 값

- next(): 입력 메소드, 사용자가 입력한 문자열 값

사용자가 입력한 값 중 공백 또는 줄바꿈 문자를 구분점으로 각 문자열을 분리한다.

첫 번째 문자열은 첫 번째 next()에 담기고 두 번째 문자열은 두 번째 next()에 담긴다.

- 만들어 본 코드-1
```java
package inputTest;

import java.util.Scanner;

public class InputTask01 {
	public static void main(String[] arg) {
//		반려동물 이름을 입력받고 출력하기
		String petNameMessage="반려동물의 이름을 입력하세요: ";
		String petAgeMessage="반려동물의 나이를 입력하세요: ";
		String petName="";
		int petAge=0;
		String result="";
		
		Scanner sc=new Scanner(System.in);
		System.out.print(petNameMessage);
		petName=sc.next();
		System.out.print(petAgeMessage);
		petAge=sc.nextInt();
		
//		System.out.println(petName);
//		System.out.println(petAge);
		
		result=petAge+"살의 "+petName+"! 건강하렴~";
		System.out.println(result);
	}
}
```

- 만들어 본 코드-2
```java
package inputTest;

import java.util.Scanner;

public class InputTask03 {
	public static void main(String[] args) {
//		3개의 정수를 한 번에 입력받은 후 덧셈 결과 출력
//		nextInt() 사용하기
		
		String message="세 개의 정수 사이에 공백을 넣어 입력하세요.\n";
		String example="예시)2 6 8\n입력: ";
		int num1=0;
		int num2=0;
		int num3=0;
		String format="%d + %d + %d = %d";
		int result=0;
		
		Scanner sc=new Scanner(System.in);
		
		System.out.print(message);		
		System.out.print(example);
		num1=sc.nextInt();
		num2=sc.nextInt();
		num3=sc.nextInt();
		
		result=num1+num2+num3;
		System.out.printf(format, num1, num2, num3, result);
		
	}
}
```
