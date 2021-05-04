### Cocoa Touch

#### **코코아 터치 계층(Cocoa Touch Layer)**

Cocoa 는 **데스크톱 운영 체제 macOS를 위한 Apple 의 기본 객체 지향 응용 프로그래밍 인터페이스** (API)

**코코아 터치 계층은 iOS 애플리케이션 개발에 주 축을 이루는 개발환경**으로, **애플리케이션의 다양한 기능 구현에 필요한 여러 프레임워크를 포함하는 최상위 프레임워크 계층**입니다. 

- '코코아'라는 단어는 **Objective-C 런타임을 기반**으로하고, **NSObject를 상속받는 모든 클래스 또는 객체를 가리킬 때 사용**합니다.
- '코코아 터치' 또는 '코코아'는 iOS 또는 macOS의 전반적인 기능을 활용해 애플리케이션을 제작할 때 사용하는 프레임워크 계층입니다.
- '코코아 터치'는 핵심 프레임워크인 **UIKit과 Foundation을 포함**합니다.

- Mapkit, CoreData, CoreAnimation도 포함하고 있습니다. 



#### Cocoa & Cocoa Touch를 구성하는 핵심 Frameworks

1. **Foundation** : 가장 기반이 되고 필수적인 기능을 정의한 Framework이다. 앱 개발을 위한 기반 기능을 제공한다. Foundation은 Obj-c로 구현되어 있었으나 Swift가 등장하면서 동일 API를 Swift로 구현하여 사용할 수 있게 되었다.

2. **UIKit** : User Interface 개발 목적으로 만들어진 Framework

   Appkit과 user interface에 대한 목적은 같지만 Platform이 다르다. AppKit은 OS X, UIKit은 iOS, tvOS

3. **Core Data** : 앱에서 지속되어야 하는 데이터를 관리하고 싶을 때 사용한다.