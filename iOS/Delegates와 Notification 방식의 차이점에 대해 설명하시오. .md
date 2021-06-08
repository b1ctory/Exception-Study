#### Delegates와 Notification 방식의 차이점에 대해 설명하시오.

Delegate Pattern이란 필요한 동작들을 Protocol로 정의해 놓고, 어떤 작업이 필요할 때 위임자 인스턴스에게 protocol에 정의된 method들을 호출함으로써 작업을 **위임**하는 방식을 말합니다. 이 패턴의 장점은 위임자가 어떤 동작을 하는지, 혹은 **위임자가 어떤 형태인지 알 필요 없이 그저 필요한 시점에 필요한 메소드를 호출하도록 설계함으로써 관심사를 분리할 수 있습니다**. 예를 들어 흔히 사용하는 UITableView는 UITableViewDataSource protocol을 채택한 위임자를 가집니다. TableView를 그리기 위해 데이터가 필요하다면 UITableView는 Datasource 위임자에게 요청함 수 있습니다. 이러한 방식을 통해서 매번 UITableView를 커스텀할 필요 없이 같은 UITableView로 다른 모양과 다른 동작을 가지는 TableView를 구현할 수 있습니다.

Notification은 특정 이벤트가 발생했을 때 사전에 등록된 Notification 이름으로 알림이 발생했다는 것을 Notification Center에게 알려줍니다. 그럼 Notification Center는 해당 알림을 수신하겠다고 등록되어있는 곳에 다시 알려주는 방식입니다.

둘의 차이는 **Delegate Pattern은 알림을 발생시키는 주체와 그에 대응하는 위임자가 1:1로 소통한다는 것이고**, **Notification은 1:N로 하나의 알림을 여러 주체가 받을 수 있습니다. 그렇기 때문에 Notification을 사용할 때 의도하지 않은 곳에서 알림을 수신하고 있는 지 주의해야**합니다. 



reference : https://caution-dev.github.io/swift/2019/03/16/iOS-Q&A.html

