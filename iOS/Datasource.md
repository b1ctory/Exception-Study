### Datasource

- 데이터를 받아 뷰를 그려주는 역할을 한다.
  - 너는 어떻게 뭘 보여줄거냐? 를 담당하는 것이 Datasource
- 테이블뷰 데이터 소스 객체는 `UITableViewDataSource` 프로토콜을 채택한다.
- 데이터 소스는 테이블 뷰를 생성하고 수정하는데 필요한 정보를 테이블뷰 객체에 제공한다.
- 데이터 소스는 데이터 모델의 델리게이트로, 테이블뷰의 시각적 모양에 대한 최소한의 정보를 제공한다.

- `UITableView` 객체에 섹션의 수와 행의 수를 알려주며, 행의 삽입, 삭제 및 재정렬하는 기능을 선택적으로 구현할 수 있다.

- `UITableViewDataSource` 프로토콜의 주요 메서드는 아래와 같다. 이 중 `@required`로 선언된 두 가지 메서드는 `UITableViewDataSource` 프로토콜을 채택한 타입에 필수로 구현해야 한다

  ```swift
  @required 
   // 특정 위치에 표시할 셀을 요청하는 메서드
   func tableView(UITableView, cellForRowAt: IndexPath) 
   
   // 각 섹션에 표시할 행의 개수를 묻는 메서드
   func tableView(UITableView, numberOfRowsInSection: Int)
   
   @optional
   // 테이블뷰의 총 섹션 개수를 묻는 메서드
   func numberOfSections(in: UITableView)
   
   // 특정 섹션의 헤더 혹은 푸터 타이틀을 묻는 메서드
   func tableView(UITableView, titleForHeaderInSection: Int)
   func tableView(UITableView, titleForFooterInSection: Int)
   
   // 특정 위치의 행을 삭제 또는 추가 요청하는 메서드
   func tableView(UITableView, commit: UITableViewCellEditingStyle, forRowAt: IndexPath)
   
   // 특정 위치의 행이 편집 가능한지 묻는 메서드
   func tableView(UITableView, canEditRowAt: IndexPath)
  
   // 특정 위치의 행을 재정렬 할 수 있는지 묻는 메서드
   func tableView(UITableView, canMoveRowAt: IndexPath)
   
   // 특정 위치의 행을 다른 위치로 옮기는 메서드
   func tableView(UITableView, moveRowAt: IndexPath, to: IndexPath)
  ```

  