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
    
#### **앱의 콘텐츠나 데이터 자체를 저장/보관하는 특별한 객체를 무엇이라고 하는가?**   
#### **앱 화면의 콘텐츠를 표시하는 로직과 관리를 담당하는 객체를 무엇이라고 하는가?**   
#### **App thinning에 대해서 설명하시오.**   
#### **앱이 시작할 때 main.c 에 있는 UIApplicationMain 함수에 의해서 생성되는 객체는 무엇인가?**   
#### **@Main에 대해서 설명하시오.**   

#### **App의 Not running, Inactive, Active, Background, Suspended에 대해 설명하시오.**    
    Not running : 앱이 아예 실행되지 않았거나 시스템에 의해 종료되었을 때의 상황입니다.
    Inactive : 앱이 foreground 상태이기는 하나 이벤트를 받지 못한 상태입니다.
    Active : 앱이 foreground에서 실행 중이며 이벤트를 받았을 때의 상황입니다.
    Background : 앱이 background에 있으며 코드를 실행하고 있는 상태입니다.
    Suspended : 앱이 background이며 앱이 메모리에 남아 있긴 하나 코드를 실행하고 있지 않은 상태입니다.
   
#### **앱이 foreground에 있을 때와 background에 있을 때 어떤 제약사항이 있나요?**   
    foreground 
        메모리 및 기타 시스템 리소스에 높은 우선순위를 가지며 시스템은 이러한 리소스를 사용할 수 있도록 필요에 따라 background 앱을 종료합니다.
    background 
        가능한 적은 메모리공간을 사용해야한다.
        상태란 앱이 홈화면에 들어가서 사용자한테 보이지 않는 상태를 의미합니다. 
        하지만앱이 background 상태가 되어도 계속 실행해야 될 때가 존재합니다. 
        ex) 음악 어플을 사용해 노래를 들을 때 다른 어플을 사용한다고 노래가 멈추지 않는다.
     

#### **상태 변화에 따라 다른 동작을 처리하기 위한 앱델리게이트 메서드들을 설명하시오.**   
#### **앱이 In-Active 상태가 되는 시나리오를 설명하시오.**   
#### **scene delegate에 대해 설명하시오.**   
#### **UIApplication 객체의 컨트롤러 역할은 어디에 구현해야 하는가?**   
#### **NSOperationQueue 와 GCD Queue 의 차이점을 설명하시오.**   
#### **GCD API 동작 방식과 필요성에 대해 설명하시오.**   
#### **Global DispatchQueue 의 Qos 에는 어떤 종류가 있는지, 각각 어떤 의미인지 설명하시오.**   
#### **iOS 앱을 만들고, User Interface를 구성하는 데 필수적인 프레임워크 이름은 무엇인가?**   
    UIKit
    사용자의 인터페이스를 관리하고, 이벤트를 처리하는게 주 목적이다. Cocoa Touch 계층에 속해있음
    
#### **Foundation Kit은 무엇이고 포함되어 있는 클래스들은 어떤 것이 있는지 설명하시오.**   
    Foundation
    필수 데이터 타입, 컬렉션, 운영체제 서비스를 이용하여 앱의 기본계층을 정희한다.
    Core Services 계층에 속해있음.

#### **Delegate란 무언인가 설명하고, retain 되는지 안되는지 그 이유를 함께 설명하시오.**   
    대리자
    객체 지향 프로그래밍에서 하나의 객체가 모든 일을 처리하는 것이 아니라 처리해야 할 일 중 일부를 다른 객체에게 넘기는 것을 의미한다.
    처리하라고 시키는 객체와 대신처리해줄 객체가 존재한다.

    retain 되는가?
    객체 간의 작업이기 때문에 참조 값을 사용한다. 그래서 retain 현상이 일어난다.
    
#### **NotificationCenter 동작 방식과 활용 방안에 대해 설명하시오.**   
    Notification Center 동작방식
    하나의 앱에는 알림센터가 하나씩 존재
    어느화면에서 이벤트가 발생했다는 것을 Notification Center로 송신
    Notification Center에서 해당 발생된 이벤트를 모든 화면에 broadcast방식으로 전송
    해당 이벤트를 구독하는 Observer가 있다면 해당 화면에서 이벤트에 대한 처리

    활용방안
    화면간 연결관계가 없는경우
    화면의 Depth가 깊을 때
    같은 이벤트로 다수의 옵저버가 필요한경우
    
