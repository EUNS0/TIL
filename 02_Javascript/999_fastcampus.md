# Javascript - fast campus


```js
엔진

* V8 - Chrome, Opera
* SpiderMonkey - Firefox
* Trident or Chakra - IE
* ChakraCore - Microsoft Edge
* SquirrelFish - Safari

```


## Expression (표현식)
- 값을 만들어내는 간단한 코드
```js
예시
* ture = ture
* 26 = 26
* 1000+900+90+4 = 1994
* "Anna" = Anna
* "Hello" + "Javascript" = Hello Javascript
```
- 표현식은 값을 만들어내기 때문에 함수의 "인자"로 사용할 수 있다.


## Statement (문장)
```js
ture;
26;
Anna; 
var name = “Mark”;
alert(’’);
```
- 하나 혹은 여러 개의 표현식이 모여 -> "문장"을 이룸 (모든 표현식은 문장이 될 수 있음.)
- 보통 문장의 끝에는 세미콜론; 을 붙임
- 한 줄에 문장이 하나인 경우 ; 붙이지 않아도 됨. (관례적으로 붙이는 것)
- 한 줄에 여러 문장일 경우 ;로 구분
- 마지막 문장은 ; 붙지이 않아도 문제 없음.
- 마지막 문장의 결과가 반환됨.
- 조건문(if), 반복문(for)도 문장이며, 마지막 {} 뒤에는 ; 붙이지 않음



## 키워드와 예약어
### Keyword (키워드)
- Javascript에서 특정한 목적을 위해 사용하는 언어
- 이러한 키워드들은 예약어로 지정되어 있음
```js
  var name = 'Mark';
  //var: 변수를 선언할 때 사용하는 키워드
```


### Reserved Words (예약어)
- 프로그램을 작성할 때, 변수명, 함수명 등 이름으로 사용할 수 없는 단어
```js
  var return = '변수명'; // return은 예약어 -> 변수명 사용 X
  function for() {} // for는 예약어 -> 함수명으로 사용 X
```


## 식별자
- 코드 내의 변수, 함수 혹은 속성을 식별하는 문자열
- 대소문자를 구별함 -> myName / myname (다름)
- '유니코드 문자(한글)', '$', '_', '숫자0~9' 사용 
    숫자로 시작 불가 / 유니코드 문자는 잘 사용안함
- '예약어'는 사용할 수 없고 '공백 문자'도 사용할 수 없음



## Variable(변수)와 Constant(상수)
- 어떤 값을 메모리에 보관하게 해주는 보관소 역할 ...


### 상수
- const
- sum 이라는 상수를 선언, 값 바뀌지 않음.
```js
    const sum = 5 + 10

    if (sum % 3 === 0) {
        console.log('야호3');
    }

    if (sum % 5 === 0) {
        console.log('야호5');
    }
```


### 변수
- let 
- 상황에 따라 값을 재 할당 할 수 있는 것
```js
    function() {
        const sum = 5 + 10;
        let result = false;  // 재 할당 할 수 있는 let

        if (sum % 3 === 0) {
            console.log('야호3');
            result = ture; // flase를 기본으로 두고 이런 상황일때만 true 되도록 재 할당
        }

        console.log(result)
    }
```


### 변수의 유효 범위 ( scope of variables )
- 변수가 선언되고 사용되는 공간이 어느 부분에서 유효한지 정하는 규칙
- const, let을 주로 선언하게 되는데 이는 블록 스코프의 범위를 가진다.
    + 블록은 {} 안에 있는 것
    + 밖에 있는 것은 오류
        단, 밖에 선언되어 있는 것을 블록 안에 가져와서 쓰게 되면 그 값을 인지함.
    + var의 유효범위: 함수 스코프 -> function() {}



### var와 호이스팅
- 호이스팅: 선언문만 위로 올라가게 되는 현상 ( var에서만 발생 )
```js
    console.log(name);  // undefined

    name = 'Mark'; 

    console.log(name);  // Mark

    var name = 'EunSeo'; 
```
```js
    var name; 

    console.log(name); 

    name = 'Mark';

    console.log(name);

    name = 'EunSeo';
```
- 제일 아래의 선언문의 'var name' 선언부만 호이스팅 되어 위로 올라감
- let 등을 사용할 때는 실행문 아래에 선언하는 것이 오류이기 때문에 var에서만 나타남



### 자료형
- 동적 타이핑: 변수의 타입이 계속 바뀔 수 있기 때문
    변수가 가지는 고정 타입이 없다.
    + 데이터 타입
        - 기본타입
        - 객체



## 조건문 If
* Falsy: false로 평가되는 값
    - false: 논리적으로 거짓을 나타내는 boolean 값 *boolean이란 참 또는 거짓 중 하나를 나타내는 자료형*
    - 0: 숫자 0은 거짓으로 간주됨
    - 빈 문자열 (""): 아무런 문자를 포함하지 않은 빈 문자열은 거짓으로 간주됨
    - null: 값이 없을은 나타내는 특별한 값으로 거짓으로 간주됨
    - undefined: 값이 정의되지 않음을 나타내는 특별한 값으로 거짓으로 간주됨
    - NaN: 숫자가 아님(Not a Number)을 나타내는 특별한 값으로 거짓으로 간주됨
    - document.all: 이전에는 웹 브라우저에서 사용되었으며, 현재는 잘 사용되지 않지만 브라우저 환경에서는 
        거짓으로 간주


* Truthy
    - true: 논리적으로 참을 나타내는 bolean 값
    - 숫자: 0을 제외한 모든 숫자 
    - 문자열: 빈 문제열을 제외한, 모든 문자열
    - 배열: 빈 배열을 제외한 모든 배열
    - 객체: 빈 객체를 제외한 모든 객체
    - 함수: 함수는 항상 ture
    - 정규 표현식: 정규 표현싱을 항상  


















