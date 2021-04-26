#### iOS 아키텍처 패턴

###### MVC

먼저 기존 MVC의 개념을 살펴보면 아래와 같다. 

**Model** : 애플리케이션에서 사용할 데이터 관리

**View** : 유저 인터페이스 표현 및 관리

**Controller** : View와 Model의 다리 역할을 해 View의 입력을 Model에 반영하고 Model의 변화를 View에 갱신

![image-20210426191645462](http://labs.brandi.co.kr///assets/2018/20180227/01.png)

하지만, 애플의 MVC 패턴은 기존 MVC 패턴은 기존 MVC 패턴과 다르다. View와 Controller가 강하게 연결되어있어서 View Controller가 거의 모든 일을 한다.

![](http://labs.brandi.co.kr///assets/2018/20180227/02.png)



###### MVVM

![](http://labs.brandi.co.kr///assets/2018/20180227/03.png)

Model, View, ViewModel이다. Controller를 빼고 View Model을 추가한 패턴이다. 

여기서 View Controller가 View가 되고, ViewModel이 중간 역할을 한다. View와 ViewModel 사이에 Binding (연결고리) 이 있다. 

ViewModel은 Model에 변화를 주고, ViewModel을 업데이트하는데 이 바인딩으로 인해 View도 업데이트된다. ViewModel은 View에 대해 아무것도 모르기 때문에 테스트가 쉽고 바인딩으로 인해 코드 양을 줄일 수 있다. 



###### VIPER

![](http://labs.brandi.co.kr///assets/2018/20180227/05.png)

| 항목              | 내용                                                         |
| :---------------- | :----------------------------------------------------------- |
| View              | Presenter의 요청대로 디스플레이하고, 사용자 입력을 Presenter로 보내는 작업을 합니다. |
| Interactor        | Use case에 따라서 Entity 모델 객체를 조작하는 로직을 담고 있습니다. |
| Presenter         | Interactor로부터 데이터를 가져오고, View로 보내기 위해 데이터를 준비하여 “언제” View에 보여줄지를 결정합니다. |
| Entity            | 모델 객체. Dumb Model.                                       |
| Router(Wireframe) | 화면 전환(navigation information)을 담당하며, Presenter가 “언제” 화면 전환해야하는지를 안다면, Wireframe은 화면 전환을 “어떻게” 하는지를 알고 있습니다. |





참고 블로그 출처 : http://labs.brandi.co.kr/2018/02/21/kimjh.html