#### **UIKit 클래스들을 다룰 때 꼭 처리해야하는 애플리케이션 쓰레드 이름은 무엇인가?**   
    Main Thread
    Cocoa Touch 앱에서는 UIApplication의 인스턴스가 main thread에 attach하기 때문에, run loop를 포함하여, main event loop를 설정하고 event처리를 시작합니다.
    따라서, main thread에서 모든 UI event를 수신하게 되어있습니다. 

#### **App Bundle의 구조와 역할에 대해 설명하시오.**   
#### **모든 View Controller 객체의 상위 클래스는 무엇이고 그 역할은 무엇인가?**   
#### **자신만의 Custom View를 만들려면 어떻게 해야하는지 설명하시오.**   
#### **View 객체에 대해 설명하시오.**   
#### **UIView 에서 Layer 객체는 무엇이고 어떤 역할을 담당하는지 설명하시오.**   
#### **UIWindow 객체의 역할은 무엇인가?**   
#### **UINavigationController 의 역할이 무엇인지 설명하시오.**   
#### **TableView의 동작 방식과 화면에 Cell을 출력하기 위해 최소한 구현해야 하는 DataSource 메서드를 설명하시오.**   
    동작 방식   
    테이블 뷰는 데이터 기반으로 작동한다.
    개발자에 의해 정의된 데이터소스 객체로 부터 데이터를 받아오고
    그 데이터소스 객체는 앱의 데이터를 관리하고, 테이블 뷰의 셀들을 정의하는 역할을 한다.
    구현은 일반적으로 테이블 뷰가 들어가는 상위 객체에 TableView를 추가하고,
    해당 객체가 UITableViewDataSource 프로토콜을 채택하게 한다.
    
    그 후, numberOfRowInSection과 cellForRowAt 메서드를 정의하면
    테이블 뷰와 각 셀에 들어간 데이터가 열로 출력된다.
    테이블 뷰가 내려가면서 새로운 셀을 반환하는 것은 cellForRowAt 메서드에서
    일반적으로 반환할 셀을 정의할 때, TableView의 dequeReusableCell 메서드를 사용하는데,
    셀이 화면 밖으로 밀려나면 reusableQueue에 들어가고,
    다시 나오는 셀은 reusableQueue에서 나오게 되면서 모든 셀을 만드는 것이 아닌 셀을 재사용한다.
    (모든 셀을 만드는 것은 앱 성능 측면에서 비효율적임) 
   
    UITabelViewDelegate (이 중 필수로 구현하는 메서드는 없습니다.)   
    
    // 지정된 행이 선택 되었다는걸 알리는 메서드
    @available(iOS 2.0, *)
    optional func tableview(UITableView, didSelectRowAt: IndexPath)

    // 지정된 행이 선택해체 되었다는걸 알리는 메서드
    @available(iOS 2.0, *)
    optional func tableView(UITableView, didDeselectRowAt: IndexPath)

    // 특정 위치 행의 높이를 묻는 메서드
    @available(iOS 2.0, *)
    optional func tableView(UITableView, heightForRowAt: IndexPath)
    
    UITableViewDataSource (2가지 모두 필수로 구현하는 메서드)   
    
    // 섹션에 표시할 행의 개수
    @available(ios 2.0, *)
    func tableview(_ tableView: UITableView, numberOfRowInSection section : Int) -> Int

    @available(ios 2.0, *)
    // 특정 위치에 표시할 셀을 요청하는 메서드
    func tableview(_ tableView: UITableView, cellForRowAt indexPath : IndexPath) -> UITableViewCell
    
#### **하나의 View Controller 코드에서 여러 TableView Controller 역할을 해야 할 경우 어떻게 구분해서 구현해야 하는지 설명하시오.**   
    UItableViewDelegate및 UItableViewDatasource를 채택하고 필수 메서드에서 조건문을 통해 TableView중 원하는 TableView를 선택한다.   
    
#### **setNeedsLayout와 setNeedsDisplay의 차이에 대해 설명하시오.**   
#### **NSCache와 딕셔너리로 캐시를 구성했을때의 차이를 설명하시오.**   
#### **URLSession에 대해서 설명하시오.**   
#### **prepareForReuse에 대해서 설명하시오.**   
#### **다크모드를 지원하는 방법에 대해 설명하시오.**   

