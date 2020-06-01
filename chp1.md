# Chapter1. 스위프트 기초



## Swift 네이밍 규칙

​	기본적으로 Camel Case 사용

* Lower Camel Case : 함수, 메소드, 변수, 상수
  * ex) someVariableName
* Upper Camel Case : class, sturct, enum, extension ...
  * ex) Person, Poinnt

> Swift는 모든 대소문자를 구분합니다.

## 콘솔 로그

* print
  * 단순 문자열 출력
* dump
  * 인스턴스 자세한 설명(description)까지 출력

```swift
/* 콘솔 로그 */

import swift

class Person {
  var name: String = "mango906"
  var age: Int = 20
}

let mango: Person = Person()

print(mango)

/*
	__lldb_expr_1.Person
*/

dump(mango)

/* 
▿ __lldb_expr_1.Person #0
  - name: "mango906"
  - age: 20
*/

//훨씬 자세히 나옴

```

## 문자열 보간법

* 프로그램 실행 중 문자열 내에 변수 또는 상수의 실질적인 값을 표현하기 위해 사용
* \\()

```swift
/* 문자열 보간법 예시 */

import Swift

let age: Int = 10
"안녕하세요! 저는 \(age)살 입니다"

// "안녕하세요! 저는 10살입니다"

print("안녕하세요! 저는 \(age + 5)살입니다")
	
```

## 변수와 상수

```swift
/* 변수와 상수 */

import Swift

// 상수 선언 키워드 let
// 변수 선언 키워드 var

// 상수 선언
// let 이름 : 타입 = 값
let constant: String = "상수입니다."

// 변수 선언
// var 이름 : 타입 = 값
var variable = String = "변수입니다."

variable = "변수입니다22"	// 변수는 값을 변경할 수 있지만
const = "상수입니다22" // 상수는 바꿀 수 없습니다. (오류 발생)

// 상수 선언 후에 나중에 값 할당하기

// 나중에 할당하려고 하는 상수나 변수는 타입을 꼭 명시해주어야 합니다.
let sum: Int
let inputA: Int = 100
let inputB: Int = 200

// 선언 후 첫 할당
sum = inputA + inputB

sum = 1 // 그 이후에 다시 값을 바꿀수 없음 (오류 발생)

// 변수도 차후에 할당하는 것이 가능합니다
var nickName: String
print(nickName)	// 초기화가 되어 있지 않아서 오류 발생
nickName = "mango906"

// 변수는 차후에 다시 다른 값을 할당해도 문제가 없습니다.
nickName = "민경빈"



```

## 기본 데이터 타입

#### swift의 기본 데이터 타입

* Bool
  * true, false로 값을 가지는 타입
* Int
  * 정수 타입, 64비트 정수형
* UInt 
  * 양의 정수 타입, 64비트 양의 정수형
* Float 
  * 실수 타입, 32비트 부동소수형
* Double
  * 실수 타입, 64비트 부동소수형
* Character (한 글자)
  * 문자 타입, 유니코드 사용, 큰따옴표("") 사용, 1글자만 사용할때 사용
* String
  * 문자 타입, 유니코드 사용, 큰따옴표("") 사용

```swift
/* 기본 데이터 타입 */
import UIKit

// Swift의 기본 데이터 타입
// Bool
var someBool: Bool = true
someBool = false

// Int
var someInt: Int = -100

// UInt
var someUInt: UInt = 100
someUInt = someInt // 자료형이 달라서 오류 뱉음 (UInt -> Int)

// Float
var someFloat: Float = 3.14
someFloat = 3

// Double
var someDouble: Double = 3.14
someDouble = 3
someDouble = someFloat // 자료형이 달라서 오류 뱉음 (Double -> Float)

// Character
var someCharacter: Character = "😎"

// String
var someString: String "하하하 😁 "
someString = someString + "웃으면 복이와요"
print(someString)	// 하하하 😁 웃으면 복이와요

someString = someCharacter // 자료형이 달라서 오류 뱉음 (String -> Character)

```

## Any, AnyObject, nil

* Any - Swift의 모든 타입을 지칭하는 키워드
* AnyObject - 모든 클래스 타이븡ㄹ 지칭하는 프로토콜
* Nil - 없음을 의미하는 키워드 `null` 과 똑같다고 보면됨

```swift
/* Any, AnyObject, nil */

import Swift

// Any
var someAny: Any = 100
someAny = "어떤 타입도 수용 가능합니다"
someAny = 123.12

let someDouble: Double = someAny	// 자료형이 안맞아서 오류 (Double -> Any)

// AnyObject
class SomeClass {}

var someAnyObject: AnyObject = SomeClass()

someAnyObject = 123.12	// 

// nil

someAny = nil	// Any는 빈값은 들어올 수 없음
someAnyObject = nil	// AnyObject는 빈값은 들어올 수 없음

```

