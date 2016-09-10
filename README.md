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

```
# 예제 시나리오

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
- ,(콤마) 미사용
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

* 호이스팅 되지 않음

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
class Sports {
  constructor() {
    let ground = Sports.getGround();
    console.log(groud);
    ground = this.constructor.getGround();
    console.log(ground);
  }
  static getGround() {
    return '상암 구장';
  }
}
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

### Custom Elements with Classes

* https://developer.mozilla.org/en-US/docs/Web/Web_Components/Custom_Elements/Custom_Elements_with_Classes
* Custom Element is a custom HTML tag and/or element that give us the tool to extend HTML's vocabulary and teaching it new tricks. It is different than normal tags as it can use lifecycle callbacks, which enable you to attach behaviors to different parts of the new element's "lifecycle." it can be built based on the general HTMLElement, or as extends of native element like <button>
* class SaveBtn extends HTMLElement {}

```
class ExtendsImages extends Image {
  constructor() {
    super();
  }
  setProperty() {
    this.src = 'file/image.jsp';
    this.alt = '';
    this.title = '';
  }
}
let obj = new ExtendsImages();
obj.setProperty();
document.querySelector('body').appendChild(obj);
```

```
class ExtendsAudio extends Audio {
  // ...
}
```

### class vs function

* 경우에 따라서는 function 이 좋다
* 설계는 필수적
  - 경험이 필요함(5년 정도)
  - 작은 프로젝트라도 설계 연습 할 것

```
```

***

## new.target

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target
* The new.target property lets you detect whether a function or constructor was called using the new operator. In constructors and functions instantiated with the new operator, new.target returns a reference to the constructor or function. In normal function calls, new.target is undefined.
* new.target
* cunstuctor 함수를 참조함

```
let sports = function() {
  console.log(new.target) // 
  let target = new.target ? new.target.name : undefined;
  console.log(target);
}
sports(); // 
new sports(); // 
```

```
function Foo() {
  if (!new.target) throw "Foo() must be called with new";
  console.log("Foo instantiated with new");
}

Foo(); // throws "Foo() must be called with new"
new Foo(); // logs "Foo instantiated with new"
```

***

## Symbol

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol
* A symbol is a unique and immutable data type and may be used as an identifier for object properties. The Symbol object is an implicit object wrapper for the symbol primitive data type.
* Symbol([description])
* 특징
  - 생성한 값은 프로그램 전체를 통틀어 유일한 값으로 엔진 차원에서 관리(in 다른 라이브러리, 프레임워크...)
  - +, | 연산자 사용 불가(+: Number 타입으로 캐스팅)
  - template(`${...}`) 사용불가

```
var sym1 = Symbol();
var sym2 = Symbol("foo");
var sym3 = Symbol("foo");
```

```
console.log(String(Symbol('심볼'))); // Symbol(심볼)
```

### primitive data

* 자바스크립트에 Primitive 개념이 있음
  - 오브젝트가 아닌 데이터
  - 따라서 메소드를 갖고 있지 않음
* let num = 123;
  - num에 123만 할당되고 아무것도 첨부되지 않음
  - 123은 number data로 primitive
* ES5의 primitive data
  - string, number, boolean, null, undefined
* ES6에 symbol이 추가됨
* wrapper object
  - string: String
  - number: Number
  - boolean: Boolean
  - symbol: Symbol
* undefined, null은 없음
* wrapper 오브젝는 메소드가 존재

```
```

### Symbol 사용 형태

* Ojbect 프로퍼티 이름으로 사용
  - symbol-keyed property
* for-in
  - 프로퍼티 이름으로 Symbol이 열거되지 않음
* 메소드 이름
* JSON.stringify()
  - Symbol 값이 문자열로 변환 불가

```
```

### Well-known symbols

* Symbol.toStringTag
  - A string value used for the default description of an object. Used by Object.prototype.toString().

```
class Sports {
  get [Symbol.toStringTag]() {
    return 'Sports-class';
  }
}
```

* Symbol.isConcatSpreadable
  - A Boolean value indicating if an object should be flattened to its array elements. Used by Array.prototype.concat().

```
```

* Symbol.unscopables
  - An object value of whose own and inherited property names are excluded from the with environment bindings of the associated object.

* Symbol.species
  - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/species
  - A constructor function that is used to create derived objects.
  - The species accessor property allows subclasses to over-ride the default constructor for objects.
  - 사전적 의미: (공통 특성을 지닌) 종류, 인류, 종

```
class MyArray extends Array {
  // Overwrite species to the parent Array constructor
  static get [Symbol.species]() { return Array; }
}
var a = new MyArray(1,2,3);
var mapped = a.map(x => x * x);

console.log(mapped instanceof MyArray); // false
console.log(mapped instanceof Array);   // true
```

```
class ExtendOne extends Array {
  showOne() {
    console.log('ExtendOne');
  }
};

class ExtendTwo extends Array {
  // 함수가 호출되면 자신을 반환하지 않고 앞에 작성한 ExtendOne class 반환
  // 이와 같이 반환 값을 바꿀 수 있음
  static get [Symbol.species]() {
    return ExtendOne;
    // return null // null 인 경우 default constructor(이 경우Array) 가 호출. 
  }
  showTwo() {
    console.log('ExtendTow');
  }
};

let twoInstance = new ExtendTwo(10, 20, 30);
twoInstance = twoInstance.filter(value => value > 10);
console.log(twoInstance); // 20, 30
twoInstance.showOne(); // ExtendOne
console.log(twoInstance.showTwo); // undefined

