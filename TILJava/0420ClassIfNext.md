## 2025-04-20

- class와 객체의 개념 이해
- 변수의 데이터 형식 구분
- 연산자, if, else if 구문 적용해 보기
- nextInt(), nextLine() 메서드 사용해 보기

## 생각

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
