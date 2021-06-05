#### TableView를 동작 방식과 화면에 Cell을 출력하기 위해 최소한 구현해야 하는 DataSource 메서드를 설명하시오.

1. 뷰 컨트롤러는 테이블 뷰의 데이터 소스와 델리게이트를 설정하고 reloadData 메시지를 보냅니다. 데이터 소스는 **UITableViewDataSource 프로토콜을 채택**해야하며 Delegate는 UITableViewDelegate 프로토콜을 채택해야합니다.
2. 데이터 소스는 UITableView 개체로부터 numberOfRowsInSection: 메시지를 수신하고 테이블보기의 섹션 수를 반환합니다. 이는 선택적 프로토콜 방법이지만 테이블보기에 둘 이상의 섹션이있는 경우 데이터 소스에서이를 구현해야합니다.
3. 각 섹션에 대해 데이터 소스는 tableView : numberOfRowsInSection : 메시지를 수신하고 섹션의 행 수를 반환하여 응답합니다.
4. 데이터 소스는 테이블 뷰에 표시되는 각 행에 대해 tableView : cellForRowAt : 메시지를 수신합니다.
   각 행에 대해 UITableViewCell 개체를 구성하고 반환하여 응답합니다. UITableView 개체는이 셀을 사용하여 행을 그립니다.

------

### 최소한 구현해야 하는 Method

1. func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int
2. func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell



reference : https://github.com/iOS-SOPT-iNNovation/iOS_Traning/issues/17

