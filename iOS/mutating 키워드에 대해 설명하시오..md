#### mutating 키워드에 대해 설명하시오.

mutating은 Swift에서 값 복사 형태의 Struct 에서 멤버 변수의 값을 변경하고자 할 때 함수를 통해 멤버 변수의 값을 변경할 수 있도록 하는 키워드이다. 

```swift
struct Point {
	var x = 0.0, y = 0.0
	mutating func move(x deltaX: Double, y deltaY: Double) {
		x += deltaX
		y += deltaY
	}
}
```