## Autolayout
#### **오토레이아웃을 코드로 작성하는 방법은 무엇인가? (3가지)**   
    Anchor
    NSLayoutConstraint
    Visual Format Language
#### **hugging, resistance에 대해서 설명하시오.**   
#### **Intrinsic Size에 대해서 설명하시오.**   
    intrinsicContentSize란?
    View 자체의 본질의 크기
    UILabel, UIButton, UISwitch,TextField 등 이런 view 들은 제약 없이도 자체적인 width와 height를 가질 수 있다.
#### **스토리보드를 이용했을때의 장단점을 설명하시오.**   
    장점
        1. 제작 속도, 난이도: 뷰를 금방금방 쉽게 만들 수 있음
        2. 시각화: 앱의 구성이나 흐름을 한눈에 볼 수 있음

    단점
        1. 생산성: 앱이 커질수록 느려짐. storyboard를 분리해서 해결할 수 있다.
        2. 협업이 어려움: Merge Conflict 문제 (xml 포멧)
        3. 재사용성: 코드와 달리 재사용이 어렵다
        4. 스토리보드로 불가능한 작업이 있음
        
#### **Safearea에 대해서 설명하시오.**   
    Top / Bottom Layout Guide
    Safe Area 등장전에는 top / bottom layout guide 가 존재했다.
    상태바, 내비게이션 바, 탭바등에 의해서 가려지는 부분을 피하기 위해서..

    iOS 11이 등장하면서 노치가 생겼고, Landscape 모드일때 Leading / Trailing 마진도 필요하게 되었음.
    기존에 쓰이던 Top / Bottom Layout Guide가 Deprecate가 됬고, Top, bottom, Leading, Trailing 시스템 마진을 모두 가지는 Safe Area라는 개념이 등장하게 되었다.

#### **Left Constraint 와 Leading Constraint 의 차이점을 설명하시오.**   
    Left는 왼쪽
    Leading은 글자가 시작하는 방향

    다국어지원해야할때 유용
    굳이 left를 써야할 필요는 없을듯

## Swift
#### **struct와 class와 enum의 차이를 설명하시오.**   
    class
        OOP의 class를 의미한다.

        heap 영역에 저장되어 상대적으로 느림   
        runtime에 직접 할당하며, reference counting을 통해서 해제 한다.   
        deinitializer가 존재한다.   
        단일 상속 가능   
        매서드, 프로퍼티 를 가진다.   
        참조타입 (reference type) 이다.   
        iOS framework의 대부분이 클래스로 구성되어 있다.   
        
    struct
        stack 영역에 저장됨 (일정 크기 이상이면 구조체지만 heap에 저장된다.)   
        속도가 빠르고, multi-thread 환경에서 안전함   
        complie time에 메모리 할당/해제가 결정된다.   
        상속이 불가능.   
        매서드, 프로퍼티 를 가진다.   
        값 타입 (value type) 이다.   
        AnyObject로 타입캐스팅이 불가능 하다.   
        swift의 대부분의 뼈대는 구조체로 구성되어 있다.   
            
    구조체와 클래스의 공통점   
        프로퍼티와 매서드를 사용해서 구조화된 데이터와 기능을 가진다.   
        새로운 사용자 지정 타입을 만들어준다.       
        extension이 가능하다.   
        protocol을 사용할 수 있다.   
        initializer의 정의가 가능하다.   
            
    enum
        연관된 값들의 집합을 공통된 타입으로 정의   
        RawValue 를 통해 원시값을 지정할 수 있음(String, Characer, Number)   
        Associated Value 를 통해 연관값을 지정할 수도 있음   
        protocol 사용 가능   
        상속이 불가능하다.   
        (인스턴스/타입) 매서드, (인스턴스/타입) 연산 프로퍼티 를 가진다.   
        
#### **class의 성능을 향상 시킬수 있는 방법들을 나열해보시오.**   
    기능에 문제가 없다면 struct로 바꾸기 (heap영역이 아닌 stack영역을 사용)   
    오버라이딩 할 필요가 없는 클래스, 매서드, 프로퍼티에는 final 접근제어자를 사용 (dynamic dispatch -> static dispatch)   
    파일 외부에서 class에 접근할 필요가 없다면 private or fileprivate 접근 제어자를 사용   
    
