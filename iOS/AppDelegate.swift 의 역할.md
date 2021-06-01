### AppDelegate.swift 의 역할

#### 1. AppDelegate 클래스 정의

app delegate(AppDelegate클래스의 인스턴스)는 앱 안에서 상태 변화에 응답하고, 앱의 컨텐츠가 그려지는 창(window)를 만든다. *-> 창을 만드는 부분은 SceneDelegate가 생기면서 그쪽으로 넘어감.*

#### 2. entry point(진입 지점)과 입력 이벤트(input events)를 앱에 전달하는 run loop 생성

이 작업은 `UIApplicationMain` 속성에 의해 완료된다. ( `@UIApplicationMain` 파일)
**`UIApplicationMain` 속성을 사용하는 것은 `UIApplicationMain` 함수를 호출하고 AppDelegate 클래스의 이름을 delegate 클래스의 이름으로 전달하는 것**과 같다. (UIApplicationMain 메서드의 인자로 들어갈 delegate 클래스 이름)

이에 대한 응답으로 시스템은 응용 프로그램 객체(application object)를 생성한다. 이 응용프로그램 객체는 앱의 생명주기를 관리한다. 시스템은 또한 AppDelegate 클래스의 인스턴스를 생성하고 응용프로그램 객체에 할당한다.

마침내 시스템이 앱을 시작한다.



```swift
//애플리케이션이 실행된 직후 사용자의 화면에 보여지기 직전에 호출 
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool	

//애플리케이션이 최초 실행될 때 호출되는 메소드 
func application(_ application: UIApplication, willFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) -> Bool		
//애플리케이션이 InActive 상태로 전환되기 직전에 호출 
func applicationWillResignActive(_ application: UIApplication)	

//애플리케이션이 백그라운드 상태로 전환된 직후 호출
func applicationDidEnterBackground(_ application: UIApplication)	

//애플리케이션이 Active 상태가 되기 직전, 화면에 보여지기 직전에 호출 
func applicationWillEnterForeground(_ application: UIApplication)	

//애플리케이션이 Active 상태로 전환된 직후 호출
func applicationDidBecomeActive(_ application: UIApplication)

//애플리케이션이 종료되기 직전에 호출 
func applicationWillTerminate(_ application: UIApplication)	
```



#### iOS 13부터 AppDelegate가 하는 일?

이전엔 앱이 foreground에 들어가거나 background로 이동할 때 앱의 상태를 업데이트하는 등의 **앱의 주요 생명주기 이벤를 관리**했었지만 이제는 더이상 하지 않는다.

1. 앱의 가장 중요한 데이터 구조를 초기화
2. 앱의 Scene을 환경설정 하는 것
3. 앱 밖에서 발생한 알림 (배터리 부족, 다운로드 완료 등)에 대응하는 것
4. 특정한 scenes, views, view controllers에 한정되지 않고 앱 자체를 타겟하는 이벤트에 대응하는 것
5. 애플 푸쉬 알림 서비스와 같이 실행시 요구되는 모든 서비스를 등록하는 것

#### Deployment Target이 iOS 13 미만인 상황에서는?

iOS 12 이하는 하나의 앱에 하나의 window를 가지고 있기 때문에 (즉, 멀티 window를 사용하지 않기 때문에) iOS 13에서 추가된 부분을 삭제하고 이전 버전과 설정을 똑같이 바꿔주면 이전 방식과 동일하게 사용할 수 있다.

1. SceneDelegate.swift 파일 삭제
2. iOS 13에서 AppDelegate에 추가된 UISceneSession과 관련된 두 메소드 삭제
3. iOS 13에서 Scene Delegate로 옮겨진 window 프로퍼티를 AppDelegate로 다시 옮기기
4. Info.plist 에서 Scene과 관련된 Manifest인 Application Scene Manifest 삭제



reference : https://velog.io/@delmasong/App-Delegate