### Escaping Closure의 개념

<!-- 아직 잘 이해가 안됨. -->

메서드 파라미터로 전달받은 closure 를 메서드의 라이프사이클 내에서 실행하여 끝내지 않고, 메서드 scope 의 외부에 전달하려 할 때는 해당 closure 를 escaping 해야한다. 해당 메서드의 호출이 끝난 이후에도 closure 는 메모리 어딘가에 저장되어야 하며, 이는 closure 안에서 사용된 outer object (self 와 같은) 에 weak 와 같은 레퍼런스타입을 사용해야할 수 있음을 주의하도록 한다.

escaping 이 명시되어있지 않으면 기본적으로 non-escaping 이며, 이는 메서드의 실행이 끝나기 전에 closure 의 사용이 모두 완료됨을 보장하며, 따라서 closure 내에서 weak 을 굳이 사용하지 않아도 안전할 수 있음을 의미하기도 한다.

