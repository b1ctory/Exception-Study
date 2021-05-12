## 배열

> 배열은 일련의 순서를 가지는 리스트 형식의 값을 저장하는데에 사용되는 자료형

- 배열에 입력되는 개발 아이템들은 모두 각각의 순서가 있다. 이 순서를 **"인덱스"**라고 한다.
- 배열에서 인덱스는 순서대로 할당되며, 중간에 값을 생략하거나 건너뛰는 경우는 없다.
- 배열에 저장할 아이템의 타입에는 제약이 없지만, 하나의 배열에 저장하는 아이템 타입은 모두 동일해야 한다.
- 선언 시 배열에 저장할 아이템 타입을 명확히 정의해야 한다.
- 배열의 크기는 동적으로 확장할 수 있음

```swift
// 정적인 방식의 배열 선언
var cities = ["Seoul", "New York", "LA", "Santiago"]
```

🚀 **리터럴이란?** 값 자체이다. 값이 변수나 상수에 담긴 형태가 아니라, 그에 해당되는 값 자체를 리터럴이라고 한다.

```swift
// 배열의 아이템 참조
cities[0] // Seoul
```

### 배열 순회 탐색

```swift
var cities = ["Seoul", "New York", "LA", "Santiago"]
let length = cities.count // 배열의 길이 (4)

// for ~ in 구문을 이용하여 배열 순회 시에는 닫힌 범위 연산자를 사용하자
for i in 0..<length { 
	print("\\(i)번째 배열 원소는 \\(cities[i) 입니다.")
}

// iterator()를 이용하는 방식
// 배열값의 순회 특성 사용!
for row in cities {
	// 배열값의 인덱스 값을 찾고 싶다면?
	let index = cities.index(of: row) 
	print("\\(index)번째 배열 원소는 \\(row)입니다.")
}
```

### 배열의 동적 선언과 초기화

값을 할당하지 않은 빈 배열을 선언하고 초기화할 때는 두 가지 형식을 사용할 수 있다.

```swift
// 첫번쨰로
Array < 아이템 타입 > ()

// 두번째로
[ 아이템타입 ]()
```

- 사용 시점에서 < > 기호를 사용하여 배열 내부에서 사용할 아이템 타입을 지정하는 문법을 **제네릭** 이라고한다.
- 제네릭은 구조체나 클래스 외부에서 객체 내부에 사용될 타입을 지정할 수 있다는 점에서 동적 프로그래밍 영역으로 간주되기도 하는데, 생산성을 높여주는 문법이다.
- 동적으로 배열을 정의할 때에는 선언과 초기화 과정이 차례로 필요하다.
- **선언** : 이런 배열을 만들겁니다! 라고 컴파일러에 미리 알려주는 역할
- **초기화** : 앞서 선언한대로 실제로 만들어주세요! 라고 요청하는 과정

```swift
// 문자열 배열의 선언 및 초기화
var cities = Array<String>()
var cities = [String]()

// 문자열 배열을 선언
var cities: Array<String>
var cities: [String]

// 배열의 초기화
cities = Array()
cities = [String]() // - (1)
cities = [] // - (2)
```

- (1) 방식은 선언된 배열 그대로를 초기화
- (2) 방식은 빈 배열 하나를 새로 만들어서 이것을 변수에 할당. 엄밀히 말하면 두번째 방식은 초기화가 아니다.
- 이렇게 배열의 선언과 초기화 방법은 정말 다양하다. 필요에 따라서는 선언과 초기화 표현을 서로 섞어서 아래와 같이 쓰기도 한다. 어느 방식이 꼭 맞다! 라는것은 없으므로 각자 익숙한 형태로 사용하자.

```swift
var cities : [String] // 선언
cities = [String]() // 초기화

var country : [String] // 선언
country = [] // 초기화

var list : [Int] = [] // 타입 어노테이션 + 초기화

var rows : Array<Float> = [Float]() // 타입 어노테이션 + 제네릭 + 초기화

var tables : [String] = Array() // 타입 어노테이션 + 구방식의 초기화
```

- 배열이 비어있는지 체크하는 속성 `isEmpty`

