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
//		결과를 담을 변수 선언 및 초기화
		String result="";
		
//		스캐너 세팅
		Scanner sc=new Scanner(System.in);
		
//		메세지 출력 및 숫자 입력 받아 각 변수에 저장
		System.out.println("첫 번째 정수를 입력하세요: ");
		num1=sc.nextInt();
		System.out.println("두 번째 정수를 입력하세요: ");
		num2=sc.nextInt();
		
//		두 변수에 지정된 값을 비교, num1이 큰 경우 결과 메세지 저장
		result= num1>num2?"더 큰 값: "+num1:
//			 동일할 경우 메세지 출력, 아닐 경우 num2가 더 크다고 결과 메세지 저장
			num1==num2?"두 수가 같습니다.":"더 큰 값: " + num2;
//		결과 메세지 출력
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
//		수를 담을 변수 두 개 선언 및 초기화
		int num1=0;
		int num2=0;
		
//		스캐너 세팅
		Scanner sc=new Scanner(System.in);
		
//		정수 둘 입력받기
		System.out.println("첫 번째 정수를 입력하세요: ");
		num1=sc.nextInt();
		System.out.println("두 번째 정수를 입력하세요: ");
		num2=sc.nextInt();
		
//		num1이 num2보다 크다면 큰 값으로 num1 출력
		if(num1>num2) {
			System.out.println("큰 값: "+num1);
		}
		
//		num1이 num2보다 작다면 큰 값으로 num2 출력
		else if(num1<num2) {
			System.out.println("큰 값: "+num2);
		}
		
//		둘 다 아니라면 같다는 메세지 출력
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

import java.util.Scanner;

public class ForTask {

	public static void main(String[] args) {
//		0~99까지 i+1을 100번 반복하여 출력
		for(int i=0; i<100; i++) {
			System.out.println(i+1);
		}
//		0~99까지 100-i를 100번 반복하여 출력
		for(int i=0; i<100; i++) {
			System.out.println(100-i);
		}
//		0~49까지 (i+1)*2를 50번 반복하여 출력
		for(int i=0; i<50; i++) {
			System.out.println((i+1)*2);
		}
		
//		i+1이 짝수일 때 i+1을 출력, 100번 반복
		for(int i=0; i<100; i++) {
			if((i+1)%2==0) {
				System.out.println(i+1);
			}
		}
//		합을 담을 j 선언
		int j=0;
//		j+i+1을 j에 담고 0~9까지 9번 반복
		for(int i=0; i<10; i++) {
			j+=i+1;
//			잘 들어가고 있는지 확인용 출력, 주석 처리함
//			System.out.println("i="+i+", j="+j);
		}
//		j의 값 출력
		System.out.println("1~10까지의 합: "+j);
		
//		입력받을 변수 선언
		int num1=0;
//		스캐너 세팅, 메세지 출력 후 num1에 수 입력받기
		Scanner sc=new Scanner(System.in);
		System.out.println("수를 입력하세요: ");
		num1=sc.nextInt();
		
//		num-1에서 1까지 num-1번 반복(기존에 num1값은 이미 들어가 있기 때문)
		for(int num2=num1-1; num2>0; num2--) {
//			num1에 num2(=num1-1)+기존 num1 담기
			num1+=num2;
//			확인용 출력, 주석 처리함
//			System.out.println("num1="+num1+", num2="+num2);
		}
		
//		1~num1까지의 합 출력
		System.out.println("1~입력한 수까지의 합: "+num1);
		
//		아스키 코드로 A는 65, 따라서 0~6까지 i+65를 5번 반복하려 출력
		for(int i=0; i<6; i++) {
			System.out.println((char)(i+65));
		}
		
//		A~F까지 중 C를 제외하고 아스키코드 넘버를 담을 변수 result 선언
		int result1=0;
//		0~4까지 5번 반복
		for(int i=0; i<5; i++) {
//			result가 2보다 작을 때(A, B) 65를 더하고 2보다 같거나 클 때(C, D, E) 65를 더하여 D, E, F의 아스키 코드를 담음
			result1=i<2?i+65:i+66;
//			문자로 형변환하여 출력
			System.out.println((char)result1);
		}
		
//		012301230123을 출력하기 위해 12번 반복
		for(int i=0; i<12; i++) {
//			4로 나누면 나머지가 0, 1, 2, 3 반복이므로 4로 나눈 나머지 값을 출력
			System.out.print(i%4+" ");
		}
//		가독성을 위해 한 줄 띄어 씀
		System.out.println("\n");
		
//		aBcDeF...Z 형태로 출력하기 위해 26번 반복
		for(int k=0; k<26; k++) {
//			아스키 코드 넘버를 담을 변수 선언
			int result2=0;
//			나머지가 0이라면(홀수, a c e등 소문자) 97을 더하고 나머지가 1이라면(짝수, B D F등 대문자) 65를 더하여 출력
			result2=k+(k%2==0?97:65);
			System.out.print((char)result2);
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

※ 기타 제어문

break: 즉시 해당 중괄호 영역을 탈출한다.
	- if문 안에서 사용 시, if문을 탈출하는 게 아니라 if문을 감싸고 있는 중괄호 영역을 탈출한다.

continue: : 즉시 다음 반복으로 넘어간다.
	-아래의 코드를 실행하지 않기 위해서 사용한다.

