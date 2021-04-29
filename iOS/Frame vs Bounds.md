### Frame vs Bounds

- `Frame` : 부모뷰의 상대적인 위치(x, y) 및 크기 (너비, 높이)로 표현되는 사각형
- `Bounds` : 자체 좌표계 (0,0)를 기준으로 위치 (x, y) 및 크기 (너비, 높이)로 표현되는 사각형



### 언제 Frame과 Bounds를 써야 하는가?

- Frame : UIView의 위치나 크기를 설정하는 경우.
- Bounds :
  - View내부에 그림을 그릴때 (drawRect).
  - transfomation 후, View의 크기를 알고싶을 때.
  - 하위View를 정렬하는 것과 같이 **내부적으로 변경하는 경우.**
  - Bounds는 View "크기"만 변경할 수 있으며 위치정보가 없다.