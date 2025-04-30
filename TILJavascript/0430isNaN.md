## 2025-04-30

- isNaN 메서드 이해
- 산술, 대입, 비교, 논리, 삼항연산자 학습
- 배열과 길이
- JSON('키워드: 값'을 가지는 데이터 형식)

## 생각

- isNaN은 변수가 정수나 실수일 때 false가 나오니 반대로 인식하지 않도록 주의.
- and(&&)와 or(||) 개념을 정확히 기억할 것.
- 배열을 추가할 수 있는 변수도 const로 지정해도 되는 게 의문이다.
- JSON으로 변수를 선언할 땐 중괄호, 헷갈리지 않도록 해야겠다.

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
TF=numbe
```

## 만들어 본 코드 - 배열

```Javascript
let a=new Array(1, 2, 3);

let b=[4, 5, 6];

console.log(a, b ,'\n');

let c=new Array();
const d=[];

c.push(7, 8, 9);
d.push('Have', 'a', 'nice', 'day');

console.log(c, d, '\n');

a.push(4);
b.push(7, 8);

console.log(a, b, c, d);

const Arr=[];
console.log(Arr[0]);
console.log(Arr.length);
Arr.push("첫째", "둘째", "셋째");
console.log(Arr[1]);
console.log(Arr.length);
```

## 만들어 본 코드 - JSON

```Javascript
const user={};
user.name='Hong Gil Dong';
user.age=20;
user.addr="Seoul";
console.log(user);

const user2={
    name: 'Go Gil Dong',
    age: 22,
    addr:"Busan"
};
console.log(user2);
```
