## 2025-06-16

# 연산자

기능이 있는 특수문자

- 하나의 식에 여러 종류의 연산자가 사용될 경우 연산되는 순서

1. 최우선 연산자
2. 단항 연산자
3. 산술 연산자
4. 쉬프트 연산자
5. 관계 연산자
6. 논리 연산자
7. 삼항 연산자
8. 대입 연산자

-하나의 식에 동일한 연산자가 여러 개 사용되면 알맞은 방향으로 결합되어 연산되는 성질

- 만들어 본 코드
```java
package operTest;

import java.util.Scanner;

public class OperTest02 {

	public static void main(String[] args) {
		// 두 정수 입력받기
		int num1=0;
		int num2=0;
		String result="";
		
		Scanner sc=new Scanner(System.in);
		
		System.out.println("첫 번째 정수를 입력하세요: ");
		num1=sc.nextInt();
		System.out.println("두 번째 정수를 입력하세요: ");
		num2=sc.nextInt();
		
		result= num1>num2?"더 큰 값: "+num1:
			num1==num2?"두 수가 같습니다.":"더 큰 값: " + num2;
		System.out.println(result);
		
		
	}

}
```

※ 조건식

- 결과가 참 또는 거짓, 둘 중 하나가 나오는 식.
- 
- 조건식은 항상 값으로 봐야 한다.

논리형(boolean): true와 false의 값을 가질 수 있는 자료형

초기값은 false

# 제어문


1. 조건문

if, else if, else

→소괄호 안을 순서대로 판별하여 참일 경우 중괄호 안을 실행

※ 위의 조건식 결과와 상관없이 무조건 검사해야 할 때에는 if를 연달아 쓰고, 위의 조건식이 true라면 검사하지 않아도 될 때에는 else if를 쓴다.

- 만들어 본 코드

```java
package controlStatement;

import java.util.Scanner;

public class ControlStatement {

	public static void main(String[] args) {
		// 두 정수 입력받기
		int num1=0;
		int num2=0;
		String result="";
		
		Scanner sc=new Scanner(System.in);
		
		System.out.println("첫 번째 정수를 입력하세요: ");
		num1=sc.nextInt();
		System.out.println("두 번째 정수를 입력하세요: ");
		num2=sc.nextInt();
		
		if(num1>num2) {
			System.out.println("큰 값: "+num1);
		}
		
		else if(num1<num2) {
			System.out.println("큰 값: "+num2);
		}
		
		else {
			System.out.println("두 수가 같습니다.");
		}
		
	}

}

```

switch(case: 값, default)

소괄호 안의 변수가 case와 동일한 경우 : 다음을 실행, 어떤 case도 해당하지 않는다면 default 실행

※ 반드시 실행할 문장 마지막에 break;를 사용해 준다.

※ 문자열은 사용 가능하지만 실수는 사용할 수 없다.

## 삼항 연산자, if문, switch문의 비교

삼항 연산자: 조건식을 1개만 사용할 때

if문: 조건식에 비교 연산자를 사용하거나 여러 개의 조건식을 논리 연산자로 연결할 때

switch문: 하나의 변수에 여러 경우의 값이 담길 수 있고, 각 값이 같은지 비교할 때 사용

2. 반복문

▶ 반복문

▷for문

int i=0;  i<10;   i+1

for(초기식; 조건식; 증감식){
	실행할 문장;
 
}

- 만들어 본 코드
```java
package controlStatement;

public class ForTest {

	public static void main(String[] args) {
//		for(int i=0; i<10; i=i+1) {
//			System.out.println("정은유");
//		}
		for(int i=10;i>0;i--) {
			System.out.println(11-i+". 정은유");
		}
	}
}
```

▷while문

조건식이 true일 경우 반복

while(조건식){
	실행할 문장;
}

▷do while문

한 번 반복한 이후 조건식이 true일 경우 반복

do{
	실행할 문장;
 
}while(조건식);

※ for문, while문, do~while문 활용 예시
	for문: 몇 번 반복할지 알 때
	while문: 몇 번 반복할지 모를 때
	do while문: 무조건 처음 한 번은 실행해야 할 때

기타 제어문

break: 즉시 해당 중괄호 영역을 탈출한다.
	- if문 안에서 사용 시, if문을 탈출하는 게 아니라 if문을 감싸고 있는 중괄호 영역을 탈출한다.

continue: : 즉시 다음 반복으로 넘어간다.
	-아래의 코드를 실행하지 않기 위해서 사용한다.

