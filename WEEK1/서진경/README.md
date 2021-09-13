# 자바스크립트 1주차
## 드림코딩 엘리
------------
### 1. 자바스크립트 배우기 전 꼭 봐야할 영상 | 자바스크립트의 역사와 현재 그리고 미래

#### 1-1. 자바스크립트 탄생 배경?
- 1993년 Mosaic Web Browser
- 1994년 Netscape Navigator (정적인 웹사이트)
- 1994년, 9월 LiveScript => JavaScript (동적인 웹사이트)
- 1995년 Netscape Navigator를 이해할 수 있는 "JavaScript" 엔진 출시
- 1997년, 7월 ECMAScript 1 language specification (공식 문서 출시)
- 1998년 ECMAScript 2
- 1999년 ECMAScript 3 (추가 기능: error handling)
- 2000년 ECMAScript 4 (추가 기능: 관계 연산자)
- 2004년 mozilla사의 Firefox 출시, AJAX 도입 (비동기적 데이터 처리)
    - 브라우저 공식화 논쟁: mozilla의 Firefox vs Netscape의 Netscape Navigator vs Microsoft의 Internet Explorer
    - 개발자 커뮤니티에서 탄생: 브라우저 jQuery, dojo, mootools
 - 2008년 Chrome 브라우저 출시 (+JIT: 자바스크립트를 실행하는 속도가 엄청 빠른 강력한 엔진) 
- 2008년, 7월 브라우저들 간의 표준화 추진
- 2009년 ECMAScript 5
- 2015년 ECMAScript 6 (ex.default parameter, class, arrow function, const, let)
- 2016년 ECMAScript 7
- 2017년 ECMAScript 8
 - 2018년 ECMAScript 9
- 2019년 ECMAScript 10

#### 1-2. JavaScript는 어떤 문제를 해결하기 위해 만들어 졌는가?
개발자들이 다른 브라우저의 다양한 구현 사항을 신경쓰지 않기 위해서 만들어 짐

#### 1-3. Javascript Engines
- Chrome => V8
- Firefox => SpiderMonkey
- Safari => JSCore
- MS Edge => Chakra
- Opera => Carakan
- Adobe Flash => Tamarin

#### 1-4. 현재 가고 있는 방향?
SPA(Single Page Application): 하나의 페이지 안에서 데이터를 받아와서 필요한 부분만 부분적으로 업데이트하기 위해 개발
- React
- Angular
- Vue

#### 1-5. JavaScript의 활용 분야? (JavaScirpt의 상용화에 따라 다양한 활용 가능 분야 증가)
- back-end: node.js
- mobile: react.Native
- desktop: electron    
------------
### 2. 자바스크립트 2. 콘솔에 출력, script async와 defer의 차이점 및 앞으로 자바스크립트 공부 방향 | 프론트엔드 개발자 입문편

2-1. 자바스크립트 공식사이트? 
<br>
developer.mozilla.org (MDN)

2-2. async vs defer (html에서 JavaScript를 포함할 때, 어떤 방식이 더 효율적인지)
1. head 안에 js 파일 포함
    - 단점: js 파일이 어마어마하게 크고, 인터넷도 느릴 경우 => 사용자가 웹사이트를 보는 데까지 많은 시간이 소요됨
2. body 안 끝 부분에 js 파일 포함
    - 단점: 사용자가 기본적인 웹사이트는 빨리 볼 수 있지만, 웹사이트가 js에 굉장히 의존적이라면 사용자는 웹사이트에서 의미있는 행동을 하지 못 함 (fetch 시간과 executing 시간을 기다려야 하기 때문)
3. head안에 asyn 속성 값 사용하여 js 파일 포함
    - 장점: 병렬적인 다운로드이기 때문에 body 끝에 사용하는 것보다는 다운로드 받는 시간을 절약할 수 있음
    - 단점: HTML을 parsing하는 동안에 언제든지 js를 실행하기 위해서 멈출 수 있기 때문에 사용자가 페이지를 보는데 시간이 오래 걸릴 수 있음
4. head안에 defer 속성 값을 이용하여 js 파일 포함
    - 가장 좋은 옵션: HTML을 parsing 하는 동안 필요한 JavaScript를 다 다운로드 받아놓고, HTML을 parsing 먼저해서 사용자에게 page를 보여준 다음 JavaScript를 실행하기 때문
