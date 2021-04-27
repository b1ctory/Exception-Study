### ARC(Automatic Reference Counting)

- **ARC란**?
  - **ARC** (Automatic Reference Counting)란, 자동 레퍼런스 카운팅으로서 자동으로 메모리를 관리해주는 방식을 말한다. 참조 카운팅이 0이 될때만 메모리에서 해제한다는 뜻이다.
- **동작 원리**
  - 클래스의 새로운 인스턴스를 만들 때 ARC는 인스턴스의 정보를 저장하기 위해 메모리를 할당한다. 또한 ARC는 인스턴스가 더 이상 사용되지 (참조 카운팅 0) 않는다고 판단하면 메모리를 해제한다. 레퍼런스 프로퍼티에 인스턴스를 할당하면 ARC는 참조되는 프로퍼티의 갯수를 카운팅하여 참조하는 모든 변수가 인스턴스를 해제하기 전에 ARC는 인스턴스를 메모리에서 해제하지 않는다.
- **동작 시점**
  - **컴파일 시점**에 동작한다.
- **구체적인 예시 설명**

```java
class Person {
    let name: String
    init(name: String) {
        self.name = name
        println("\\(name) is being initialized")
    }

    deinit {
        println("\\(name) is being deinitialized")
    }
}
```

- Person 클래스는 이니셜라이저를 가지며 인스턴스의 name 속성을 설정하고 초기화 진행 중이다고 표시하는 메시지를 출력
- Person 클래스는 디이니셜라이저를 가지며 클래스의 인스턴스가 해제될 때 메시지를 출력

```swift
// Person 클래스 타입을 갖는 reference 변수 3개를 선언. 모두 옵셔널 변수이므로 초기값은 nil을 갖고 있습니다.
var reference1: Person?
var reference2: Person?
var reference3: Person?

//reference1 변수에 Person 인스턴스 생성하여 참조하게됩니다.
reference1 = Person(name: "John Appleseed")

//나머지 두 변수를 reference1를 참조하게 합니다.
reference2 = reference1
reference3 = reference1

/*이시점의 인스턴스에 대한 참조 횟수는 3이된다. 그런 후 reference1, reference2 참조 해지합니다. 
그렇게 되면 Person 인스턴스에 대한 참조 횟수는 아직 1이어서 Person 인스턴스는 해지되지 않습니다.*/
reference1 = nil
reference2 = nil

/*
Pesron 인스턴스를 참조하고 있는 나머지 변수 refernce3의 참조 해지하면 
더이상 Person 인스턴스를 참조하고 있는 것이 없으므로 ARC가 Person 인스턴스 메모리를 해지합니다.
*/
reference3 = nil
```

#### ARC와 GC의 차이점

- **참조 카운팅 시점** : ARC는 컴파일시 / GC는 프로그램 동작 중

- **장점**
  - ARC
    - 컴파일 당시 이미 인스턴스의 해제 시점이 정해져 있어서 인스턴스가 언제 메모리에서 해제될지 예측할 수 있다.
    - 컴파일 당시 이미 인스턴스의 해제 시점이 정해져 있어서 메모리 관리를 위한 시스템 자원을 추가할 필요가 없다.
  - GC
    - 상호 참조 상황 등의 복잡한 상황에서도 인스턴스를 해제할 수 있는 가능성이 더 높다.
    - 특별히 규칙에 신경 쓸 필요가 없다.
- 단점
  - ARC
    - ARC의 작동 규칙을 모르고 사용하면 인스턴스가 메모리에서 영원히 해제되지 않을 수 있다.
  - GC
    - 프로그램 동작 외에 메모리 감시를 위한 추가 자원이 필요하므로 한정적인 자원 환경에서는 성능 저하 발생 가능
    - 명확한 규칙이 없기 때문에 인스턴스가 정확히 언제 메모리에서 해제될지 예측이 어려움







