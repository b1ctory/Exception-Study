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



reference : https://velog.io/@delmasong/App-Delegate