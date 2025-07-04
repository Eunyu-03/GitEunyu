## 2025-06-24
# 추상 클래스

- 필드 안에 구현이 안 된 메소드가 선언되어 있는 클래스를 추상 클래스라고 한다.
- 이때 구현되지 않은 메소드를 추상 메소드라고 부른다.
- 즉, 추상 클래스에 추상 메소드를 선언할 수 있다.
- 반드시 재정의를 통해 구현을 해야 메모리에 할당되기 때문에 "강제성"을 위해 사용한다.

# 추상 클래스 선언
	abstract class 클래스명 {
		abstract 리턴타입 메소드명(매개변수, ...);

		//일반 메소드도 선언 가능하다.
		리턴타입 메소드명 (매개변수, ...){
		}	
	}

# 만들어 본 코드
```java
package abstractTest;

public abstract class Electronics {
	
//	무조건 재정의해라
	public abstract void on();
	
//	재정의는 선택
	public void printProduct() {
		System.out.println("전자 제품");
	}
	
//	재정의 절대 하지 마라
	public final void sos() {
		System.out.println("긴급 전화 119 연락");
	}
}
```
```java
package abstractTest;

public class Refregerator extends Electronics {
	public void on() {
		System.out.println("켰어용!");
	}
}
```
```java
package abstractTest;

public class Gogo {
	public static void main(String[] args) {
		Refregerator ref= new Refregerator();
		
		ref.on();
		ref.printProduct();
		ref.sos();
	}
}
```

# 인터페이스(틀)
- 추상 클래스를 고도화시킨 문법, 상수와 추상 메소드만 존재한다.
- 구현은 지정한 클래스에서 진행하고, 인터페이스를 다른 클래스에 지정할 때에는 implements 키워드를 사용한다.

# 추상 클래스와 인터페이스 간의 관계
- 인터페이스를 클래스에 바로 지정하면 모든 메소드에 강제성이 부여되기 때문에 전부 다 구현해야 한다.
- 하지만 일반적인 상황에서는 필요한 메소드를 골라서 재정의한다.
- 따라서 인터페이스를 직접 지정하지 않고 다른 클래스에 지정 후 구현해 놓는다면, 강제성이 소멸되고 이로 인해 골라서 재정의할 수 있게 된다.
- 이때 중간에서 강제성을 없애주는 클래스를 추상 클래스로 선언하기로 하며, 추상 클래스 이름 뒤에는 Adapter를 붙여서 목적을 알려준다.

# 인터페이스의 특징
1. 인터페이스도 자료형(타입)이다. 인터페이스를 구현한 클래스는 모두 인터페이스 자료형이다.
2. 인터페이스끼리 필드를 주고 받을 때에는 extends 키워드를 사용한다.
3. default 메소드를 사용하면, 인터페이스 내부에서 일반 메소드 선언이 가능하다.

# 만들어 본 코드
```java
package interfaceTest;

public interface Animal {
	int eyes=2;
	final static int nose=1;
	
	void showHands();
	abstract void sitDown();
	void poop();
	void waitNow();
}
```
```java
package interfaceTest;

public class Puppy implements Animal {

	@Override
	public void showHands() {
		System.out.println("멍");
	}

	@Override
	public void sitDown() {
		System.out.println("멍멍");
	}

	@Override
	public void poop() {
		System.out.println("멍멍멍");
	}

	@Override
	public void waitNow() {
		System.out.println("ㅜㅜ");
	}
}
```
```java
package interfaceTest;

public class Cat implements Animal {

	@Override
	public void showHands() {
		System.out.println("?");
	}

	@Override
	public void sitDown() {
		System.out.println("??");
	}

	@Override
	public void poop() {
		System.out.println("냥");
	}

	@Override
	public void waitNow() {
		System.out.println("???");
	}

}
```
```java
package interfaceTest;

public class Tiger extends AnimalAdapter {
	
	@Override
	public void poop() {
		System.out.println("어흥");
	}
}
```
```java
package interfaceTest;

public abstract class AnimalAdapter implements Animal {

	@Override
	public void showHands() {
		// TODO Auto-generated method stub

	}

	@Override
	public void sitDown() {
		// TODO Auto-generated method stub

	}

	@Override
	public void waitNow() {
		// TODO Auto-generated method stub

	}

}
```
```java
package interfaceTest;

public class Simul {
	public static void main(String[] args) {
		Puppy puppy=new Puppy();
		Cat kitty=new Cat();
		Tiger tiny=new Tiger();
		
		puppy.showHands();
		puppy.poop();
		puppy.sitDown();
		
		kitty.showHands();
		kitty.poop();
		kitty.sitDown();
		
//		아무것도 출력되지 않음
		tiny.showHands();
		tiny.poop();
//		아무것도 출력되지 않음
		tiny.sitDown();
	}
}
```

# 함수형 인터페이스(Functional Interface)
- 인터페이스 중 추상 메소드를 하나만 가지고 있는 인터페이스를 함수형 인터페이스라고 한다.
- 이때 @FuntionalInterface를 인터페이스 위에 작성하여 단 하나의 추상 메소드만 선언하도록 제한한다.

# 람다식(Lambda Expression)
- 함수형 인터페이스에서는 한 개의 추상 메소드만 존재하기 때문에 구현 시 메소드 이름이 딱히 필요가 없다.
- 람다식은 이름이 없는 메소드로서, 값처럼 사용이 가능하고 당연히 매개변수로도 전달이 가능하다.
- 따라서 람다식을 익명 메소드(Anonymous Method)라고도 부른다.

# 람다식 문법
1. (매개변수 형식 나열, ...) -> 리턴값;
2. (매개변수 형식 나열, ...) -> {실행할 문장; return 리턴값;};
3. 매개변수 - 리턴값;
4. 매개변수 -> {실행할 문장; return 리턴값;};

# 만들어 본 코드
```java
package lambdaTask;

@FunctionalInterface
public abstract interface PrintName {
	public String getFullName(String firstname, String lastname);
}
```
```java
package lambdaTask;

public class PrintNameTest {
	void printFullName(PrintName printName, String firstName, String lastName) {
		System.out.println(printName.getFullName(firstName, lastName));
	}

	public static void main(String[] args) {
		PrintNameTest printNameTest = new PrintNameTest();
		printNameTest.printFullName((f, l) -> l + f, "은유", "정");
	}
}
```
# 컴파일 순서
1. 디버그: 오류 검사
2. 빌드: 프로그램 생성
3. 링크: 생성된 프로그램까지의 경로를 저장한다.
4. 실행

# 예외 처리
- 컴파일 오류: 빨간 줄 오류
- 빌드 오류: 실행하자마자 오류
- 런타임 오류: 잘 실행되다가 갑자기 오류, 사용자의 입력 및 외부 요인에 의한 오류

※ 런타임 오류는 제어문으로 막을 수 없는 경우가 생긴다. 이때, 예외 처리 문법으로 해결할 수 있다.

# 예외 처리 문법
	try{
		오류가 발생할 수 있는 문장;

	} catch(예외 이름 객체면){
		오류 발생 시 실행할 문장;

	} catch(예외 이름 객체면){
		오류 발생 시 실행할 문장;

	} catch(예외 이름 객체면){
		오류 발생 시 실행할 문장;

	}
	...
	} finally{

	}
