# 손상배 [201840119]
## 2021-05-11
>오늘 배운내용 요약<br>
>요약 : 
>
## 기본 자료형

```jsx
let n = 273;
let s = '안녕하세요';
let b = true;

console.log(typeof n);
console.log(typeof s);
console.log(typeof b);

//출력
//number
//string
//boolean
```

### Number 객체

```jsx
let number = new Number2(27.11122);

console.log(number.toFixed(1));
//출력값 27.1
console.log(number.toFixed(4));
//출력값 27.1112
```

### String 객체

```jsx
let string = 'Hello World!';

if(string.indexOf('Hello')>=0){
	console.log('hello JS')
}
```

### Date 객체

```jsx
//현재 시간을 기반으로 Date객체 생성
let dateA = new Date();
console.log(dateA);

//유닉스타임(1970년 1월 1일 0시 00분 00초부터 경과한 밀리초 )
let dateB = new Date(692281800000);

//문자열 기반 Date객체 생성
let dateC = new Date("December 9, 1991 21:30:00");
```

### 시간 더하기

```jsx
let date = new Date();

console.log(date);

//시간더함
date.setFullYear(date.getFullYear()+1);
date.setMonth(date.getMonth()+2);
date.setDate(date.getDate()+3);

console.log(date);
```

### 배열

```jsx
let array =[{
	name:'고구마',
	price:1000
},{
	name:'감자',
	price:500
},{
	name:'바나나',
	price:1500
}];
```

### 기본예외처리

사전에 해당 데이터가 undefined인지 조건문으로 확인

```jsx
function callTenTimes(callback){
	if (callback){
		for(let i=0;i<10;i++){
		callback();
		}
	}else {
		console.log('매개변수 callback에 지정되지 않았습니다');
	}
}
// 정상 실행
callTenTimes(function(){console.log('안녕하세요')});

//예외 발생
callTentimes();
```

### 고급 예외 처리

```jsx
try{
	//예외가 발생하면
}catch(exception){
	//catch문에서 처리
} finally{
	//무조건 실행
}
```

### 강제 예외 발생

throw error;

```jsx
//예외 객체를 만듬
const error = new Error('메시지');
error.name = '내마음대로 오류';
error.message = '오류의 메시지';

//예외 발생
throw error;
```

---
# 손상배 [201840119]
## 2021-05-04
>오늘 배운내용 요약<br>
>요약 : 
>

### 객체배열

```jsx
let prducts ={
	{name : '바나나',price:1200},
	{name : '사과',price:2000},
	{name : '배',price:3000},
	{name : '고구마',price:700},
	{name : '감자',price:600}
};
```

### 함수를 외부로 내보낸 형태

```jsx
let products ={
	{name : '바나나',price:1200},
	{name : '사과',price:2000},
	{name : '배',price:3000},
	{name : '고구마',price:700},
	{name : '감자',price:600}
}
//함수 선언
function printProduct(product){
	console.log(`${product.name}의 가격은 ${product.price}원 입니다`);
}
```

### 생성자 함수를 사용한  객체생성

```jsx
//생성자 함수
funtion Product(name,price){
	this.name = name;
	this.price = price;

}
//객체 생성
let product = new Product('바나나',1200);

console.log(Product);
```

### 프로토 타입

```jsx
fuction Product(name,price){
	this.name = name;
	this.price = price;
}

//프로토 타입에 메소드 선언

Product.prototype.print = function(){
	console.log(` ${product.name}의 가격은 ${product.price}원 입니다`)}

//객체 생성
let product = new Product('바나나', 1200);

product.print();
```


# 손상배 [201840119]
## 2021-04-27
>오늘 배운내용 요약<br>
>요약 : 
>## 객체 접근

product['제품명']

product['유형']

product['성분']

product['원산지']

---

## 객체 기본

```jsx
let object ={
	name:'바나나',
	price:1200
}
console.log(object.name);
console.log(object.price);

```

요소 :내부에 있는 값 하나하나

속성 : 객체 내부에 있는 값 하나하나

메소드 :객체의 속성중 자료형이 함수인 속성

### 메소드 내의 this 키워드

```jsx
let object ={
	name='바나나';
	price='1200',
	print:function(){
		console.log(`${this.name}의 가격은 ${this.price}원 입니다 `)
}

};

object.print();
```


# 손상배 [201840119]
## 2021-04-13
>오늘 배운내용 요약<br>
>요약 : 
>## 익명 함수

이름을 붙이지 않고 함수 생성
함수를 호출하면 함수 내부의 코드 덩어리가 모두 실행

let <변수 이름> = function(){ };

```jsx
let foo = function(){

  console.log("첫줄");
  console.log("둘쨰 줄");
}

foo();
console.log(foo);
//무명함수 ES6 이전에 사용
```

---

### 선언적 함수

```jsx
function foo(){
  console.log("첫줄");
  console.log("둘째줄");
}

foo();
//선언적 함수
```

---



### 화살표 함수

```jsx
let foo = ()=>{

  console.log("첫줄");
  console.log("둘쨰 줄");
}

foo();
console.log(foo);
```

---

## 함수의 기본형태

function <함수이름>(매개변수){

<함수코드>

return <리턴값> }

```jsx
function multiply(x,y){
  return x*y;

}
console.log(multiply(10,20));
console.log(multiply(20,6));
```


```jsx
function print(x){

  console.log(`"${x}"라고 말했습니다.`);
}
print("안녕하세요");
```


