연산자, 문장, Object, Number, Math, String
Template, RegExp, Array, Function, Iterator, Generator, Symbol
Map, WeakMap, Set, WeakSet, Class, Reflect, Proxy
ArrayBuffer, TypedArray, DataView, Promise, Module, Babel & Webpack
ES6와 연관된 Node.js, XMLHttpRequest, Workers, Canvas 부분

연산자,
문장,
Object,
Number,
Math,
String

Template,
RegExp,
Array,
Function,
Iterator,
Generator,
Symbol

Map,
WeakMap,
Set,
WeakSet,
Class,
Reflect,
Proxy

ArrayBuffer,
TypedArray,
DataView,
Promise,
Module,
Babel & Webpack

ES6와 연관된 Node.js,
XMLHttpRequest,
Workers,
Canvas 부분

```
* arrow function

- ...rest // arguments 대체 권장
- function내 scope 유의해야 함
- 자동 return; 1줄이거나 소괄호로 둘러쌓인 JSON객체
- new 연산자로 인스턴스 생성 불가; prototype, constructor가 없음, 생성자가 없는 특별한 형태의 함수;
- this;
- // ES5: setTimeout() 의 경우 this를 window객체 참조
- // ES6: arrow function 의 경우 스코프를 유지할 수 있음. setTimeout() 내에서 this 참조
- 기존 function 키워드 함수와 비교해서 선택 사용

```

```
* Iteration_protocols
- Iteration
- next()
- 
```

## spread
```
- obect는 프로퍼티만 변경 할 수 있음.
```

## array-like
```
- arguments // array-like
- ...rest // array obejct
```

## Destructuring assignment
```
* Array destructuring
* Object destructuring
- The ( .. ) around the assignment statement...
- let {nine, plus: {ten}} = {nine:9, plus: {ten: 10}} // plus: 경로 역할
- Setting a function parameter's default value
```


## Object.defineProperty()
```
configureable
enumerable
value
writable
get
set
```

## Object initializer: shorthand method names
```
vs ES5
* ES5
get: function() {return "book"}
* ES6
get getBook() {return "book"}
```

## Object initializer: computed property names
```
```

## default
```
let {a, b = 5} = {a: 10, b: 20}
let {a, b = a + 1, c = b + 1} = {a: 1}
```

## for...of
```
* 프로퍼티 값이 설정됨
* Difference between for...of and for...in
- 프로토타입에 정의된 프로퍼티는 제외시킴
- Object는 iterable이 아니므로 사용불가 // Ojbect.keys로 활용하여 사용
```

## prototype
```
valueOf
toString

최신동향; 메서드, 함수 prototype에 연결 되지않고 Object에 바로 연결(ES6)
```

## Object.is()
```
* https://dorey.github.io/JavaScript-Equality-Table/
* NaN 도 하나의 값임
- NaN === NaN // false
- Object.is(NaN, NaN) // true

```

## Object.assign()
```
* property 작성 순서 주의
- property, get property vs get property, property
```

## Object.setPrototypeOf()
```
* __proto__ 에 설정하는 목적
* prototype vs __proto__

```

## Object.prototype.__proto__
```
```

## Number
```
* IEEE 754
- double precision floating point format
- 64bit(8byte) 유동 소수점 형태로 수를 표시
- 
- 
```

## Number.MAX_SAFE_INTEGER, Number.MIN_SAFE_INTEGER 
```
```

## Number.EPSILON
```
0.1 + 0.2 === 0.3 // false
Number.EPSILON = true;
0.1 + 0.2 === 0.3 // true

// 기존의 해결방법
소수 -> 정수 변환 and 계산 -> 소수 (정수에서는 문제가 없음)
```

## Number.isNaN()
```
Number.isNaN("ABC");
isNaN("ABC");
```

## Number.isInteger()
```
```

## Number.isSafeInteger()
```
```

## Number.isFinite()
```
```