#### **Convinience init에 대해 설명하시오.**   
    우선 initializer는 왜 필요할까?   
        class나 struct의 모든 저장 프로퍼티 들은 생성시점에 초기화 되어야 하기 때문이다.   

    designated init(지정 이니셜라이저): 모든 프로퍼티를 초기화 해야함   
    convenience init(편의 이니셜라이저): 모든 프로퍼티를 초기화 할 필요는 없지만, 무조건 다른 이니셜라이저를 호출해야 하고,    
    최종적으로는 지정 이니셜라이저를 호출해야만 한다.   
    required init(재정의 이니셜라이저): class를 상속받았을때, 필수적으로 overriding하도록 강제하는 이니셜라이저   

#### **Anyobject에 대해 설명하시오.**   
    Any: 함수타입을 포함하여 모든 타입의 인스턴스를 나타낼 수 있음   
    AnyObject: 모든 클래스 타입의 인스턴스를 나타낼 수 있음. 모든 클래스가 준수하는 protocol.   

    가급적 쓰지 않는것이 좋다.   
    이유: swift는 타입에 민감한 언어이고, Any, AnyObejct 타입은 런타임 시점에 타입이 결정되며, 다운캐스팅이 필요함   

#### **Optional 이란 무엇인지 설명하시오.**   
    optional은 값이 있을수도 있고 없을수도 있는 상태.    
    optional 값을 실제로 사용하려면 다음과 같은 과정이 필요하다.   

    if let or guard 를 통한 optional Binding
    Forced Unwrapping(강제추출) !
    nil 병합 연산자 ??
    
#### **Struct 가 무엇이고 어떻게 사용하는지 설명하시오.**   
    언제 구조체를 사용해야 하는가? (by Apple guideline)

    연관된 간단한 값의 집합을 캡슐화 하는 것만이 목적일 때
    캡슐화된 값이 참조되는 것보다 복사되는 것이 합당할때
    구조체에 저장된 프로퍼티가 값 타입이며 참조되는 것보다 복사되는 것이 합당할 때
    다른 타입으로부터 상속받거나 자신이 상속될 필요가 없을 때
    
#### **Subscripts에 대해 설명하시오.**   
#### **instance 메서드와 class 메서드의 차이점을 설명하시오.**   
#### **Delegate 패턴을 활용하는 경우를 예를 들어 설명하시오.**   
    대표적으로 TableViewDelegate, CollectionViewDelegate가 있다.
    뷰컨트롤러에서 Delegate 함수를 정의하고
    뷰의 동작이 일어나면 해당 Delegate 함수를 호출하고
    뷰컨트롤러가 대신 처리해준다.

#### **Singleton 패턴을 활용하는 경우를 예를 들어 설명하시오.**   
    Singleton 패턴이란?     
        특정 용도로 객체를 하나만 생성하여 공용으로 사용하고 싶을 때 사용하는 디자인 패턴
        (생성자가 여러 차례 호출되더라도 실제로 생성되는 객체는 하나이다. 최초에 생성된 객체)
    장점   
        최초 한번만 메모리 할당을 하기때문에 메모리 낭비 방지
        객체들간에 하나의 데이터를 공유할 수 있음
        
