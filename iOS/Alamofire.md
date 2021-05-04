### **Alamofire**

- iOS, macOS에서 HTTP통신을 할 때 필수 라이브러리

- **Alamofire는 iOS, macOS를 위한 스위프트 기반 HTTP 네트워킹 라이브러리**로 Apple의 Foundation networking 기반으로 인터페이스를 제공하여 일반적인 네트워킹 작업을 단순화

- Alamofire를 사용한다면 데이터를 접근하기 위한 노력을 줄일 수 있으며 **코드를 더 깔끔하고 가독성 있게 쓰는 것이 가능**해짐

- Alamofire는 함께 사용가능한(chainable) request/response 매소드들, JSON 파라미터, 응답 직렬화(response serialization), 인증(authentication) 그리고 많은 다른 기능을 제공

- Alamofire의 설치는 cocoapod을 이용한다.
- Alamofire은 비동기(asynchronously)로 네트워크 연동을 하기 때문에 서버로부터 응답을 받을 때까지 기다리지 않고 콜백을 통해서 응답을 처리해준다. 따라서 요청에 대한 응답은 이를 처리하는 핸들러 안에서만 유효하므로 수신한 응답이나 데이터에 의존적인 동작들은 반드시 해당 핸들러 내에서 완료 해야한다.
  - **Handler ?**
    - 서로 다른 스레드간의 통신을 위한 장치로 쓰인다.
    - 데이터를 받고 보내는 중간 브로커의 역할
- Alamofire는 **Request뿐만 아니라 Upload, Download등 여러가지를 지원**하며 그에 맞는 기능을 최대한 편하게, 간결하게 사용할 수 있도록 제공한다.



Reference : https://www.zehye.kr/ios/2020/04/01/12iOS_alamofire/