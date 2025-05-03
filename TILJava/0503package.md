## 2025-05-03

- package의 이해
- ㅇ

## 생각

- 라이브러리, 폴더라는 용어를 대입하니 이해하기 쉬웠다.
- ㅇ

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
