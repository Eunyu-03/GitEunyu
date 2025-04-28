# Java 공부 기록

## 2025-04-19

- Java의 기본 틀 학습
- print, println 메서드 이해

## 느낀 점

- 처음 배우는 입장에서 메서드와 public의 개념을 이해하는 데에 시간을 많이 할애했다.
- class에 관하여 정확히 알고 싶다.

## 만들어 본 코드

```java
package pro0419;

public class FirstTest {

    public static void main(String[] args) {
        System.out.println("Java");
        System.out.println("Java");
    }
}
```

---

## 2025-04-20

- class와 객체의 개념 이해
- 변수의 데이터 형식 구분
- 연산자, if, else if 구문 적용해 보기
- nextInt(), nextLine() 메서드 사용해 보기

## 느낀 점

- 계산기를 만들며 여러 구문을 직접 사용해 보니 이해하기 쉬웠다.
- 더 간결한 형태로 만들 수 있지 않을까 싶다.
- AI가 준 코드를 그대로 복사하는 게 아닌 하나하나 질문하며 배우는 과정이 훨씬 도움이 되는 것 같다.

## 만들어 본 코드

```java
package pro0420;

import java.util.Scanner;

public class Calculator {
	public static void main(String[] args) {
		int num1, num2;
		String yeon;
		double result;
		
		Scanner sc=new Scanner(System.in); //Scanner class의 객체 생성
		
		System.out.print("첫 번째 정수를 입력하세요: ");
		num1=sc.nextInt();
		sc.nextLine();
		//정수를 입력
		
		System.out.print("연산을 선택하세요(+, -, *, /): ");
		yeon=sc.nextLine();
		
		System.out.print("두 번째 정수를 입력하세요: ");
		num2=sc.nextInt();
		if(num2==0&&yeon.equals("/")) {
			System.out.print("0으로 나눌 수 없습니다.");
		}
		
		else {
			if(yeon.equals("+")) {
				result=num1+num2;
				System.out.println(num1+"+"+num2+"="+result);
			}
			
			else if(yeon.equals("-")) {
				result=num1-num2;
				System.out.println(num1+"-"+num2+"="+result);
			}
			
			else if(yeon.equals("*")) {
				result=num1*num2;
				System.out.println(num1+"*"+num2+"="+result);
			}
			
			else if(yeon.equals("/")) {
				result=(double)num1/num2;
				System.out.println(num1+"/"+num2+"="+result);
			}
			
			else {
				System.out.print("잘못 입력하셨습니다.");
			}
		}
		sc.close();
	}

}
```

---

## 2025-04-26

- 증감식의 이해
- 다른 패키지에 있는 클래스 이용하여 데이터 받기

## 느낀 점

- ++이 변수 이름의 앞에 붙는지 뒤에 붙는지에 따라 연산 후 대입인지 대입 후 연산인지 구분할 수 있게 되었다.
- java.util 패키지에 있는 Date 클래스를 이용하는 것 외에도,
- 어떤 클래스를 가지고 올 수 있는지, java에서 이용할 수 있는 클래스가 어느 종류가 더 있는지 궁금하다.

## 만들어 본 코드 - 증감식

```java
package pro0426;

public class plus {

	public static void main(String[] args) {
		int num1=20, num2;
		
		num2=num1++;
		System.out.printf("%d \n", num2);
		
		num2=++num1;
		System.out.printf("%d \n", num2);
		
		for(int i=0; i<=10; i++) {
			int i1=i++;
			System.out.println(i1);//0~10의 짝수 출력(println 이후 ++)
		}
		
		for(int i=0; i<=10; ++i) {
			int i2=++i;
			System.out.println(i2);//1~11의 홀수 출력(++하고 println)
		}


	}

}
```

## 만들어 본 코드 - 날짜

```java
package pro0426;

import java.util.*;

/** 외부 데이터를 받아 만들어 보는
   * 자바 문서
   *이 프로그램은 날짜를 보여준다.
*/

public class HelloDate{
   /**자바 application의 실행이 시작되는 곳임
      *param args String 배열 타입의 인자 선언
      *@throws exception 예외 throw하지 않음
   */
   public static void main(String[] args){
      System.out.println("안녕하세요, 오늘의 날짜는: ");
      System.out.print(new Date());
      System.out.println("입니다.");
      System.out.println("감사합니다.");
   }
}
```
