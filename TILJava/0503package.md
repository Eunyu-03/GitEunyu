## 2025-05-03

- package 불러오기
- getter, setter

## 생각

- 라이브러리, 폴더라는 용어를 대입하니 이해하기 쉬웠다.
- public, protected, private, default의 차이를 잘 기억해야겠다.
- get, set 다음에 오는 객체 이름은 무조건 대문자로 시작.
- 주의)초기값이 설정되지 않았다면 setter를 이용해 먼저 값을 넣어 주어야 한다.

## 만들어 본 코드 - package1

```Java
package net.eunyu.util;
import java.io.*;

public class Print{
	public static void print(Object obj){
		System.out.println(obj);
	}
	public static void print(){
		System.out.println();
	}
	public static void printnb(Object obj){
		System.out.print(obj);
	}
	public static PrintStream printf(String format, Object... args){
		return System.out.printf(format, args);
	}
}
```

## 만들어 본 코드 - package2

```Java
import static net.eunyu.util.Print.*;

public class PrintTest{
	public static void main(String[] args){
		print("print util test");
		print(30);
		print(30.23);
	}
}
```

## 만들어 본 코드 - getter, setter

```Java
package pro0503;

class Dog{
	private int size;

	public int getSize() {
		return size;
	}

	public void setSize(int size) {
		this.size = size;
	}
	
	void bark() {
		if(size>60) {
			System.out.println("늑대 크기네요.");
		}
		else if(size>40) {
			System.out.println("일반적인 강아지 크기네요.");
		}
		else {
			System.out.println("고양이 크기의 강아지군요.");
		}
	}
}


class Pro0503 {
	public static void main(String[] args) {
		Dog dog1=new Dog();
		dog1.setSize(50);
		System.out.println("dog1의 크기는: "+dog1.getSize());
		
		dog1.bark();
		
	}
}
```
