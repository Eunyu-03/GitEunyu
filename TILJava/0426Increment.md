## 2025-04-26

- 증감식의 이해
- 다른 패키지에 있는 클래스 이용하여 데이터 받기

## 생각

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