#### **KVO 동작 방식에 대해 설명하시오.**   
#### **Delegates와 Notification 방식의 차이점에 대해 설명하시오.**   
    Delegate 
    장점
        엄격한 Syntax 로 인해 프로토콜에 필요한 메소드들이 명확하게 명시되어 있습니다.
        프로코콜에 정의되어 있는 메소드 들을 구현하지 않으면 컴파일 시 경고 혹은 에러 가 발생합니다.
        커뮤니케이션 과정을 유지하고 모니터링하는 제 3의 객체(NotificationCenter) 가 필요하지 않습니다.
    단점
        많은 줄의 코드 가 필요합니다.
        Delegate 설정에 nil이 들어가지 않게 주의해야 합니다. (crash 주된 원인)
        많은 객체들에게 이벤트를 알리는것이 어렵고 비효율적 입니다.
        
    Notification
    장점
        많은 줄의 코드 가 필요없이 쉽게 구현 가능합니다.
        다수의 객체 들에 동시에 이벤트를 전달할 수 있습니다.
        Notoification 과 관련된 정보를 Any? 타입의 object ,
        [AnyHashable: Any]? 타입의 userInfo 로 전달 할 수 있습니다.
    단점
        key 값으로 Notification 의 이름과 userInfo 를 서로 맞추기 때문에 컴파일 시 구독이 잘 되고 있는지 , 올바르게 userInfo 의 value 를 받아오는지 확인이 불가능합니다.
        Notification 의 post 이후 그에 대한 응답 정보를 받을 수 없습니다.
    
    Delegation 패턴 은 각각의 객체가 delegate 를 설정하여 이벤트에 대한 처리를 합니다.
    먼저, Notification , Delegation 패턴으로 많은 객체들 에 이벤트를 전달해야 하는 경우를 생각해 봅시다.
    Notification 의 경우, 특정 키 값 을 가진 notification 이 하나의 이벤트를 post 하게 되면 해당하는 키 값을 가진 notification 을 구독 하고 있는 모두에게 이벤트를 전달 하게 됩니다.
    Delegation 의 경우, 이벤트를 전달받아야 하는 각각의 객체들 에 delegate 를 설정 해줘야 합니다.
    명확한 답은 없지만, 많은 객체들 에 이벤트를 전달 해야 하는 경우, Notification 을 사용하고 그 외에는 코드의 흐름을 이해하기 쉽고 추적이 쉬운 Delegate 를 사용하는게 좋을 것 같습니다.
    
#### **멀티 스레드로 동작하는 앱을 작성하고 싶을 때 고려할 수 있는 방식들을 설명하시오.**   
    프로세스(Process) 란?
    프로세스(Process): 운영체제로부터 시스템 자원을 할당받는 작업의 단위. 
    독립된 메모리 영역(Code Data Stack Heap)을 할당받으며 프로세스끼지 서로의 변수 / 구조에 접근 불가능 (IPC 통신을 사용해야만 함. 파일이나 소켓)
    
    멀티 프로세스(Multi Process): 하나의 프로그램을 여러 개의 프로세스로 구성하여, 각 프로세스 마다 하나의 작업을 처리하도록 하는것
    장점
        독립된 구조이기 때문에 안정성이 높음
    단점
        Context Switching 의 CPU 부담이 크고 오버헤드가 발생한다.
        프로세스간 자원공유가 어렵다

    쓰레드(Thread) 란?
    쓰레드(thread): 한 프로세스 내에서 동작되는 여러 실행의 흐름. 
    Code Data Heap 영역은 공유하고 Stack(LIFO 자료구조여서 공유하기가 힘듬) 영역만 독립적으로 할당받는다. 
    결국 Heap 영역을 공유할 수 있음. 하지만 여전히 Stack 영역에 접근할 수는 없음.
    
    멀티 쓰레드(Multi Thread): 하나의 프로그램을 여러개의 쓰레드로 구성하여, 각 쓰레드마다 하나의 작업씩 처리하도록 하는것
    장점
        Code, Data, Heap 영역의 공유로 인해 Context Switching이 빠르다
        프로세스를 생성하여 자원을 할당하는 것이 아니기 때문에, 생성/종료 시간도 프로세스보다 빠르다
        통신방법이 간단함
    단점
        다루기가 어렵다. 자원공유가 되기때문에, 동기화 문제가 발생함
        독립적이지 않아서, 하나의 쓰레드에서 발생한 문제가 전체 쓰레드에 영향을 줄 수 있다.
        
    멀티 쓰레딩을 사용하는 이유
        시간이 오래 걸리는 작업 진행시 앱의 실행을 방해해서는 안되기 때문에
        메모리 공간과 시스템 자원을 절약
        
    iOS 에서 고려해야 할 점
        UI 업데이트에 관련된 작업들은 무조건 main thread에서 구현해야 한다.
        Thread - unsafe 한 변수는 서로 다른 스레드에서 동시에 접근하지 않게 해야함
        
    1) Mutable, Immutable
        Immutable 인스턴스는 Thread - safe 하다.
        Mutable 인스턴스는 Thread - unsafe 하다
        
    2) 프로퍼티 속성
        한 프로퍼티를 두개의 스레드가 참조하고 있는 상황에서 해당 프로퍼티의 접근자 매소드를 atomic으로 하지 않는다면 해당 프로퍼티 값에 대한 싱크가 맞지 않을 수 있다
        동시 접근 가능성이 없다면, nonatomic으로 사용해도 상관없음
        
    3) Synchronized
        semaphore를 이용해서 Lock을 걸 수 있음.

    4) GCD
        Swift 에서 스레드 작업은 Grand Central Dispatch API를 통해 처리된다.
        GCD는 클로저 블록 안에 있는 특정 작업을 큐에 올리고, 해당 큐를 특정 스레드에 실행하는 방식이다.
    
