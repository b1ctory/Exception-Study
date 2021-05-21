### 타입 메소드 vs 인스턴스 메소드

- 인스턴스 메소드는 인스턴스를 만들고 내부 함수를 호출
- 인스턴스를 만들지 않고 함수를 호출하는 방법? -> 타입 메소드
- 타입 메소드란 타입 자체에서 호출을 할 수 있는 메소드

```swift
class Test {
	// 인스턴스 메소드
	func useInstance() -> String {
		return "instance"
	}
	
	// 타입 메소드 
	class func getSomething() -> String{
		return "type"
	}
}


// 호출할 때!
var nana = Test()
print(nana.useInstance())
// print(nana.getSomething()) // Error!
print(Test.getSomething())

출력 결과는 >>
instance
type
```