---

## 리턴 함수

```jsx
function sum(min,max){
  let output = 0;
  for(let i =min;i<=max;i++){
    output +=i;
  }
  return output;
}

console.log(sum(1,100));
```

***출력:* 5050**

```jsx
function print(name, count){
  console.log(`${name}가 ${count}개 있습니다.`);

}
print("사과",10);
```

***출력: 사과가 10개 있습니다***

---

## 콜백 함수

```jsx
function call(cb){
  for(let i =0;i<10;i++){
    cb();
  }
}
call(function(){
  console.log("함수호출");
})
```


---

## 숫자 변환 함수

parseInt() : 문자열을 정수로 반환

parseFloat() : 정수를 문자열로 반환

```jsx
let A = "52"
let B = "52.273"
let C = "123가나다";

console.log(parseInt(A));

console.log(parseInt(B));
console.log(parseFloat(B));

console.log(parseInt(C));
```



---

## 표준 내장 함수

특정 시간 후에 또는 특정 시간마다 어떤 일을 할 때 사용

시간은 밀리초로 지정. 1초 = 1000밀리초

```jsx
setTimeout(function(){
  console.log("1초지남")
},1000);
```

***1초지날때 한번출력***

```jsx
setInterval(()=>{
  console.log("1초지남")
},1000);
```

***1초 지날 때마다 출력***



# 손상배 [201840119]
## 2021-04-06
>오늘 배운내용 요약<br>
>요약 : 
## (역) for 반복문

```jsx
역 for 반복문

let array = [1, 2, 3, 4, 5, 6];
//배열 생성

for (let i = array.length -1; i>=0; i--){
	console.log(array[i]);
}
```

 tab키 위에있는 ` = 문자와 변수를 같이 넣고싶을때 ex)     ``console.log(${i}번째 요소:)``

    

## 이중 for문

```jsx
let output = "";

for (let i = 0; i<5;i++){
  for (let j =0;j<i+1; j++){
    output += "*";
  }
 output += "\n"; 
}
console.log(output);
```



### 삼각형 찍기

```jsx
let op="";

for(i=0;i<10;i++){
  for(j=0;j<10-i;j++){
    op+=" ";
}
for(let j=0;j< i+1;j++){
  op += "*";
}
for(let j=1; j<i+1;j++){
  op += "*";
}
op+="\n";
}

console.log(op);
```


---

## While 문

```jsx
let array =[1,31,273,57,8,11];
let op;
let i =0;

while(true){
  if (array[i]%2 ==0){
    op = array[i];
    break;
  }
  i++ // i=i+1;
}
  console.log(`처음 발견한 짝수는 ${op}입니다`);
```

***출력 :  처음 발견한 짝수는 8입니다***

---

**push**는 배열의 끝에 원하는 값을 추가해주는 함수  **foo.push(1,2,3);**

**pop**은 배열의 마지막 주소에 있는 값을 제거해주는 함수. **foo.pop();**

**shift**는 배열의 첫번째 주소에 있는 값을 제거한 후에 반환해주는 함수**.foo.shift():**

**push**와 **pop**을 이용하면 **stack**으로 이용할 수 있다.

**push**와 **shift**를 이용하면 **quene**로 이용할 수 있다.


# 손상배 [201840119]
## 2021-03-30
>오늘 배운내용 요약<br>
>요약 : ## **if 문**

```jsx
let date = new Date();
let hours = date.getHours();

if (hours<11){
	console.log("아침 먹을 시간입니다");
} else if (hours<15) {
		console.log("점심 먹을 시간입니다");
}else {
	console.log("저녁 먹을 시간입니다");
}
```

## Switch 조건문

```jsx
let input = 32;

switch(input%2){
    case 0:
        console.log("짝수");
        break;

    case 1:
        console.log("홀수");
        break;
    default:
        console.log("정수가 아닙니다");
        break;
}
```

```jsx
let date = new Date();
console.log(date.getMonth());
switch (date.getMonth()+1){ 
    case 12:
    case 1 :
    case 2 :
        console.log("겨울");
        break;
    case 3 :
    case 4 :
    case 5 :
        console.log("봄");
        break;
    case 6:
    case 7 :
    case 8 :
        console.log("여름");
        break;    
    case 9 :
    case 10 :
    case 11 :
        console.log("가을");
        break;
    default : console.log("정수x");
							break; 

}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script>
        let input = prompt("입력해주세요");
        console.log(input);

    </script>
</head>
<body>
    
</body>
</html>
```

```jsx
let date = new Date();
let hours = date.getHours(); 

if (hours<11){
	console.log("아침 먹을 시간입니다");
} else if (hours<15) {
		console.log("점심 먹을 시간입니다");
}else {
	console.log("저녁 먹을 시간입니다");
}
```

## 배열

## while 반복문

```jsx
let i = 0;
let array =[52,273,32,65,103];
//반복을 수행합니다
while(i < array.length){
//출력
console.log(i + "번째 출력" + array[i]);
//탈출 변수 
i++;
}
```

## for 반복문

```jsx
let output = 0;

for (let i =0;i<= 100; i++){
	output += i;
}
console.log(output);

// 1부터 100까지 더하기
```

## 2021-03-23
>오늘 배운내용 요약<br>
>요약 : 논리 연산자 

## 2021-03-16
>오늘 배운 내용 요약<br>
>요약 : nord.js설치함