#### **MVC 구조에 대해 블록 그림을 그리고, 각 역할과 흐름을 설명하시오.**   

#### **프로토콜이란 무엇인지 설명하시오.**
    프로토콜(Protocol) : 특정 역할을 하기 위한 메서드, 프로퍼티, 기타 요구사항의 구조
    특징   
        구조체, 클래스, 열거형은 프로토콜을 채택할 수 있음
        프로토콜에서는 실제 기능은 구현하지 않는다
        하나의 타입으로써 동작 가능하다.
        
#### **Hashable이 무엇이고, Equatable을 왜 상속해야 하는지 설명하시오.**   

#### **mutating 키워드에 대해 설명하시오.**   
    구조체는 값 타입이다.
    값 타입의 속성은 인스턴스 메서드 내에서 수정할 수 없다.
    값 타입의 속성을 수정하기 위해서 mutating키워드를 사용 해줘야 한다.
    
    ex) 구조체로 구현한 stack의 push, pop은 mutating키워드를 사용한다.
    
#### **탈출 클로저에 대하여 설명하시오.**   

#### **Extension에 대해 설명하시오.**
    Extension : 구조체, 클래스, 열거형 타입에 새로운 기능을 추가하는 것을 말함
    추가할 수 있는 속성   
        연산속성
        이니셜라이저(default)
        매소드(인스턴스, 타입, mutating 모두 가능)
        서브스크립트
        중첩 타입   
        
    추가할 수 없는 속성
        저장속성: extension은 새 값을 저장하기 위한 추가 메모리를 관리할 수 없음
        이니셜라이저(designated)
        소멸자   
        기존기능 재정의 불가능   
        
    Extension vs 상속
        익스텐션 : 수평확장, 모든 타입에 사용가능, 재정의 불가능
        상속 : 수직확장, 클래스에만 사용가능, 재정의 가능   
        
#### **접근 제어자의 종류엔 어떤게 있는지 설명하시오.**   
    다섯가지 접근레벨   
        open : 모듈 외부에서도 접근 가능 - 개방 접근수준
        public : 모듈 외부에서도 접근 가능 - 공개 접근수준
    open과 public의 차이점   
        open : 오버라이딩, 서브클래싱 가능
        public : 모듈 내에서 오버라이딩, 서브클래싱 가능
        
        internal: 하나의 모듈 내부에서만 접근 가능 - 내부 접근수준
        File-private: 하나의 파일 내에서만 접근 가능 - 파일내부 접근수준
        private: 정의한 블록 내부에서만 접근 가능 - 비공개 접근수준

#### **defer란 무엇인지 설명하시오.**   
#### **defer가 호출되는 순서는 어떻게 되고, defer가 호출되지 않는 경우를 설명하시오.**   
#### **property wrapper에 대해서 설명하시오.**   
    @propertyWrapper: 반복되는 로직들을 프로퍼티 자체에 연결할수 있다.
    프로퍼티를 가질 수 있는 타입(class, struct, enum) 앞에 붙힐 수 있다.

#### **Generic에 대해 설명하시오.**   
#### **Result타입에 대해 설명하시오.**   
#### **Codable에 대하여 설명하시오.**   
    Codable은 Encodable과 Decodable이 합쳐진것
        Encodable : 자신을 외부표현으로 인코딩 할수있는 타입.
        Decodable : 자신을 외부표현으로부터 디코딩할수있는 타입.

#### **escaping Closure**
    Swift 3 부터는 기본적으로 함수의 인자로 들어온 클로저가 함수 밖에서 실행될수 없습니다.
    따라서 @escaping을 붙이면 함수밖에서 실행가능합니다.