```swift
var list = [String]()

if list.isEmpty {
	print("list is Empty")
} else {
	print("list contains \\(list.count) items")
}
```

### 배열 아이템 동적 추가

- 대표적인 메소드

```swift
append(_ :)
insert(_ :at:)
append(contentsOf:)
```

- `append(_ :)` : 입력된 값을 배열의 맨 뒤에 추가한다. 일반적으로 배열에서 존재하지 않는 인덱스에 접근하면 오류가 발생하므로 이 메소드는 아이템 추가 전에 먼저 배열의 크기를 +1만큼 확장하여 인덱스 공간을 확보한 후, 인자값을 마지막 인덱스 위치에 추가한다.
- `insert(_ :at:)` : 아이템을 배열의 맨 뒤가 아닌 원하는 위치에 직접 추가하고 싶을 때 사용한다.  at: 뒤에 입력되는 정수값은 인덱스의 위치를 의미한다. 이 인덱스에 값이 추가되면 해당 인덱스 기준 뒤의 인덱스들은 하나씩 다음으로 밀려난다.
- `append(contentsOf:)` : `append(_ :)` 메소드처럼 배열의 맨 마지막에 아이템을 추가하지만, 개별 아이템이 아니라 여러 개의 아이템을 배열에 한꺼번에 추가할 때 사용하는 메소드이다. 이를 위해 메소드의 인자값은 항상 배열이어야 한다.

```swift
var cities = [String]() // []

cities.append("Seoul") // ["Seoul"]
cities.append("New York") // ["Seoul", "New York"]
cities.insert("Tokyo", at: 1) //["Seoul", "Tokyo", "New York"]
cities.append(contentsOf: ["Dubai", "Sydney"]) // ["Seoul", "Tokyo", "New York", "Dubai", "Sydney"]
```

- 입력된 값을 변경하고 싶을 때는

```swift
cities[2] = "Madrid"

-> 2번 index 항목이 "Madrid"로 변경!
```

- 인덱스를 이용하여 위처럼 기존 내용을 수정할 수는 있지만, 처음부터 `cities[0] = "AA"` 라고 배열에 값을 추가해줄 수는 없다. → **배열의 잘못된 인덱스 참조로 인한 오류!**

  → 아직 배열에는 0번째 인덱스의 공간이 생성되지 않았는데 그 곳에 값을 할당하려고 했기 때문이다.

- 다만 코코아 터치 프레임워크에서는 배열 초기화 시에 배열의 크기를 지정할 수 있는 구문을 제공한다.

```swift
var cities = Array(repeating: "None", count:3)
var cities = [String](repeating: "None", count:3)

// 위의 두 구문을 이용하여 배열을 생성하면 배열의 크기가 3이고 배열의 아이템에는 None이라는 값이 기본값으로 입력된다. 
```

### 범위 연산자를 이용한 인덱스 참조

```swift
var alphabet = ["a", "b", "c", "d", "e"]

alphabet[0...2] // ["a", "b", "c"]

alphaber[0...2] = ["A"] 

// -> alphabet = ["A", "d", "e"]
```

## 집합

> 같은 타입의 서로 다른 값을 중복 없이 저장하고자 할 때 사용하는 집단 자료형

- 집합은 배열과 매우 유사하지만, 배열을 사용하기에는 순서가 그다지 중요하지 않은 데이터들이거나 중복 없이 한 번만 저장되어야 하는 데이터들을 다룰 때 배열 대신 사용할 수 있는 자료형이다.

### 집합의 정의

```swift
var genres : Set = ["Classic", "Rock", "Balad"]
```

- 원래 집합은 배열처럼 저장할 아이템의 타입을 명시하는 것이 원칙이다. 그러나, 지금처럼 초기값이 처음부터 할당되어 타입 추론이 가능할 경우 생략 가능.

```swift
Set< 아이템 타입 > ()

var genres = Set<String>()
genres.insert("Classic")
```

- 배열과 마찬가지로 count 속성으로 길이를 알아낼 수 있고, isEmpty 속성을 이용하여 집합이 비었는지 여부 확인 가능

### 집합 순회 탐색

- 배열은 index 탐색은 안된다. 순서가 중요하지 않으니까.