------------
### 3. 자바스크립트 3. 데이터타입, data types, let vs var, hoisting | 프론트엔드 개발자 입문편
    // 1. Use strict
    // added in ES 5
    // use this for Vanila Javascript.
    'use strict';

    // 2. Variable (Mutable 데이터 타입: 값이 계속 변경될 수 있는 데이터)
    // let (added in ES6) 
    let globalName = 'global name';
    {
        let name = 'ellie';
        console.log(name);
        name = 'hello';
        console.log(name);
    }
    console.log(name);
    console.log(globalName);

    // var (don't ever use this!)
    // var hoisting (move declaration form bottom to top)
    // has no block scope
    {
        age = 4;
        var age;
    }
    console.log(age);

    // 3. Constant (Immutable 데이터 타입: 값이 고정되는 데이터)
    // use const whenever possible.
    // only use let if variable needs to change.

    // favor immutable data type always for a few reasons:
    // - security
    // - thread safety
    // - reduce human mistakes
    const daysInWeek = 8;
    const maxNumber = 5;

    // 4. Variable types
    // primitive, single item: number, string, boolean, null, undefined, symbol
    // object, box contatiner
    // function, first-class function
    const count = 17; // integer
    const size = 17.1; // decimal number
    console.log(`value: ${count}, type: ${typeof count}`);
    console.log(`value: ${size}, type: ${typeof size}`);

    // number = special numeric values: infinity, -infinity, NaN
    const infinity = 1 / 0;
    const negativeInfinity = -1 / 0;
    const nAn = 'not a number' / 2;
    console.log(infinity);
    console.log(negativeInfinity);
    console.log(nAn)

    // bigInt (fairly new, don't use it yet)
    const bigInt = 1234567890123456789012345678901234567890n; // over (-2**53  ~ 2*53)
    console.log(`value: ${bigInt}, type: ${typeof bigInt}`);
    Number.MAX_SAFE_INTEGER;

    // string
    const char = 'c';
    const brendan = 'brendan';
    const greeting = 'hello ' + brendan;
    console.log(`value: ${greeting}, type: ${typeof greeting}`);
    const helloBob = `hi ${brendan}`; // template literals (string)
    console.log(`value: ${helloBob}, type: ${typeof helloBob}`);

    // boolean
    // false: 0, null, undefined, NaN, ''
    // true: any other value
    const canRead = true;
    const test = 3 < 1; // false
    console.log(`value: ${canRead}, type: ${typeof canRead}`);
    console.log(`value: ${test}, type: ${typeof test}`);

    // null
    let nothing = null;
    console.log(`value: ${nothing}, type: ${typeof nothing}`);

    // undefined
    let x;
    console.log(`value: ${x}, type: ${typeof x}`);

    // symbol, create unique identifiers for objects
    const symbol1 = Symbol('id');
    const symbol2 = Symbol('id');
    console.log(symbol1 === symbol2);
    const gSymbol1 = Symbol.for('id');
    const gSymbol2 = Symbol.for('id');
    console.log(gSymbol1 === gSymbol2); // true
    console.log(`value: ${symbol1.description}, type: ${typeof symbol1}`);

    // object, real-life object, data structure
    const ellie = { name: 'ellie', age: 20 };
    ellie.age = 21;

    // 5. Dynamic typing: dynamically typed language
    let text = 'hello';
    console.log(text.charAt(0)); // h
    console.log(`value: ${text}, type: ${typeof text}`);
    let text = 1;
    console.log(`value: ${text}, type: ${typeof text}`);
    text = '7' + 5;
    console.log(`value: ${text}, type: ${typeof text}`);
    text = '8' / '2';
    console.log(`value: ${text}, type: ${typeof text}`);
    console.log(text.charAt(0)); // Dynamic typing에 의한 에러 발생