## ARC
#### **ARC란 무엇인지 설명하시오.**   
    먼저 메모리 관리를 해야하는 이유

    앱의 성능 유지를 위해서 (Memory leak, dangling Pointer등의 문제)
    Objective-C에서는 MRC,Manual Reference Counting (ARC도 가능)를 사용. 개발자들이 직접 메모리를 관리했음.
    단점: 코드양이 많아지고 메모리 오류 가능성이 높아짐. 즉 프로그램 안정성이 낮아진다.

    Stack에 메모리에 저장된 데이터는 자동으로 제거되기 때문에 특별한 관리가 필요없다.
    그러나 Heap 메모리에 저장된 데이터는 메모리 관리가 필요함
    
    ARC(Auto Reference Counting)란?
    객체에 대한 참조 카운트를 관리하고 0이되면 자동으로 메모리에서 객체를 해제하는 방법을 의미한다. (컴파일러가 알아서 관리해줌)

    장점
        컴파일시 이미 인스턴스의 해제 시점이 정해져 있어서 인스턴스가 언제 메모리에서 해제될지 예측 가능
        메모리 관리를 위한 시스템 자원을 추가할 필요가 없음

    단점
        작동규칙을 모른채 사용하면, 영원히 메모리에서 해제되지 않는 인스턴스가 생길 수도 있음. (순환 참조 문제)
        참조방식에는 3가지가 있다.
        
    강한참조
    Strong  
        기본적으로 인스턴스와 소유자는 강한참조로 연결됨. 대상을 소유할 때마다 reference count가 1씩 증가하고, 포기하면 1씩 감소함. 순환참조 문제가 발생할 수 있다. (특히 delegate)
     
    약한참조
    Weak
        * 옵셔널 방식
        참조 카운트에 영향을 주지 않음
        소유자에 비해 짧은 생명주기를 가진 인스턴스를 참조할 때 주로 사용됨
    Unowned
        * 넌 옵셔널 방식
        해제된 인스턴스에 접근할 경우 런타임 에러가 발생한다.
        인스턴스의 생명주기가 소유자와 같거나 더 긴 경우에만 사용

    클로저의 경우 클로저 캡쳐 리스트를 통해서 해결할 수 있음
    
#### **Retain Count 방식에 대해 설명하시오.**   
    retain : retain count(= reference count) 증가를 통해 현재 Scope에서 객체가 유지되는것을 보장
    release : retain count(= reference count)를 감소시킴. retain 후에 필요 없을 때 release 함    

    Retain Count가 증가할때
        1. 인스턴스가 생성될때
        2. retain 매소드를 사용할때 (인스턴스의 주소값을 할당받은경우 직접 해주어야한다)

    Retain Count가 감소할때
        1. release 매소드를 사용할때

#### **Strong 과 Weak 참조 방식에 대해 설명하시오.**   
    Strong: 별도의 식별자를 명시하지 않으면 자동으로 강한참조(Strong)으로 작동하며 reference Count를 1 증가시키게 된다.
    Weak: reference Count를 증가시키지 않는다. 상수에서 사용할 수 없고, 옵셔널 타입이여야 함.

#### **순환 참조에 대하여 설명하시오.**   
    절대로 reference Count가 0이 되지 못하는 상황을 의미. memeory Leak이 발생한다.
    weak, unowned를 사용함으로서 해결할 수 있다.
    
#### **강한 순환 참조 (Strong Reference Cycle) 는 어떤 경우에 발생하는지 설명하시오.**   
    클로저 내에서 self를 참조할 경우
    서로가 서로를 참조하여, reference Count가 절대로 0이 될수 없는 경우
    두가지 중 하나를 약한 참조로 변환

## Functional Programming
#### **함수형 프로그래밍이 무엇인지 설명하시오.**   
    자료처리를 함수의 계산으로 취급하고 상태와 가변 데이터 대신 불변 데이터를 처리하는 것을 함수 중심 프로그래밍이라고 합니다.
    즉 함수형 프로그래밍은
        1. Function을 이용해서
        2. No Side-Effect하도록
        3. Declarative Programming 하는것이다.

    명령형 프로그래밍의 경우 상태 값을 변경할 수 있어 예측하지 못한 에러를 유발할 수 있다.
    하지만 함수형 프로그래밍의 경우 순수함수를 사용하기 때문에 항상 예측된 결과가 나오게 된다.
    함수형 프로그래밍을 하려면 모듈 단위로 기능을 작게 쪼개야하고, 가변상태를 피하도록 프로그래밍해야하며, 타입을 신중하게 사용해야합니다.
        