```swift
var genres : Set = ["Classic", "Rock", "Balad"]

for g in genres {
	print("\\(g)")
}

// sort() 메소드를 사용하면 정렬된 결과를 받을 수 있다.
for g in genres.sorted() {
	print("\\(g)")
}

// 출력 결과
Balad
Classic
Rock
```

### 집합의 동적 추가와 삭제

```swift
genres.insert("Jazz") // 추가
genres.remove("Rock") // 삭제
genres.removeAll() // 모든 아이템 삭제
```

- `contains(_ :)` 메소드는 인자값으로 입력된 데이터를 사용하여 해당 집합 내에서 일치하는 값이 있는지 검색하여 있으면 true 없으면 false  반환

### 기본 집합 연산

- `intersection(_ : )` : 교집합
- `symmetricDifference(_ : )` : 양 쪽 집합 모두에 공통으로 있는 아이템 제외
- `union(_ :)` : 합집합 / 공통으로 가진 아이템 중복 추가 X
- `subtract(_ : )` : 차집합

### 부분집합과 포함관계 판단 연산

집합 A와 B의 아이템이 모두 일치할 때 A == B가 정립하며, 이와 동시에 두 집합은 서로의 부분집합이 될 수 있다. 스위프트는 집합 자료형에 대해 부분집합 관계를 확인해주는 메소드를 제공하는데, 대표적으로 5개의 메소드가 사용된다.

- `isSubset(of: )` : 주어진 집합의 값 전체가 특정 집합에 포함되는지 판단하여 true, false 반환.
- `isSuperset(of: )` : 주어진 집합이 특정 집합의 **모든** 값을 포함하는지를 판단하여 true, false를 반환
- `isStrictSubset(of: )` , `isStrictSuperset(of: )` : 위의 두 메소드처럼 주어진 집합이 특정 집합의 부분집합인지 상위집합인지를 판단하는 역할을 하지만 두 집합이 서로 같은 경우의 결과값이 다르게 반환된다. 두 집합이 서로 일치할 경우 수학적으로는 서로가 서로의 부분집합이자 상위집합이 될 수 있으므로 isSubset(of:)와 isSuperset(of:) 메소드가 true를 반환하는 반면, **이 두 메소드는 더 엄격하게 판단하여 정확하게 부분집합이거나 상위집합일때만 true를 반환**한다. 서로 일치하는 집합은 동일 집합으로 판단할 뿐 부분집합 or 상위집합으로 판단하지 않는다는 뜻이다.
- `isDisjoint(with : )` : 두 집합 사이의 공통 값을 확인하여 아무런 공통 값이 없을 때 true를 공통 값이 하나라도 있으면 false 반환

### 중복이 제거된 배열 만들기

```swift
var A = [ 4, 2, 5, 1, 7, 4, 9, 11, 3, 5, 4 ] // 배열

let B = Set(A) // 집합
A = Array(B) // 중복이 제거된 배열
```

## 튜플

> 튜플은 스위프트에서 제공하는 특별한 성격의 집단 자료형

- 튜플은 하나의 튜플에 여러가지 타입의 아이템을 저장할 수 있지만, 일단 선언되고 나면 상수적 성격을 띄므로 더 이상 값을 추가하거나 삭제하는 등의 변경이 안된다.

```swift
( <튜플 아이템1> , <튜플 아이템2> , ... )

let tuple = ("a", "b", 2, true)

tuple.0 // "a"
```

- 튜플은 별도의 선언 구문이 없지만 타입 어노테이션을 사용하기 위한 타입을 정의할 수는 있다.

```swift
var tpl : (Int, Int) = (100, 200)
```

- 튜플의 아이템을 개별 변수나 상수로 각각 할당받는 바인딩 방식의 구문도 제공한다.

```swift
let tupleValue : (String, Character, Int, Float, Bool) = ("a", "b", 1, 2.5, true)
let (a, b, c, d, e) = tupleValue

// a = "a"
// b = "b"
// c = 1
// d = 2.5
// e = true
```