------------
### 4. 자바스크립트 4. 코딩의 기본 operator, if, for loop 코드리뷰 팁 | 프론트엔드 개발자 입문편
    // Note!
    // 2. Vatiable, r/w(read/write)
    // 3. Constants, r(read only)
    // use const whenever possible
    // only use let if variable needs to change.

    // Immutable data types: primitive types, frozen objects (i.e. object.freeze()) 
    // Mutable data types: all objects by default are mutable in JS

    // 1. string concatenation
    console.log('my' + ' cat');
    console.log('1' + 2);
    console.log(`string literals: 1 + 2 = ${1+2}`);

    // 2. Numeric operators
    console.log(1 + 1); // add
    console.log(1 - 1); // substract
    console.log(1 / 1); // divide
    console.log(1 * 1); // multiply
    console.log(5 % 2); // remainder
    console.log(2 ** 3); // exponentiation

    // 3. Increment and decrement operators
    let counter = 2;
    const preIncrement = ++counter;
    // counter = counter + 1;
    // preIncrement = counter;
    console.log(`preIncrement: ${preIncrement}, counter: ${counter}`);
    const postIncrement = counter++;
    // postIncrement = counter;
    // counter = counter + 1;
    console.log(`postIncrement: ${postIncrement}, counter: ${counter}`);

    // 4. Assignment operators
    let x = 3;
    let y = 6;
    x += y; // x = x + y;
    x -= y;
    x *= y;
    x /= y;

    // 5. Comparison operators
    console.log(10 < 6); // less than
    console.log(10 <= 6); // less than or equal
    console.log(10 > 6); // greater than
    console.log(10 >= 6); // greater than or equal

    // 6. Logical operators:  || (or), %% (and), ! (not)
    const value1 = false;
    const value2 = 4 < 2;

    // || (or), finds the first truthy value
    console.log(`or: ${value1 || value2 || check()}`);

    // && (and), finds the first falsy value
    console.log(`or: ${value1 && value2 && check()}`);

    // often used to compress long if-statement
    // nullableObject && nullableObject.something
    if (nullableObject != null) {
        nullableObject.something;
    }

    function check() {
        for (let i = 0; i < 10; i++){
            //wasting time
            console.log('😨');
        }
        return true;
    }

    // ! (not)
    console.log(!value1);

    // 7. Equality
    const stringFive = '5';
    const numberFive = 5;

    // == loose equality, with type conversion
    console.log(stringFive == numberFive);
    console.log(stringFive != numberFive);

    // === strict equality, no type conversion
    console.log(stringFive === numberFive);
    console.log(stringFive !== numberFive);

    // object equality by reference
    const ellie1 = { name: 'ellie' };
    const ellie2 = { name: 'ellie' };
    const ellie3 = ellie1;
    console.log(ellie1 == ellie2);
    console.log(ellie1 === ellie2);
    console.log(ellie1 === ellie3);

    // equality - puzzler
    console.log(0 == false);
    console.log(0 === false);
    console.log('' == false);
    console.log('' === false);
    console.log(null == undefined);
    console.log(null === undefined);

    // 8. Conditional operators: if
    // if, else if, else
    const name = 'ellie';
    if (name === 'ellie') {
        console.log('Welcome, Ellie!');
    } else if (name === 'coder') {
        console.log('You are amazing coder');
    } else {
        console.log('unknown');
    }

    // 9. Ternary operator: ?
    // condition ? value1 : value2;
    console.log(name === 'ellie' ? 'yes' : 'no');

    // 10. Switch statement
    // use for multiple if checks
    // use for enum-like value check
    // use for multiple type checks in TS
    const browser = 'IE';
    switch (browser) {
        case 'IE':
            console.log('go away!');
            breakl
        case 'Chrome':
        case 'Firefox':
            console.log('love you!');
            break;
        default:
            console.log('same all!');
            break;
    }

    // 11. Loops
    // while loop, while the condition is truthy.
    // body code is excuted.
    let i = 3;
    while (i > 0) {
        console.log(`while: ${i}`);
        i--;
    }

    // do while loop, body code is excuted first,
    // then check the condition.
    do {
        console.log(`do while: ${i}`);
        i--;
    } while (i > 0);

    // for loop, for(begin; condition; step)
    for (i = 3; i > 0; i--) {
        console.log(`for: ${i}`);
    }

    for (let i = 3; i > 0; i = i -2) {
        // incline variable declaration
        console.log(`incline variable for: ${i}`);
    }

    // nested loops
    for (let i = 0; i < 10; i++) {
        for (let j = 0; j < 10; j++) {
            console.log(`i: ${i}, j: ${j}`);
        }
    }

    // break, continue
    // Q1. iterate from 0 to 10 and print only even numbers (use continue)
    for (let i = 0; i < 11; i++) {
        if (i % 2 !== 0) {
            continue;
        }
        console.log(`q1. ${i}`);
    }

    // Q2. iterate from 0 to 10 and print numbers untill reaching 8 (use break)
    for (let i = 0; i < 11; i++) {
        if (i > 8) {
            break;
        }
        console.log(`q2. ${i}`);
    }
------------
## 모던 자바스크립트
------------
### 3장 변수
- 변수 선언자 var (*변수 선언자 let: 블록 유효 범위)
- ES6부터 추가된 데이터 타입
    - 심벌: Symbol( )
    - 템플릿 리터럴: ``
------------
### 4장 객체와 배열, 함수의 기초
JavaScript에서 객체를 생성하는 방법 (2가지)
1. 객체 리터럴: { . . . }
    - var card = { suit: "하트", rank: "A" }
2. 생성자 함수: new 연산자
- Java와 C++ 등은 클래스(Class)를 제공하지만 JavaScript의 경우 클래스(Class)가 없어, 생성자 함수로 객체를 생성
    - var card = new Card("하트", "A");
------------
### 5장 표현식과 연산자
1. 관계 연산자
    |연산자|뜻|예제|예제의 뜻|
    |:-----:|:-----:|:-----:|:-----:|
    |==|값이 같음|a==b|a값과 b값이 같으면 true, 그 외에는 false|
    |!=|값이 다름|a!=b|a값과 b값이 다르면 true, 그 외에는 false|
    |===|값과 타입이 같음|a===b|a와 b의 값과 타입이 같으면 true, 그 외에는 false|
    |!==|갑과 타입이 다름|a!==b|a와 b의 값과 타입이 다르면 true, 그 외에는 false|
    |<|작음|a<b|a값이 b값보다 작으면 true, 그 외에는 false|
    |>|큼|a>b|a값이 b값보다 크면 true, 그 외에는 false|
    |<=|작거나 같음|a<=b|a값이 b값보다 작거나 같으면 true, 그 외에는 false|
    |>=|크거나 같음|a>=b|a값이 b값보다 크거나 같으면 true, 그 외에는 false|

2. 논리 연산자
    |연산자|뜻|예제|예제의 뜻|
    |:-----:|:-----:|:-----:|:-----:|
    |&&|논리곱|a&&b|a와 b가 모두 true면 true, 그 외에는 false|
    |&#124;&#124;|논리합|a &#124;&#124; b|a와 b 중 하나라도 true면 true, 모두가 false면 false|
    |!|부정|!a|a가 true면 false, false면 true|
------------