## 2025-04-27

- class의 구현 순서 이해

## 생각

- 아직 class 구현 순서가 잘 보이지 않는다.
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

결과:
Window(1)
Window(2)
Window(30)
House()
Window(3)
f()

## 만들어 본 코드 - class 구현 순서2

```java
package pro0427;

class Bowl {
    Bowl(int marker) {
        System.out.println("Bowl(" + marker + ")");
    }

    void f1(int marker) {
        System.out.println("f1(" + marker + ")");
    }
}

class Table {
    static Bowl bowl1 = new Bowl(1);

    Table() {
        System.out.println("Table()");
        bowl2.f1(1);
    }

    void f2(int marker) {
        System.out.println("f2(" + marker + ")");
    }

    static Bowl bowl2 = new Bowl(2);
}

class Cupboard {
    Bowl bowl3 = new Bowl(3);
    static Bowl bowl4 = new Bowl(4);

    Cupboard() {
        System.out.println("Cupboard()");
        bowl4.f1(2);
    }

    void f3(int marker) {
        System.out.println("f3(" + marker + ")");
    }

    static Bowl bowl5 = new Bowl(5);
}

public class OrderClass2 { 
    public static void main(String[] args) {
        System.out.println("새로운 클래스 Cupboard() 1");
        new Cupboard();
        System.out.println("새로운 클래스 Cupboard() 2");
        new Cupboard();
        table.f2(1);
        cupboard.f3(1); 
    }

    static Table table = new Table();
    static Cupboard cupboard = new Cupboard();
}
```

결과:
Bowl(1)
Bowl(2)
Table()
f1(1)
Bowl(4)
Bowl(5)
Bowl(3)
Cupboard()
f1(2)
새로운 클래스 Cupboard() 1
Bowl(3)
Cupboard()
f1(2)
새로운 클래스 Cupboard() 2
Bowl(3)
Cupboard()
f1(2)
f2(1)
f3(1)
