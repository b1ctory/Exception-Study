####  NSOperationQueue 와 GCD Queue 의 차이점을 설명하시오.

쉽고 편한 멀티 스레딩 처리를 위해 애플은 두가지의 API를 제공하고 있다.

GCD(Grand Central Dispatch)라는 C기반의 **저수준 API**와 NSOperation이라는 Obj-C 기반으로 만들어진 **고수준 API**가 있다. NSOperation은 GCD보다 **약간의 오버헤드가 더 발생되고 느리지만** **GCD에서는 직접 처리해야 하는 작업들을 지원** 하고 있기 때문에 (KVO관찰, 작업취소 등등) 그정도는 감수하고 사용할만하다.

#### GCD

GCD는 백그라운드에서 스레드를 관리하면서 동시적으로 작업을 실행시키는 저수준 API를 제공하는 라이브러리이다.

- Dispatch Queues: 디스패치 큐는 FIFO 순서로 작업을 실행시키는 역할을 담당
  - DispatchQueue는 2가지로 종류로 나눌수 있다.
    1. **Serial Dispatch Queue**: 등록된 작업을 한번에 하나씩 차례대로 처리 한다. 처리중인 작업이 완료되면 다음 작업을 처리!
    2. **Concurrent Dispatch Queue**: Concurrent Queue는 등록된 작업을 한번에 하나씩 처리 하지 않고 여러 작업들을 동시에 처리
- Serial Dispatch Queue: 시리얼 디스패치 큐는 한번에 한 작업만 실행
- Concurrent Dispatch Queue: 컨커런트 디스패치 큐는 시작한 작업이 끝나는것을 기다리지 않고 가능한 많은 작업을 실행
- Main Dispatch Queue: 앱의 메인 스레드에서 작업을 실행할 수있는 전역에서 사용가능한 시리얼 큐

앱 실행시 시스템에서 기본적으로 2개의 Queue를 만들어 준다.

1. **Main Queue**: 메인 스레드(UI 스레드)에서 사용 되는 Serial Queue로 **모든 UI 처리는 메인 스레드에서 처리**를 해야한다.
2. **Global Queue**: 편의상 사용할수 있게 만들어 놓은 Concurrent Queue로 Global Queue는 처리 우선 순위를 위한 qos(Quality of service) 파라메터를 제공하여 병렬적으로 동시에 처리를 하기때문에 **작업 완료의 순서는 정할수 없지만 우선적으로 일을 처리**하게 할수 있다.

#### Sync / Async

- Dispatch Queue는 sync와 async라는 메소드를 가지고 있는데, sync는 동기 처리 메소드로 해당 작업을 처리하는 동안 다음으로 진행되지 않고 계속 머물러 있다.
- 반면 **async는 비동기 처리 메소드**로 sync와는 다르게 처리를 하라고 지시후 다음으로 넘어가 버린다.

- 직렬과 병렬은 한번에 하나만 처리하느냐 동시에 여러개 처리하느냐고 동기와 비동기는 처리가 끝날때까지 기다리느냐 지시만하고 다른 처리를 하느냐를 의미한다!

#### NSOperation

- NSOperation: GCD와 비교했을땐 추가적인 오버해드가 있으나, 다양한 작업들 가운데 의존성을 추가할 수 있고, 재사용, 취소, 중지시킬 수 있다.
- NSOperationQueue: NSOperation들을 만들어서 병렬로 실행시키는 스레드 풀을 제공한다. Operation queue가 GCD의 일부는 아니다.
- NSBlockOperation: 하나 혹은 그 이상의 클로저에서 NSOperation을 생성할 수 있게 해준다. NSBlockOperation들은 동시적으로 실행하는 다중 블락을 가질 수 있다.



reference : https://www.zehye.kr/ios/2020/04/23/11iOS_GCD_NSOperation_queue/