#### **고차 함수가 무엇인지 설명하시오.**   
    고차함수란 함수를 매개변수로 받는 함수를 말한다
        
#### **Swift Standard Library의 map, filter, reduce, compactMap, flatMap에 대하여 설명하시오.**   
    map
        맵은 자신을 호출할 때 매개변수로 전달된 함수를 실행하여 그 결과를 다시 반환해주는 함수이다. 
    filter
        필터는 컨테이너의 내부의 값을 걸러서 추출하는 역할을 한다.
        기존 컨텐츠를 변형하지 않고 특정 조건에 맞게 걸러내는 역할을 한다.
        리턴값이 true일때 포함하고 false일때 배제합니다.
    reduce
        리듀스는 컨테이너 내부의 컨텐츠를 하나로 합하는 기능을 실행한다.
    compactMap - map과 nil 반환 차이가 있다.
        컴팩트 맵은 매개변수로 전달된 클로저가 옵셔널 값을 생산할때(produce) 사용한다.
        nil이 아닌 값들만 배열 추가한 후 반환한다.
    flatMap - map은 N차원 배열, flatMap은 1차원 배열
        플랫 맵은 시퀀스의 각 요소들에 매개변수로 전달된 클로저을 적용하여 연속적인(concatenated) 값을 가지는 배열을 반환한다.
        일차원 컬렉션을 얻고자 사용한다.
    
## Architecture
#### **MVVM, Ribs, VIP 등 자신이 알고있는 아키텍쳐를 설명하시오.**   
#### **의존성 주입에 대하여 설명하시오.**   


## Rx
#### **Reactive Programming이 무엇인지 설명하시오.**   
    Rx는 무엇인가?
    Rx는 Reactive Programming 반응형 프로그래밍으로 되어있는 API입니다.
    반응형 프로그래밍은 변화할 수 있는 상태에 쉽게 대처할 수 있고 이벤트들의 순서,재사용성을 향상 시킬 수 있습니다.
    즉, 비동기식(여러 작업을 동시에 진행) 활동을 쉽고 안전하게 다룰 수 있습니다.
    반응형 프로그래밍은 Functional Programming을 활용한다.
    
    Functionanl Programming(함수형 프로그래밍)이란?
    함수형 프로그래밍의 특징은 순수함수(상태의 변화가 없는것)와 익명함수(closure),고차함수(map,reduce,filter)입니다.
    즉 RxSwift란 함수형 프로그래밍을 활용하는 반응형프로그래밍 API가 Swift와 합쳐진 것이라고 볼 수 있습니다.
    
#### **RxSwift의 장단점**   
    장점
        1. 코드를 깔끔하게 정리할 수 있다.   
        2. 비동기 작업을 쉽게 관리할 수 있다.   
        3. 반응형 패러다임이 제공하는 명확함, 비동기를 동기화 된 것인양 작성이 가능하다.   
    단점
        1. 높은 러닝커브   
        2. 클로저 사용이 많아 메모리 누수의 위험이 있다.   
    
#### **RxSwift에서 Hot Observable과 Cold Observable의 차이를 설명하시오.**   
    Hot : Observable은 생성되는 즉시 방출하기 시작하는데 이 때, 중간의 아이템을 방출하고 있더라고 그 아이템을 방출하기 시작합니다.   
    ex 
        Live Streaming. 방송 방송에 입장하게 되면 방송이 처음에 시작됐을 때부터가 아닌 현재 방송중인 시점부터 방송을 시청   
        
    Cold : Observer가 구독할 때까지 기다리고 구독하는 순간부터 방출하기 시작합니다. 그리고 Observer에게 방출하는 아이템의 전부를 볼 수 있게 보장합니다.   
    ex
        VOD. 언제부터 시청을 하더라도 처음부터 끝까지 원하는 부분을 시청   

#### **Subject와 drive의 차이를 설명하시오.**   
