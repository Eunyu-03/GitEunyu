## 2025-04-27

- class의 구현 순서 이해
- 

## 생각

- 아직 class 구현 순서가 한 번에 확 보이지는 않는다.
- 조금 더 연습이 필요할 것 같다.

## 만들어 본 코드 - class의 구현 순서

```java
package pro0426;

public class Plus {

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
