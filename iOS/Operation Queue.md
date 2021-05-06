### OperationQueue

`Operation`은 **태스크(작업)와 관련된 코드와 데이터를 나타내는 추상 클래스**입니다. `Operation Queue`는 연산(Operation)의 실행을 관리합니다. 대기열(Queue)에 추가한 동작은 직접 제거할 수 없습니다.

연산(Operation)은 **작업이 끝날 때까지 대기열에 남아 있습니다. 연산(Operation)을 대기열에서 제거하는 방법은 연산(Operation)을 취소하는 방법 뿐**입니다.

취소하는 방법은 연산 객체(Operation Object)의 `cancel()`메서드를 호출하거나 `Oeration Queue`의 `cancelAllOperations()` 메서드를 호출하여 대기열에 있는 모든 연산(Operation)을 취소하는 방법이 있습니다.

그리고 실행 중인 연산(Operation)의 경우 연산 객체(Operation Object)의 취소 상태를 확인하고 실행 중인 연산(Operation)을 중지하고 완료 상태로 변경됩니다.

#### **연산 객체(Operation Object)**

연산 객체 (Operation Object)는 **애플리케이션에서 수행하려는 연산(Operation)을 캡슐화하는 데 사용하는 `Foundation` 프레임 워크의 `Operation` 클래스 인스턴스**입니다.

