#### Foundation Kit은 무엇이고 포함되어 있는 클래스들은 어떤 것이 있는지 설명하시오.

Foundation은 원시 데이터 타입(String, Int, Double), 컬렉션 타입(Array, Dictionary, Set) 및 운영체제 서비스를 사용해 애플리케이션의 기본적인 기능을 관리하는 프레임워크 입니다.

- Foundation 프레임워크는 데이터 타입, 날짜 및 시간 계산, 필터 및 정렬, 네트워킹 등의 기본 기능을 제공합니다.
- Foundation 프레임워크에서 정의한 클래스, 프로토콜 및 데이터 타입은 iOS뿐만 아니라 macOS, watchOS, tvOS 등 모든 애플 SDK에서 사용됩니다.

*Foundation에서 제공하는 데이터 타입 및 컬렉션 타입의 대부분은 Objective-C 언어의 기능에서 지원하지 않는 것이기 때문에 언어기능을 보완하기 위한 구현이며, Swift에서는 이에 해당하는 데이터 타입과 기능 대부분을 [Swift 표준 라이브러리](https://developer.apple.com/documentation/swift)에서 제공합니다.*

- Number, Data, String: 원시 데이터 타입 사용
- Collection: Array, Dictionary, Set 등과 같은 컬렉션 타입 사용
- Date and Time: 날짜와 시간을 계산하거나 비교하는 작업
- Unit and Measurement: 물리적 차원을 숫자로 표현 및 관련 단위 간 변환 기능
- Data Formatting: 숫자, 날짜, 측정값 등을 문자열로 변환 또는 반대 작업
- Filter and Sorting: 컬렉션의 요소를 검사하거나 정렬하는 작업

##### **애플리케이션 지원**

- Resources: 애플리케이션의 에셋과 번들 데이터에 접근 지원
- Notification: 정보를 퍼뜨리거나 받아들이기는 기능 지원
- App Extension: 확장 애플리케이션과의 상호작용 지원
- Error and Exceptions: API와의 상호작용에서 발생할 수 있는 문제 상황에 대처할 수 있는 기능 지원