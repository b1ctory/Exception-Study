### View Life Cycle

앱은 하나 이상의 뷰로 구성이 되어 있으며, 각각의 뷰들은 라이프 사이클을 가지고 있습니다. 따라서 뷰의 라이프 사이클을 고려해서 로직을 넣고, 구성해야 합니다.

각각의 메소드를 보면 네이밍이 비슷하고 Did 와 Will 의 차이가 있는 것을 알 수 있습니다. 하나씩 살펴보겠습니다.

- `ViewDidLoad` : 뷰 컨트롤러 클래스가 생성될 때, 가장 먼저 실행됩니다. 특별한 경우가 아니라면 **딱 한 번** 실행되기 때문에 초기화 할 때 사용 할 수 있습니다.
- `ViewWillAppear` : 뷰가 생성되기 직전에 **항상** 실행이 되기 때문에 뷰가 나타나기 전에 실행해야 하는 작업들을 여기서 할 수 있습니다.
- `ViewDidAppear` : 뷰가 생성되고 난 뒤에 실행 됩니다. 데이터를 받아서 화면에 뿌려주거나 애니메이션 등의 작업을 하는 로직을 위치시킬 수 있습니다. ViewWillAppear 에서 로직을 넣었다가 뷰에 반영이 안되는 경우가 있기 때문입니다.
- `ViewWillDisappear` : 뷰가 사라지기 직전에 실행 됩니다.
- `ViewDidDisappear` : 뷰가 사라지고 난 뒤에 실행 됩니다.

순환적으로 발생하기 때문에 화면 전환에 따라 발생해야 하는 로직을 적절한 곳에서 실행시켜야 합니다.