## Math.log10(), Math.log2(), Math.log1p(), Math.expm1(), Math.cosh(), Math.sinh(), Math.tanh(), Math.acosh(), Math.asinh(), Math.atanh(), Math.hypot(): 제곱근, Math.trunc(): 소수를 제외한 정수 반환, Math.sign(), Math.cbrt(): 세제곱근
```
```

## Math.imul()
```
* 32bit
* Emscripten
```

## Unicode code point escapes
```
\u{XXXXXX}
```

## Surrogate pair
```
* ES5 호환
* http://unicode-table.com/en/
- http://unicode-table.com/en/1F418/
* \{?}\{?}
```

## String.fromCodePoint()
```
* binary 데이터
```

## String.prototype.codePointAt()
```
```

## String.prototype.includes() 
```
* 2번째 파라미터 인덱스 제한 // .incldues('a', 5)
* 정규표현식 사용불가
```

## String.prototype.startsWith(), String.prototype.endsWith()
```
```

## String.prototype.repeat()
```
```

## String.prototype.normalize()
```
* 유니코드 정규화
let ja = "ㄱ".charCodeAt(0); // 초성, 종성 등.. 조합에 따라 유니코드 값이 달라짐
let mo = "ㅏ".charCodeAt(0);
let jamo = '\u3131\u314F';
let result = jamo.normalize('NFC');
```

## String.raw()
```
Template literals
```

## Template literals
```
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals
* 문자열과 표현식(${...})로 구성
```

### Multi-line strings
```
```

### Expression interpolation
```
```

### Tagged template literals
```
var a = 5;
var b = 10;

function tag(strings, ...values) {
  console.log(strings[0]); // "Hello "
  console.log(strings[1]); // " world "
  console.log(strings[2]); // ""
  console.log(values[0]);  // 15
  console.log(values[1]);  // 50

  return "Bazinga!";
}

tag`Hello ${ a + b } world ${ a * b }`;
// "Bazinga!"
```

### Raw strings
```
// * 역슬레시를 문자자체로 인식

let oen = 1, two = 2;
String.raw({raw: 'ABCDE', one, two, 3}); // A1B2C3DE

// * 활용: dinamic한 문자열 생성, HTML 엘리먼트 속성값 파싱(id, class, style ...)
```

## Array
```
* from

```

### Array iteration with for...of (Firefox 13)
```
```

### Array.from() (Firefox 32)
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from
* The Array.from() method creates a new Array instance from an array-like or iterable object.
* Array.from(arrayLike[, mapFn[, thisArg]])

```
let arrayLike = {0: 'one', 1: 'two', length: 2};

```

```
// Array-like object (arguments) to Array
function f() {
  return Array.from(arguments);
}

f(1, 2, 3); 
// [1, 2, 3]
```

```
let nodes = document.querySelect...('li');
Array.from(nodes).forEach((node) => {
    console.log(node.textContent);
    })
```

### Array.of() (Firefox 25)
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/of
* The Array.of() method creates a new Array instance with a variable number of arguments, regardless of number or type of the arguments.
* Array.of(element0[, element1[, ...[, elementN]]])
```
```

### Array.prototype.fill() (Firefox 31)
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill
* The fill() method fills all the elements of an array from a start index to an end index with a static value.
* arr.fill(value[, start = 0[, end = this.length]])
```
[1, 2, 3].fill(4);               // [4, 4, 4]
[1, 2, 3].fill(4, 1);            // [1, 4, 4]
[1, 2, 3].fill(4, 1, 2);         // [1, 4, 3]
[1, 2, 3].fill(4, 1, 1);         // [1, 2, 3]
[1, 2, 3].fill(4, -3, -2);       // [4, 2, 3]
[1, 2, 3].fill(4, NaN, NaN);     // [1, 2, 3]
Array(3).fill(4);                // [4, 4, 4]
[].fill.call({ length: 3 }, 4);  // {0: 4, 1: 4, 2: 4, length: 3}
```