- 튜플이 진가를 발휘하는 곳은 아무래도 함수 혹은 메소드에서 이다. 함수나 메소드에서 둘 이상의 값을 반환하려면 별도의 자료형 객체를 만들거나 배열 또는 딕셔너리를 만들어 담아야 하는데, 이럴 때 튜플을 이용하면 편리하다.

  ✔️ 함수와 메소드의 차이? : https://zeddios.tistory.com/233 (Zedd님 블로그 참고!)

```swift
func getTupleValue -> (String, String, Int) {
	return ("t", "v", 199)
}

// 함수가 반환하는 튜플을 상수로 바인딩
let (a, b, c) = getTupleValue()
```

## 딕셔너리

> 고유 키와 그에 대응하는 값을 연결하여 데이터를 저장하는 자료형이다.

🤔 Java를 주 언어로 사용해왔던 필자에게는 Java의 Hashmap과 비슷하다는 생각을 했다.

```swift
[ 키 : 데이터, 키 : 데이터, ... ]
```

- 하나의 키는 하나의 데이터에만 연결되어야 한다.
- 하나의 딕셔너리에서 키는 중복될 수 없다. 중복해서 선언하면 아이템 추가가 아니라 수정이 이루어져 기존 키에 연결된 데이터가 제거된다.
- 저장할 수 있는 데이터 타입에는 제한이 없지만, 하나의 딕셔너리에 저장하는 데이터 타입은 모두 일치해야 한다.
- 딕셔너리의 아이템에는 순서가 없지만 키에는 내부적으로 순서가 있으므로 for ~ in 구문을 이용한 순회 탐색이 가능하다.
- 딕셔너리에서 사용할 수 있는 키의 타입은 거의 제한이 없으나 해시 연산이 가능한 타입이어야 한다.

```swift
var capital = ["KR" : "Seoul", "EN" , "London"]
```

### 딕셔너리의 선언과 초기화

```swift
Dictionary< 키의 타입, 값의 타입 > () // 선언
Dictionary<String, Int> ()

[ 키로 사용할 타입 : 값으로 사용할 타입 ]() // 초기화
[String : Int]()

// 딕셔너리의 선언과 초기화
var capital = Dictionary<String, String>() // 방법 1
var capital = [String : String]() // 방법 2
```

### 딕셔너리에 동적으로 아이템 추가

```swift
var newCapital = [String:String]()
newCapital["JP"] = "Tokyo"

if newCapital.isEnpty { // 비어있는지 확인
	... 
}

// "KR" : "Seoul" 데이터가 추가되고 nil 리턴함
newCapital.updateValue("Seoul", forKey: "KR")

// "JP" : "Sapporo" 데이터가 추가되고 "Tokyo" 리턴함
newCapital.updateValue("Sapporo", forKey: "JP")
```

### 아이템 제거

```swift
newCapital["KR"] = nil // 방법 1
newCapital.removeValue(forKey: "KR") // 방법 2
```

- 딕셔너리는 키와 값에 대한 보장이 없다. 배열은 값을 저장할 때 만들어져있지 않은 인덱스라면 오류를 발생시키기만 하면 된다. 하지만 딕셔너리는 고유 키에 대한 제약이 덜하다보니 프로그램이 이 딕셔너리로부터 키를 호출해서 저장된 값을 불러올 때 없는 키를 호출했을 가능성을 염두에 두어야 한다. 그래서 **스위프트에서는 딕셔너리로부터 키를 호출해서 저장된 값을 불러올 때 혹은 업데이트 메소드를 실행한 결과를 반환할 때, 오류가 발생할 가능성을 염두에 둔 `Optional("Seoul")` 타입으로 반환**한다.

  → Optional에 대한 내용은 뒷 부분에서 다시 다룬다.

### 딕셔너리 순회 탐색

- 딕셔너리를 순회탐색하면 입력한 값의 순서대로 탐색되지 않는다는 점이다. 기본적으로 딕셔너리는 고유 키에 대한 해시 처리 값을 기준으로 내부 정렬하기 때문에 데이터가 우리가 생각한대로 정렬되지 않는다는 것을 항상 생각하자

```swift
for row in newCapital {
	let (key, value) = row
	print("\\(key) : \\(value)")
}

for (key, value) in new Capital {
	print("\\(key) : \\(value)")
}
```