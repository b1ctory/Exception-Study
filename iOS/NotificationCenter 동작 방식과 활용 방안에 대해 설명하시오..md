#### NotificationCenter 동작 방식과 활용 방안에 대해 설명하시오.

- 옵서버에 등록된 정보들의 broadcasting 을 하는 메커니즘
- notification을 받기 위해 `addObserver(_:selector:name:object:)` 혹은 `addObserver(forName:object:queue:using:)` 를 사용해 오브젝트를 notification center 에 등록

## NotificationCenter

- 등록된 observer에게 notification을 전달하는 클래스
- NotificationCenter 는 notification 을 발송하면 NotificationCenter에서 메세지를 전달한 observer를 처리할 때까지 대기합니다 (동기)

```swift
// 옵저버 등록
 NotificationCenter.default.addObserver(self, selector: 
		#selector(didRecieveTestNotification(_:)), 
		name: NSNotification.Name("TestNotification"), object: nil)

 @objc func didRecieveTestNotification(_ notification: Notification) {
         print("Test Notification")
 }
 
 ...
 
 // 노티피케이션 발송
 NotificationCenter.default.post(name: NSNotification.Name("TestNotification"), 
		object: nil, userInfo: nil)
```

- 동작 방식
  - 옵저버 등록
  - 시스템에서 등록된 옵저버를 감시하면서 변경사항이 발생하면 1을 등록한 객체에게 알려준다.
- 활용 방안
  - 다른 객체의 변경 사항을 알고 싶을 때 -> 화면의 가로세로가 전환되었을 때 등
- 동작 방식
  - 구성 요소
    - 객체 A : Listener
    - 객체 B : sender
    - NotificationCenter
  - 객체 A는 객체 B의 어떠한 행위를 관찰하기 위해서 NOtificationCenter에 옵저버 등록
  - 옵저버에는 어떤 객체를 관찰할 것인지 어떤 행위를 관찰할 것인지 등이 들어감
  - 객체 A가 어떠한 행위를 한다.
  - 객체 A는 알림을 생성하고 NotificationCenter에 Post함
  - NotificationCenter는 객체 B에게 등록한 옵저버에 대한 알림이 많이 발생했다고 알려줌