### Array.prototype.find()
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find
* The find() method returns a value in the array, if an element in the array satisfies the provided testing function. Otherwise undefined is returned.
* arr.find(callback[, thisArg])
* parameters
```
element
The current element being processed in the array.

index
The index of the current element being processed in the array.

array
The array find was called upon.
```

* this binding에 주의(function vs arrow function)

### Array.prototype.findIndex() (Firefox 25)
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex
* The findIndex() method returns an index in the array, if an element in the array satisfies the provided testing function. Otherwise -1 is returned.
* arr.findIndex(callback[, thisArg])
- parameters
```
element
The current element being processed in the array.
index
The index of the current element being processed in the array.
array
The array findIndex was called upon.
```

```
```

### Array.prototype.entries()
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries
* The entries() method returns a new Array Iterator object that contains the key/value pairs for each index in the array.
* arr.entries()
```
var arr = ['a', 'b', 'c'];
var eArr = arr.entries();

console.log(eArr.next().value); // [0, 'a']
console.log(eArr.next().value); // [1, 'b']
console.log(eArr.next().value); // [2, 'c']
```

```
for (let e of eArr) {
  console.log(e);
}

```

```
// 분해 할당 활용
for (let [key, value] of eArr) {
  console.log(key, ': ', value);
}
```

### Array.prototype.keys() (Firefox 28)
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys
* The keys() method returns a new Array Iterator that contains the keys for each index in the array.
* arr.keys()
* vs .entries(); vs .keys(); vs .values()
```
var arr = ["a", "b", "c"];
var iterator = arr.keys();

console.log(iterator.next()); // { value: 0, done: false }
console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: 2, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

```
var arr = ["a", , "c"];
var sparseKeys = Object.keys(arr);
var denseKeys = [...arr.keys()];
console.log(sparseKeys); // ['0', '2']
console.log(denseKeys);  // [0, 1, 2]
```

### Array.prototype.values()
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values
* The values() method returns a new Array Iterator object that contains the values for each index in the array.
* arr.values()
```
var arr = ['w', 'y', 'k', 'o', 'p'];
var eArr = arr.values();
// your browser must support for..of loop
// and let-scoped variables in for loops
for (let letter of eArr) {
  console.log(letter);
}
```

### Array.prototype.copyWithin() (Firefox 32)
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin
* The copyWithin() method shallow copies part of an array to another location in the same array and returns it, without modifying its size.
* arr.copyWithin(target[, start[, end]])
```
[1, 2, 3, 4, 5].copyWithin(-2);
// [1, 2, 3, 1, 2]

[1, 2, 3, 4, 5].copyWithin(0, 3);
// [4, 5, 3, 4, 5]

[1, 2, 3, 4, 5].copyWithin(0, 3, 4);
// [4, 2, 3, 4, 5]

[1, 2, 3, 4, 5].copyWithin(-2, -3, -1);
// [1, 2, 3, 3, 4]

[].copyWithin.call({length: 5, 3: 1}, 0, 3);
// {0: 1, 3: 1, length: 5}

// ES6 Typed Arrays are subclasses of Array
var i32a = new Int32Array([1, 2, 3, 4, 5]);

i32a.copyWithin(0, 2);
// Int32Array [3, 4, 5, 4, 5]

// On platforms that are not yet ES6 compliant: 
[].copyWithin.call(new Int32Array([1, 2, 3, 4, 5]), 0, 3, 4);
// Int32Array [4, 2, 3, 4, 5]
```

```
let one = Array.prototype.copyWithin.call({
    0: 'ABC',
    1: 'EDF',
    2: '가나다',
    length: 3
    }, 0, 1);
console.log(one); // 0: EDF, 1: 가나다, 2: 가나다
```

* The copyWithin function is intentionally generic, it does not require that its this value be an Array object.
- copyWithin() 은 Array 메서드이므로 Array가 처리 대상
- 이때 generic은 array-like, interable object도 처리 할 수 있다는 의미
```
Array.prototype.copyWithin.call(...);
```

### get Array[@@species] (Firefox 48)
```
```

## RegExp
```
```

### RegExp sticky (y) flag (Firefox 38)

* The sticky flag indicates that the regular expression performs sticky matching in the target string by attempting to match starting at RegExp.prototype.lastIndex.
* 정규 표현식은
- 매치된 문자열의 인덱스를 lastIndex에 설정
* y(sticky) 플래스
- lastIndex 위치부터 매치 수행
- 디폴트: 0
- ^패턴을 사용하지 않으면 첫 문자부터 매치

```
var str = '#foo#';
var regex = /foo/y;