// 도중에 인스턴스가 변경되었으므로 twoInstance에 ExtendOne으로 생성한 인스턴스가 할당.
```

* Symbol.toPrimitive
  - A method converting an object to a primitive value.
  - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toPrimitive
  - With the help of the Symbol.toPrimitive property (used as a function value), an object can be converted to a primitive value. The function is called with a string argument hint, which specifies the preferred type of the result primitive value. The hint argument can be one of "number", "string", and "default".
  - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/@@toPrimitive
  - Symbol()[Symbol.toPrimitive](hint);

```
// An object without Symbol.toPrimitive property.
var obj1 = {};
console.log(+obj1);     // NaN
console.log(`${obj1}`); // "[object Object]"
console.log(obj1 + ""); // "[object Object]"

// An object with Symbol.toPrimitive property.
var obj2 = {
  [Symbol.toPrimitive](hint) {
    if (hint == "number") {
      return 10;
    }
    if (hint == "string") {
      return "hello";
    }
    return true;
  }
};
console.log(+obj2);     // 10      -- hint is "number"
console.log(`${obj2}`); // "hello" -- hint is "string"
console.log(obj2 + ""); // "true"  -- hint is "default"
```

* Object.method 호출 시 Object Instance 를 반환함

```
let sliceOne = [1, 2, 3].slice(1, 3); // Instance 반환
let sliceTwo = sliceOne.pop();
```

### Iteration symbols

* 

```
```

### Regular expression symbols

* 

```
```

### Other symbols

* 

```
```


### Using the typeof operator with symbols

* 

```
```

### Symbol type conversions

* 

```
```

### Symbols and for...in iteration

* 

```
```

### Symbols and JSON.stringify()

* 

```
```

### Symbol wrapper objects as property keys

* When a Symbol wrapper object is used as a property key, this object will be coerced to its wrapped symbol:

```
var sym = Symbol("foo");
var obj = {[sym]: 1};
obj[sym];            // 1
obj[Object(sym)];    // still 1
```

---

### Symbol.iterator (Firefox 36)

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator
  - Array.prototype[@@iterator]()
  - TypedArray.prototype[@@iterator]()
  - String.prototype[@@iterator]()
  - Map.prototype[@@iterator]()
  - Set.prototype[@@iterator]()

```
var myIterable = {}
myIterable[Symbol.iterator] = function* () {
    yield 1;
    yield 2;
    yield 3;
};
[...myIterable] // [1, 2, 3]
```

### Symbol.for() - global Symbol registry (Firefox 36)

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/match
* The Symbol.for(key) method searches for existing symbols in a runtime-wide symbol registry with the given key and returns it if found. Otherwise a new symbol gets created in the global symbol registry with this key.
* Symbol.for(key);
* 특징
  - global symbol registry
  - {key: value} 형태로 저장
  - 파라미터값이 key
  - Symbol()로 생성한 값이 value
* 특징
  - 파라미터 key 값을 유일하도록 정의하면 유용(ex. Symbol.for("user.age"))

```
console.log(Symbol('abc') === Symbol('abc')); // false
console.log(Symbol('abc') === Symbol.for('abc')); // false
console.log(Symbol.for('abc') === Symbol.for('abc')); // true
```

### Symbol.keyFor()

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/keyFor
* The Symbol.keyFor(sym) method retrieves a shared symbol key from the global symbol registry for the given symbol.
* Symbol.keyFor(sym);

```
var globalSym = Symbol.for("foo"); // create a new global symbol
Symbol.keyFor(globalSym); // "foo"

var localSym = Symbol();
Symbol.keyFor(localSym); // undefined

// well-known symbols are not symbols registered 
// in the global symbol registry
Symbol.keyFor(Symbol.iterator) // undefined
```

### Symbol.match (Firefox 40)

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/match

```
class Ga {
  constructor(base) {
    this.base = base;
  }
  [Symbol.match](target) {
    return this.base.indexOf(target) < 0 ? false : true;
  }
}

var ga = new Ga('sports');
'po'.match(ga); // true
```

### Symbol.species (Firefox 41)

* 

```
```

### Symbol.toPrimitive (Firefox 44)

* 

```
```

### Symbol.prototype[@@toPrimitive] (Firefox 44)

* 

```
```

### Symbol.replace (Firefox 49)

* 

```
```

### Symbol.search (Firefox 49)

* 

```
```

### Symbol.split (Firefox 49)

* 

```
```

### Symbol.hasInstance (Firefox 50)

* 

```
```

### Object.getOwnPropertySymbols()

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertySymbols
* Object.getOwnPropertySymbols(obj)

```
var obj = {};
var a = Symbol('a');
var b = Symbol.for('b');

obj[a] = 'localSymbol';
obj[b] = 'globalSymbol';

var objectSymbols = Object.getOwnPropertySymbols(obj);

console.log(objectSymbols.length); // 2
console.log(objectSymbols);        // [Symbol(a), Symbol(b)]
console.log(objectSymbols[0]);     // Symbol(a)
```

### JSON.stringify()

* https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify
* All symbol-keyed properties will be completely ignored, even when using the replacer function.
* Symbol은 변환하지 않음

```
// Symbols:
JSON.stringify({ x: undefined, y: Object, z: Symbol('') });
// '{}'
JSON.stringify({ [Symbol('foo')]: 'foo' });
// '{}'
JSON.stringify({ [Symbol.for('foo')]: 'foo' }, [Symbol.for('foo')]);
// '{}'
JSON.stringify({ [Symbol.for('foo')]: 'foo' }, function(k, v) {
  if (typeof k === 'symbol') {
    return 'a symbol';
  }
});
// '{}'
```

***

## Function
```
```

## Iterator
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