---
title:  "01-변수"
subtitle: "Javascript"
author: "Wferr"
avatar: "img/authors/wferr.png"
image: "img/f.jpg"
date:   2019-12-27 17:11:00
---
# 변수

데이터를 저장할 수 있는 메모리 상의 공간.

## #01. 변수 만들기

### 1) 전역변수

#### 변수의 선언

변수 이름 앞에 **var** 키워드를 명시하고 변수 이름을 지정한다.


```javascript
var my_number1;
```

#### 값의 할당

생성된 변수에 대입연산자 `=`를 사용하여 값을 할당한다. 항상 오른쪽에서 왼쪽으로 대입된다.


```javascript
my_number1 = 100;
console.log(my_number1);
```

    100


#### 선언과 할당의 통합


```javascript
var my_number2 = 123;
console.log(my_number2);
```

    123


#### 변수값 변경하기

한 번 값이 할당된 변수는 다른 값으로 새롭게 할당 가능함


```javascript
my_number1 = 200;
my_number2 = 456;
console.log(my_number1);
console.log(my_number2);
```

    200
    456


#### 변수의 재선언

**var** 키워드를 사용하여 선언된 변수는 중복 선언이 가능하며 이후 뒤에서 공부할 **변수의 스코프(유효성 범위)**도 무시되므로 *가급적 사용하지 않는 것이 좋다.*


```javascript
var my_number1 = 300;
var my_number2 = 789;
console.log(my_number1);
console.log(my_number2);
```

    300
    789


### 2) 'let' 키워드를 사용한 변수

`ES6 버전`에서 새로 추가된 변수 생성 방법.
대부분의 프로그래밍 언어에서 말하는 일반적인 변수의 생성 규칙을 따른다.

#### 변수 선언


```javascript
let my_number3;
```

#### 변수 할당


```javascript
my_nuber3 = 12345;
console.log(12345);
```

    12345


#### 선언과 할당의 통합


```javascript
let my_number4 = 67890;
console.log(my_number4);
```

    67890


#### 중복 선언 금지

**let** 키워드를 사용하여 선언된 변수는 중복 선언 불가.


```javascript
let my_number3; // 앞에서 이미 선언된 변수이므로
```


    evalmachine.<anonymous>:1

    let my_number3; // 앞에서 이미 선언된 변수이므로 에러

    ^


​

    SyntaxError: Identifier 'my_number3' has already been declared

        at evalmachine.<anonymous>:1:1

        at Script.runInThisContext (vm.js:116:20)

        at Object.runInThisContext (vm.js:306:38)

        at run ([eval]:1054:15)

        at onRunRequest ([eval]:888:18)

        at onMessage ([eval]:848:13)

        at process.emit (events.js:210:5)

        at emit (internal/child_process.js:876:12)

        at processTicksAndRejections (internal/process/task_queues.js:81:21)


### 3) 상수

**const** 키워드를 사용하여 생성된 변수는 선언과 동시에 값이 할당되어야 하며,
최초 값을 할당한 이후 값을 변경할 수 없다.

> 대체적으로 상수의 이름은 모두 대문자를 사용하여 생성하는 것이 일반적입니다.


```javascript
const MY_VALUE1 = 123;
console.log(MY_VALUE1);
```

    123



```javascript
MY_VALUE1 = 234; // const로 선언된 변수이므로 값을 변경할 수 없다.
```


    evalmachine.<anonymous>:1

    MY_VALUE1 = 234; // const로 선언된 변수이므로 값을 변경할 수 없다.

              ^


​

    TypeError: Assignment to constant variable.

        at evalmachine.<anonymous>:1:11

        at Script.runInThisContext (vm.js:116:20)

        at Object.runInThisContext (vm.js:306:38)

        at run ([eval]:1054:15)

        at onRunRequest ([eval]:888:18)

        at onMessage ([eval]:848:13)

        at process.emit (events.js:210:5)

        at emit (internal/child_process.js:876:12)

        at processTicksAndRejections (internal/process/task_queues.js:81:21)



```javascript
const MY_VALUE2; // 선언시에 값이 할당되지 않았으므로 에러
```


    evalmachine.<anonymous>:1

    const MY_VALUE2; // 선언시에 값이 할당되지 않았으므로 에러

          ^^^^^^^^^


​

    SyntaxError: Missing initializer in const declaration

        at new Script (vm.js:84:7)

        at createScript (vm.js:258:10)

        at Object.runInThisContext (vm.js:306:10)

        at run ([eval]:1054:15)

        at onRunRequest ([eval]:888:18)

        at onMessage ([eval]:848:13)

        at process.emit (events.js:210:5)

        at emit (internal/child_process.js:876:12)

        at processTicksAndRejections (internal/process/task_queues.js:81:21)


### 4) 변수이름 규칙

1. 영어, 숫자, 언더바(`_`), `$` 기호만 사용할 수 있다.

   > 일반적으로 영어 소문자로 시작한다.

1. 첫 글자는 숫자로 시작할 수 없다.

1. 두 개 이상의 단어를 결합하여 이름을 지정하는 경ㅇ

   1. **스네이크 표기법** : 띄어쓰기가 필요한 위치에서 언더바(`_`)를 사용.

   - **상수**를 정의할 때 사용한다.

   > home + word ==> home_wordk

   1. **카멜 표기법** : 띄어쓰기가 필요한 위치의 첫 글자를 대문자로 변경.

   - **변수**를 정의할 때 사용한다.

   > home + work ==> homeWork

잘 알려지지 않은 규칙이지만 **UTF-8** 환경에서는 한글도 사용할 수 있다.


```javascript
let 나이 = 19;
console.log(나이);
```

    19


## #02. 변수의 자료형 (데이터 타입)

### 1) 변수에 저장할 수 있는 값의 종류

| 타입       | 설명                                                         |
| ---------- | ------------------------------------------------------------ |
| number     | 정수와 실수를 포함하는 모든 숫자 형태                        |
| string     | 문자열. 쌍따옴표나 홑따옴표의 쌍으로 감싼 모든 형식의 데이터 |
| boolean    | 논리형. `true`(참) 혹은 `false`(거짓)                        |
| object     | 객체. 함수(Function), 배열(Array), 날짜(Date), 정규식(RegExp) 등을 포함한다. |
| null       | object형의 한 종류. 나중에 할당하기 위해 임의로 비워 놓은 상태를 의미하는 특수한 값. |
| underfined | 정의되지 않음. 선언만 하고 값이 할당되지 않은 상태           |

### 2) 변수의 자료형 확인하기

`typeof` 연산자는 피연산자의 평가 전 자료형을 나타내는 문자열을 반환한다.


```javascript
let sampleValue1 = 123;
console.log(typeof sampleValue1);
```

    number



```javascript
let sampleValue2 = "Hello World";
console.log(typeof sampleValue2);
```

    string



```javascript
let sampleValue3 = true;
console.log(typeof sampleValue3);
```

    boolean



```javascript
let sampleValue4 = new Date();
console.log(typeof sampleValue4);
```

    object



```javascript
let sampleValue5 = null;
console.log(typeof sampleValue5);
```

    object



```javascript
let sampleValur6;
console.log(typeof sampleValue6);
```

    undefined