regex.lastIndex = 1;
regex.test(str); // true
regex.lastIndex = 5;
regex.test(str); // false (lastIndex is taken into account with sticky flag)
regex.lastIndex; // 0 (reset after match failure)
```

### RegExp unicode (u) flag (Firefox 46)

* As mentioned above, \w or \W only matches ASCII based characters; for example, "a" to "z", "A" to "Z", "0" to "9" and "_". To match characters from other languages such as Cyrillic or Hebrew, use \uhhhh, where "hhhh" is the character's Unicode value in hexadecimal. This example demonstrates how one can separate out Unicode characters from a word.

```
var text = 'Образец text на русском языке';
var regex = /[\u0400-\u04FF]+/g;

var match = regex.exec(text);
console.log(match[0]);        // logs 'Образец'
console.log(regex.lastIndex); // logs '7'

var match2 = regex.exec(text);
console.log(match2[0]);       // logs 'на' [did not log 'text']
console.log(regex.lastIndex); // logs '15'

// and so on
```

### generic RegExp.prototype.toString (Firefox 39)
```
```

### RegExp.prototype[@@match]() (Firefox 49)
```
```

### RegExp.prototype[@@replace]() (Firefox 49)
```
```

### RegExp.prototype[@@search]() (Firefox 49)
```
```

### RegExp.prototype[@@split]() (Firefox 49)
```
```

### get RegExp[@@species] (Firefox 49)
```
```

## Generator
```
* ref
- https://gist.github.com/marocchino/841e2ff62f59f420f9d9
- http://blog.hazard.kr/archives/399
```

### Generator function (Firefox 26)

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*
* The function* declaration (function keyword followed by an asterisk) defines a generator function, which returns a Generator object.
* function* name([param[, param[, ... param]]]) { statements... }
* 제너레이터 함수를 호출하면
- 함수 블록을 실행하지 않고
- Generator 오브젝트를 생성하여 반환
- 반환된 오브젝트는 이터레이터 오브젝트

```
function* idMaker(){
  var index = 0;
  while(index < 3)
    yield index++;
}

var gen = idMaker();

console.log(gen.next().value); // 0
console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
console.log(gen.next().value); // undefined
// ...
```

### GeneratorFunction

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/GeneratorFunction
* The GeneratorFunction constructor creates a new generator function object. In JavaScript every generator function is actually a GeneratorFunction object.
* Object.getPrototypeOf(function*(){}).constructor
* new GeneratorFunction ([arg1[, arg2[, ...argN]],] functionBody)

```
var GeneratorFunction = Object.getPrototypeOf(function*(){}).constructor
var g = new GeneratorFunction("a", "yield a * 2");
var iterator = g(10);
console.log(iterator.next().value); // 20
```

### yield (Firefox 26)

* The yield keyword is used to pause and resume a generator function (function* or legacy generator function).
* [rv] = yield [expression];
* yield 키워드는 제너레이터 함수를 멈추거나 다시 실행에 사용
* yield 오른쪽의 표현식을 평가하고 결과 반환
- 표현식을 작성하지 않으면 undefined 반환
* [rv]
- 오른쪽의 평가 결과가 설정하는 것이 아니라
- 다음 next()에서 파라미터에 지정한 값이 설정됨

```
function* foo(){
  var index = 0;
  while (index <= 2)
    yield index++;
}

var iterator = foo();
console.log(iterator.next()); // { value: 0, done: false }
console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: 2, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

