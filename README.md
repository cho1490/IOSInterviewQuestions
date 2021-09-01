## IOS
#### **Frame과 Bounds 의 차이점을 설명하시오.**   
    CGPoint: 2차원 좌표계의 점을 표현하는 구조체  
    CGSize: 너비와 높이값을 가지는 구조체   
    CGRect: 사각형의 위치와 크기를 포함하는 구조체 - CGPoint CGSize맴버로 가지고 있다.   

    공통점   
        Frame, Bounds 둘다 UIView의 instance property   
        CGRect 타입 - origin과 size를 가진다   
        open var frame: CGRect   
        open var bounds: CGRect

    차이점
        Frame: SuperView의 좌표시스템 안에서 View의 위치와 크기를 나타낸다.     
        Bounds: 자신만의 좌표시스템에서 View의 위치와 크기를 나타낸다.   

    사용
        Frame : UIView의 위치 및 크기를 설정할 때 사용한다.   
        Boudns : 1. View 내부에 그름을 그릴 때(drawRect) 사용한다. 2. ScrollView에서 스크롤을 할 때 사용된다. ( ContentOffset )   
        (https://zeddios.tistory.com/203)    
      
    회전을 하면 Frame의 origin, size는 변하지만 Bounds의 origin, size는 안변함   
    
#### **실제 디바이스가 없을 경우 개발 환경에서 사용할 수 없는 것**   
    카메라 활용
    gps
    자이로 센서
    블루투스
    faceup, facedown 같은 상태 확인
    모션 인식(가속계, 자이로스코프)
    오디오 및 비디오 입력(카메라, 마이크)
    근접 센서
    기압계
    주변 조도 센서 
    
* **앱의 콘텐츠나 데이터 자체를 저장/보관하는 특별한 객체를 무엇이라고 하는가?**   
* **앱 화면의 콘텐츠를 표시하는 로직과 관리를 담당하는 객체를 무엇이라고 하는가?**   
* **App thinning에 대해서 설명하시오.**   
* **앱이 시작할 때 main.c 에 있는 UIApplicationMain 함수에 의해서 생성되는 객체는 무엇인가?**   
* **@Main에 대해서 설명하시오.**   
* **앱이 foreground에 있을 때와 background에 있을 때 어떤 제약사항이 있나요?**   
* **상태 변화에 따라 다른 동작을 처리하기 위한 앱델리게이트 메서드들을 설명하시오.**   
* **앱이 In-Active 상태가 되는 시나리오를 설명하시오.**   
* **scene delegate에 대해 설명하시오.**   
* **UIApplication 객체의 컨트롤러 역할은 어디에 구현해야 하는가?**   
* **App의 Not running, Inactive, Active, Background, Suspended에 대해 설명하시오.**   
* NSOperationQueue 와 GCD Queue 의 차이점을 설명하시오.   
* GCD API 동작 방식과 필요성에 대해 설명하시오.   
* Global DispatchQueue 의 Qos 에는 어떤 종류가 있는지, 각각 어떤 의미인지 설명하시오.   
* iOS 앱을 만들고, User Interface를 구성하는 데 필수적인 프레임워크 이름은 무엇인가?   
* Foundation Kit은 무엇이고 포함되어 있는 클래스들은 어떤 것이 있는지 설명하시오.   
* Delegate란 무언인가 설명하고, retain 되는지 안되는지 그 이유를 함께 설명하시오.   
* NotificationCenter 동작 방식과 활용 방안에 대해 설명하시오.   
* UIKit 클래스들을 다룰 때 꼭 처리해야하는 애플리케이션 쓰레드 이름은 무엇인가?   
* App Bundle의 구조와 역할에 대해 설명하시오.   
* 모든 View Controller 객체의 상위 클래스는 무엇이고 그 역할은 무엇인가?   
* 자신만의 Custom View를 만들려면 어떻게 해야하는지 설명하시오.   
* View 객체에 대해 설명하시오.   
* UIView 에서 Layer 객체는 무엇이고 어떤 역할을 담당하는지 설명하시오.   
* UIWindow 객체의 역할은 무엇인가?   
* UINavigationController 의 역할이 무엇인지 설명하시오.   
#### * **TableView를 동작 방식과 화면에 Cell을 출력하기 위해 최소한 구현해야 하는 DataSource 메서드를 설명하시오.**   
    TableView가 화면에 나타나기 전에 데이터 소스 객체에게 테이블의 보이는 부분이나 그 근처에 있는 행에 대한 셀을 제공하도록 요청한다.   
    
    tableView(_:cellForRowAt:)는 다음과 같은 패턴으로 구현된다.   
    1. 테이블 뷰의 dequeueReusableCell(withIdentifier:for:) 메서드를 호출해서 셀 객체를 검색한다.   
    2. 사용자 지정 데이터로 셀을 구성한다.   
    3. 셀을 테이블뷰로 반환한다.   
    테이블 뷰는 테이블의 각 행에 대해 셀을 만들지 않는다. 대신 테이블뷰는 셀을 느리게 관리하여 테이블의 보이는 부분에 있거나 근처에 있는 셀만 요청한다.   
    셀을 느리게 생성하면 테이블에서 사용하는 메모리 양이 줄어든다.
    
    최소한 구현해야 하는 DataSource 메서드   
    행, 섹션의 개수를 제공하는 메서드

    ###### 행의 개수는 필수적으로 구현해야 함
        ```swift
        func numberOfSections(in tableView: UITableView) -> Int  // Optional 
        func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int
        ```
    ###### 셀 모양을 정의하는 메서드
        ```swift
        func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell
        ```   
    
#### * **하나의 View Controller 코드에서 여러 TableView Controller 역할을 해야 할 경우 어떻게 구분해서 구현해야 하는지 설명하시오.**   
    UItableViewDelegate및 UItableViewDatasource를 채택하고 필수 메서드에서 조건문을 사용하여 여러 TableView중 원하는 TableView를 선택한다.
    
* **setNeedsLayout와 setNeedsDisplay의 차이에 대해 설명하시오.**   
* **NSCache와 딕셔너리로 캐시를 구성했을때의 차이를 설명하시오.**   
* **URLSession에 대해서 설명하시오.**   
* **prepareForReuse에 대해서 설명하시오.**   
* **다크모드를 지원하는 방법에 대해 설명하시오.**   


## Autolayout
* 오토레이아웃을 코드로 작성하는 방법은 무엇인가? (3가지)   
* hugging, resistance에 대해서 설명하시오.   
* Intrinsic Size에 대해서 설명하시오.   
* 스토리보드를 이용했을때의 장단점을 설명하시오.   
* Safearea에 대해서 설명하시오.   
* Left Constraint 와 Leading Constraint 의 차이점을 설명하시오.   


## Swift
* struct와 class와 enum의 차이를 설명하시오.   
* class의 성능을 향상 시킬수 있는 방법들을 나열해보시오.   
* Convinience init에 대해 설명하시오.   
* Anyobject에 대해 설명하시오.   
* Optional 이란 무엇인지 설명하시오.   
* Struct 가 무엇이고 어떻게 사용하는지 설명하시오.   
* Subscripts에 대해 설명하시오.   
* instance 메서드와 class 메서드의 차이점을 설명하시오.   
* Delegate 패턴을 활용하는 경우를 예를 들어 설명하시오.   
* Singleton 패턴을 활용하는 경우를 예를 들어 설명하시오.   
* KVO 동작 방식에 대해 설명하시오.   
* Delegates와 Notification 방식의 차이점에 대해 설명하시오.   
* 멀티 쓰레드로 동작하는 앱을 작성하고 싶을 때 고려할 수 있는 방식들을 설명하시오.   
* MVC 구조에 대해 블록 그림을 그리고, 각 역할과 흐름을 설명하시오.   
* 프로토콜이란 무엇인지 설명하시오.   
* Hashable이 무엇이고, Equatable을 왜 상속해야 하는지 설명하시오.   
* mutating 키워드에 대해 설명하시오.   
* 탈출 클로저에 대하여 설명하시오.   
* Extension에 대해 설명하시오.   
* 접근 제어자의 종류엔 어떤게 있는지 설명하시오.   
* defer란 무엇인지 설명하시오.   
* defer가 호출되는 순서는 어떻게 되고, defer가 호출되지 않는 경우를 설명하시오.   
* property wrapper에 대해서 설명하시오.   
* Generic에 대해 설명하시오.   
* Result타입에 대해 설명하시오.   
* Codable에 대하여 설명하시오.   


## ARC
* ARC란 무엇인지 설명하시오.   
* Retain Count 방식에 대해 설명하시오.   
* Strong 과 Weak 참조 방식에 대해 설명하시오.   
* 순환 참조에 대하여 설명하시오.   
* 강한 순환 참조 (Strong Reference Cycle) 는 어떤 경우에 발생하는지 설명하시오.   


## Functional Programming
* 함수형 프로그래밍이 무엇인지 설명하시오.   
* 고차 함수가 무엇인지 설명하시오.   
* Swift Standard Library의 map, filter, reduce, compactMap, flatMap에 대하여 설명하시오.   


## Architecture
* MVVM, Ribs, VIP 등 자신이 알고있는 아키텍쳐를 설명하시오.   
* 의존성 주입에 대하여 설명하시오.   


## Rx
* Reactive Programming이 무엇인지 설명하시오.   
* RxSwift에서 Hot Observable과 Cold Observable의 차이를 설명하시오.   
* Subject와 drive의 차이를 설명하시오.   
