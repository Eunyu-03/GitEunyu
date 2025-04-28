## 2025-04-27

- class의 구현 순서 이해
- 

## 생각

- 아직 class 구현 순서가 한 번에 확 보이지는 않는다.
- 조금 더 연습이 필요할 것 같다.

## 만들어 본 코드 - class의 구현 순서

```java
package pro0427;

class Window{
	Window(int marker){
		System.out.println("Window("+marker+")");
	}
}

class House{
	Window w1=new Window(1);
	House(){
		System.out.println("House()");
		w3=new Window(3);
	}
	Window w2=new Window(2);
	void f() {
		System.out.println("f()");
	}
	
	Window w3=new Window(30);
}
public class Orderclass {
	public static void main(String[] args) {
		House h=new House();
		h.f();
	}

}

```
