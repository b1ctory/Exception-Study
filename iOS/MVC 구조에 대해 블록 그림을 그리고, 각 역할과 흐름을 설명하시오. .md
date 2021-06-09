#### MVC 구조에 대해 블록 그림을 그리고, 각 역할과 흐름을 설명하시오.

![img](https://mblogthumb-phinf.pstatic.net/MjAxNzAzMjVfMjIg/MDAxNDkwNDM4ODMzNjI2.nzDNB5K0LuyP4joE2C4rIbL5Ue2F3at7wiI6ZpuTJN0g.WZ6V-WHZygLYW2WSdzcs7uAiAWgAJe3_H0XdkYKkutkg.PNG.jhc9639/1262.png?type=w800)

[image 출처] : 오픈듀토리얼스

Model은 데이터의 틀이라고 생각할 수 있다. 

View는 화면에 보여지는 것이다. (사용자에게 보여지는 화면)

Controller는 Model과 View의 징검다리 역할로, View의 입력을 처리하여 Model을 업데이트 시키고, Update 된 Model의 정보를 View에 보여주는 역할을 담당한다. 

iOS 의 경우에는 View 와 Controller 가 강하게 연결된 View Controller가 있는데, 이 ViewController가 거의 모든 역할을 담당한다. 

