### Protocol

> 프로토콜 : 클래스나 구조체가 어떤 기준을 만족하거나 특수한 목적을 달성하기 위해 구현해야 하는 메소드와 프로퍼티의 목록

🚀 **명세** : 프로토콜에 선언된 프로퍼티나 메소드의 형식

🚀 **프로토콜을 구현한다** : 이 명세에 맞추어 실질적인 내용을 작성하는 것

#### 프로토콜의 정의

```swift
protocol <프로토콜명> {
	<구현해야 할 프로퍼티 명세 1>
	<구현해야 할 프로퍼티 명세 2>
	<구현해야 할 프로퍼티 명세 3>

	...

	<구현해야 할 메소드 명세 1>
	<구현해야 할 메소드 명세 2>
	<구현해야 할 메소드 명세 3>
	
	...
}
```

#### 프로토콜 프로퍼티

프로토콜에 선언되는 프로퍼티에는 **초기값을 할당할 수 없다**. 연산 프로퍼티인지 저장 프로퍼티인지도 구분하지 않는다. **프로퍼티의 종류, 이름, 변수/상수 구분, 타입, 읽기 전용인지 읽고 쓰기가 가능한지에 대해서만 정의**할 뿐이다.

```swift
protocol SomePropertyProtocol {
	var name: String { get set }
	var description: String { get }
}
```

- get : 읽기 전용 속성 → 저장 프로퍼티 구현할 수 없다.
- get set : 읽고 쓸 수 있는 프로퍼티

#### 프로토콜 메소드

```swift
protocol SomeMethodProtocol {
	func execute(cmd: String)
	func showPort(p: Int) -> String
}
```

- 프로토콜에 선언되는 메소드는 메소드 종류, 이름, 파라미터 타입, 파라미터 이름, 반환 타입까지는 정의할 수 있지만 실제 실행할 내용을 작성할 수는 없다.
- 메소드의 실질적인 내용 작성을 담당하는 것은 구현체, 즉 프로토콜을 구현하는 구조체나 클래스, 열거형, 혹은 익스텐션의 역할이다.
- **내부 매개변수의 경우에는 프로토콜을 그대로 따르지 않고 필요한 대로 변형하여 사용하는 것이 가능**하다. 단, 어떤 경우에도 **프로토콜에 정의된 메소드명과 외부 파라미터명은 항상 그대로 따라야한다.**
