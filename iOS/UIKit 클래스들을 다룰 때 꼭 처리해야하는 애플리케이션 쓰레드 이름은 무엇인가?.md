#### UIKit 클래스들을 다룰 때 꼭 처리해야하는 애플리케이션 쓰레드 이름은 무엇인가?

Main

**UIKit 클래스는 앱의 main thread에서만 사용해야 합니다. 이는** **UIResponder에서 파생되거나 앱의 사용자 인터페이스를 조작하는 것과 관련하여 특히 그렇습니다.**

 



출처: https://zeddios.tistory.com/519 [ZeddiOS]