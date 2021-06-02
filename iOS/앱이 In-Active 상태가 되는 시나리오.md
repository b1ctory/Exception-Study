#### 앱이 In-Active 상태가 되는 시나리오

1. 앱이 처음 실행될 때 Not Running 상태에서 **Inactive를 거쳐** Active 상태로 전환된다. 
2. 앱이 실행 후 홈 화면으로 나가면 Active에서 **Inactive를 거쳐** Background 상태로 전환된다. 
3. 앱이 백그라운드에 있다가 Suspended 상태로 전이되는데, 이 때 Active -> **In-Active** -> Background -> Suspend 순으로 상태가 전환된다.



- In-Active 상태는 앱이 실행 중이지만 이벤트를 받지 않는 상태
- 다른 상태로 넘어가기 전에 앱은 반드시 이 상태를 거치게 된다.
- 전화나 메세지 같은 interrupt 발생 시에도 In-Active 상태가 된다. 
- 미리 알람 같은 특정 알림창이 화면을 덮어서 실질적으로 이벤트를 받지 못하는 상태 등이 해당된다. 

