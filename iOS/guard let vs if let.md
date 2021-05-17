### guard let vs if let

#### guard let 

```swift
// guard let
func printHi() {
  var value: String?
  value = "Hi"
  print(value) // Optional("Hi")
  guard let hi = value else { return }
  print(hi) // "Hi"
  // hi 변수는 메소드 내에서 지역상수처럼 사용할 수 있다.
}
```

- guard 뒤에 따라붙는 코드의 실행 결과가 true일 때 코드가 계속 실행된다. 
- if 구문과는 다르게 guard 구문은 항상 else 구문이 뒤에 따라와야 한다.
- 만약 guard 뒤에 따라오는 Bool 값이 false라면 else 블록 내부 코드를 실행한다.
  - 이 내부 코드에는 자신보다 상위 코드 블록을 종료하는 코드가 반드시 들어가게 된다.
  - 코드 블록 종료시 `return, break, continue, throw` 등 제어문 전환 명령을 사용한다.
- Bool 타입의 값으로 guard문을 동작시킬 수 있지만 옵셔널 바인딩 역할도 가능하다.
  - 이렇게 사용하면 guard로 옵셔널 바인딩 된 상수를 guard 구문 실행 코드 아래부터 함수 내부의 지역 상수처럼 사용할 수 있다.
- guard let으로 할 경우 쉼표로 추가조건을 나열할 수 있고 조건은 Bool 타입 값이어야 한다. 쉼표로 나열한다는 것은 AND 논리연산자와 같은 결과이고 쉼표를 &&으로 치환할 수 있다.
- guard 구문 사용시 if 코드를 훨씬 간결하고 읽기 좋게 구성할 수 있다.
- 예외사항만을 처리하고 싶다면 guard 구문을 사용하는 것이 훨씬 간편하다.
- 단, guard는 제어문 전환 명령어를 쓸 수 없는 상황이라면 사용이 불가하다. 함수나 반복문 등 특정 블록 내부에 위치하지 않는다면 사용이 제한된다.



#### if let

```swift
// if let
func printHi() {
  var value: String?
  value = "Hi"
  print(value) // Optional("Hi")
  
  if let hi = value {
    print(name) // Hi
  }
  // hi 변수는 메소드 내에서 지역상수처럼 사용 가능
}
```



reference: https://velog.io/@dev-lena/guard-let%EA%B3%BC-if-let%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90