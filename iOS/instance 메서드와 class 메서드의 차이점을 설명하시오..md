#### instance 메서드와 class 메서드의 차이점을 설명하시오.

- instance 메소드
  - 특정 클래스, 구조체, 열거형의 인스턴스에 속하는 함수
  - 인스턴스 프로퍼티 접근 및 수정을 제공하거나 인스턴스의 목적과 관련된 기능을 제공한다.

```swift
class Person {
	var name: String?
	func changeName(name: String) {
		self.name = name 
	}
}

var personA = Person()
personA.changeName(name: "jeff")
```

- class 메소드
  - Class 메소드는 클래스에서만 사용 가능하므로 struct, enumeration 에서는 사용이 불가능하다. 
  - static 키워드는 서브 클래스에서 override 할 수 없는 타입 메소드
  - class 메소드는 서브클래스에서 override 할 수 있다,

```swift
class Person {
	var name: String?
	func changeName(name: String) {
		self.name = name 
	}
}

var personA = Person()
personA.changeName(name: "jeff")
```

