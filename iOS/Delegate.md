### Delegate 

**Protocol** : 서로간에 지켜야할 '규약' , Delegate는 프로토콜로 구현된다.

**Delegate** : '대리자'

**Delegate Pattern** : 객체 지향 프로그래밍에서 하나의 객체가 모든 일을 처리하는 것이 아니라 처리해야 할 일 중 일부를 다른 객체에 넘기는 것을 뜻한다. 프로토콜을 채택하고, 위임자가 누구인지 알려준다. (ex ) `textField.delegate = self` ) 그리고 프로토콜을 준수하기 위해 필수 구현 함수들을 구현해준다. 

`프로토콜을 채택할 때에는 반드시 같이 선언해주어야 하는 함수들이 있는지 확인하는 습관을 들이자!`

Reference : https://zeddios.tistory.com/8 (Zedd님 블로그)

