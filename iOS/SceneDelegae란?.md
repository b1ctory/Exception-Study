### SceneDelegae란?

1. iOS 12까지는 대부분 하나의 앱에 하나의 Window였지만, iOS 13 부터는 window의 개념이 Scene으로 대체되고 하나의 앱에서 여러 Scene을 가질 수 있다.  (아이패드의 분할 화면을 생각하면 됨)
2. AppDelegate의 역할 중 UI의 상태를 알 수 있는 **UILifeCycle에 대한 부분을 SceneDelegate가 담당하게 됐음**
3. 그리고 AppDelegate에 Session Lifecycle에 대한 역할이 추가되었다. 

#### Scene이란 무엇인가?

- UIKit은 UIWindowScene 객체를 사용하는 앱 UI의 각 인스턴스를 관리한다. Scene에는 UI의 하나의 인스턴스를 나타내는 windows와 view controllers가 들어있다. 또한 각 Scene에 해당하는 UIWindowSceneDelegate 객체를 가지고 있고, 이 객체는 UIKit과 앱 간의 상호 작용을 조정하는데 사용한다. Scene들을 같은 메모리와 앱 프로세스 공간을 공유하면서 서로 동시에 실행된다. 결과적으로 하나의 앱은 여러 Scene과 Scene Delegate 객체를 동시에 활성화할 수 있다. 

#### Scene Session?

UISceneSession 객체는 **scene의 고유의 런타임 인스턴스를 관리**한다. 사용자가 앱에 새로운 scene을 추가하거나 프로그래밍적으로 scene을 요청하면, 시스템은 그 scene을 추적하는 session 객체를 생성한다. 그 session에는 고유한 식별자와 scene의 구성 세부사항이 들어있다. UIKit은 session 정보를 그 scene자체의 생애 동안 유지하고, app switcher에서 사용자가 그 scene을 클로징하는 것에 대응하여 그 session을 파괴한다. session객체는 직접 생성하지 않고 UIKit가 앱의 사용자 인터페이스에 대응하여 생성한다. 