```
fnction* sports(one) {
    let two = yield one;
    let param = yield two + one;
    yield param + one;
}

let genObj = sports(10);

console.log(genObj.next());
console.log(genObj.next());
console.log(genObj.next(20));
```

```
function* sports(one) {
    yield one;
    let check = 10;
}

let genObj = sprots(10);

let result = genObj.next();
console.log(result); // {value: 10, done: false}

result = genObj.next();
console.log(result); // {value: undefined, done: true}
```

```
let gen = function* (param) {
    let one = param + 1;
    yield one;
    var two = 2;
    yield one + two;
}
let genObj = gen(10);
console.log(genObj.next()); // {value: 11, done: false}
console.log(genObj.next()); // {value: 13, done: false}
console.log(genObj.next()); // {value: undefined, done: true} // ?
```

```
let gen = function* () {
    one = yeild;
    two = yield one + 10;
}
let genObj = gen();
console.log(genObj.next()); // undefined
console.log(genObj.next(12)); // 22
console.log(genObj.next(34)); // undefined, true
```

```예제 시나리오
* 금액 계산 함수와 할인 금액 계산 함수가 있음
* 금액 계산 함수는 수량과 단가를 파라미터로 받아 금액을 계산하고 결과를 yeild로 반환
* 할인 금액 계산 함수 호출
- yield로 반환한 값을 파라미터 값으로 넘겨 줌
- 할인 금액을 계산하여 반환
* 금액 계산 함수를 호출하면서
- 할인 금액을 파라미터 값으로 넘겨 줌
- 할인 금액 - 할인 금액 결과 반환
```

```
let getAmount = function* (qty, price) {
    let amount = Math.floor(qty * price);
    let discount = yeild amount;
    return amount - discount; // return
}
let getDiscount = function(amount) {
    return amount > 1000 ? amount * 0.2 : amount * 0.1;
}
let amountObj = getAmount(10, 60);
let result = amountObj.next();
console.log(result); // {value: 600, done: false}

let dcAmount = getDiscount(result.value);
console.log(dcAmount); // 60

result = amountObj.next(dcAmount);
console.log(result); // {value: 540, done: true}
```

```
let genObj = function* () {
    return yeild yeild yeild;
}
let gen = genObj();
console.log(gen.next()); // undefined, false
console.log(gen.next(10)); // 10, false
console.log(gen.next(20)); // 20, false
console.log(gen.next(30)); // 30, true
```

```
let gen = function* (start) {
    let count = start;
    while (true) {
        yield ++count;
    }
}
for (let cnt of gen(10)) {
    console.log(cnt);
    if (cnt > 13) {
        break;
    }
}
```

### yield* (Firefox 27)
```
function* g1() {
  yield 2;
  yield 3;
  yield 4;
}

function* g2() {
  yield 1;
  yield* g1();
  yield 5;
}

var iterator = g2();

console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: 2, done: false }
console.log(iterator.next()); // { value: 3, done: false }
console.log(iterator.next()); // { value: 4, done: false }
console.log(iterator.next()); // { value: 5, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

## Class

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes
* class method 특징
- ,(콤마) 미사용ㄴ
- typeof 값 'function'
* https://hacks.mozilla.org/2015/07/es6-in-depth-classes/

```
```

### Defining classes
```
class Polygon {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
```

```
class Polygon extends SuperPolygon {
```

### Class declarations
```
* method vs function
```

### Hoisting
```
```

### Class expressions
```
```

### Class body and method definitions
```
```

### Strict mode
```
```

### Constructor
```
```

### Prototype methods
```
```

### Static methods
```
```

### Sub classing with extends
```
```

### Species
```
```

### Super class calls with super
```
```

## Function
```
```

## Iterator
```
```

## Symbol
```
```

## 
```
```

## 
```
```

## 
```
```

## 
```
```

## 
```
```

## 
```
```

## 
```
```

## 
```
```

## 성능
```
* server side 에서의 퍼포먼스 필요
- memory leak 해결
- ES6 반영(bite)
```

## 기타
* https://babeljs.io/repl
```
```