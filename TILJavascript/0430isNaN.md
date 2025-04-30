## 2025-04-30

- isNaN 메서드 이해
- 산술, 대입, 비교, 논리, 삼항연산자 학습
- 

## 생각

- isNaN은 변수가 정수나 실수일 때 false가 나오니 헷갈리지 않도록 주의.
- and(&&)와 or(||) 개념을 정확히 기억할 것.
- 

## 만들어 본 코드 - isNaN

```Javascript
const isNaN1=isNaN(100);
const isNaN2=isNaN(10.1);
const isNaN3=isNaN('good');

console.log('isNaN: ', isNaN1);
console.log('isNaN: ', isNaN2);
console.log('isNaN: ', isNaN3);
```

## 만들어 본 코드 - 연산자

```Javascript
let number1=10;
let number2=3;

console.log(number1+number2);
console.log(number1-number2);
console.log(number1*number2);
console.log(number1/number2);
console.log(number1%number2, '\n');

number1 += 1;
number2/=3;
number2*=2;

console.log(number1);
console.log(number2, '\n');

TF=number1<number2;
console.log(TF);
TF=number1>number2;
console.log(TF);
TF=number1<=number2;
console.log(TF);
TF=number1>=number2;
console.log(TF);
TF=number1==number2;
console.log(TF);
TF=number1!=number2;
console.log(TF, '\n');

console.log(number1<1&&number2<1);
console.log(number1<10&&number2<10);
console.log(number1<20&&number2<20, '\n');

console.log(number1<1||number2<1);
console.log(number1<10||number2<10);
console.log(number1<20||number2<20, '\n');

let a=(number1>number2?number1:number2);
console.log(a);
console.log(number1<number2?number1:number2);
```
