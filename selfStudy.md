

## iOS selfStudy

------

### Optional

- 일반 자료형은 nil을 가질수없다. 문자열이나 정수형 같은..., 대신 옵셔널 타입으로 선언된 자료형은 nil값을 저장할 수 있다. 
- 옵셔널 타입이 실제로 가질수있는 값의 종류는 두가지다. 오류가 발생할 가능성이 있지만 실제 실행 결과에서는 오류가 발생하지 않았을때 nil이 아닌값, 실제 실행결과에서 오류 발생시 반환되는 nil값이 두번쨰.
- 잠재적으로 오류가 발생할 가능성이 있는 상황 => 옵셔널 타입을 사용.
- 일반 자료형을 옵셔널 타입으로 정의하는 방법 -> ?만 붙이면 된다.

> 옵셔널 해제방식은 명시적 해제와 묵시적 해제로 나뉜다. 

- 명시적해제는 다시 강제적해제와 비 강제적 해제로 나뉘고
- 묵시적해제는 컴파일러에 의한 자동해제와 !연산자를 사용한 자동해제로 나눌수있다.

옵셔널 강제해제는 옵셔널 타입의 변수나 상수 뒤에 !만 붙이면 된다. 강제 해제 연산자를 사용할때는 먼저 옵셔널 값이 nil인지 점검해야 한다. 

비강제적인 해제 구문으로는 if 구문 내에서 조건식 대신 옵셔널 타입의 값을 일반 타입의 변수나 상수에 할당하는 구문을 사용하는 방식으로 옵셔널 바인딩이라고 한다. If let 구문이 있다.

컴파일러에 의한 옵셔널 자동해제는 항상 !연산자를 사용하여 옵셔널을 강제 해제하거나 옵셔널 바인딩을 통해 일반 자료형으로 바꿔줘야한다. 

묵시적해제는 옵셔널이지만 값을 사용하려고 할때는 자동으로 옵셔널이 해제된 값을 제공하기 때문에 굳이 ! 연산자를 사용할 필요가 없는 구문. 일반 옵셔널 타입의 변수선언시 ! 연산자를 ? 대신에 붙여주면 끝.

------

### Function

함수는 뒤에 매개변수를 가질때 콜론을 붙여준다. 

ex) incrementBy: 

##### *튜플*

튜플의 속성으로 튜플을 반환하는 함수의 반환값을 대입 받은 변수나 상수는 튜플의 인덱스를 이용하여 튜플 내부의 요소로 사용할수있다. 

Ex) var Uinfo = getUserInfo()

UInfo.0 , UInfo.1 ...이런식으로 사용가능하다

튜플 항목은 언더바를 이용하면 변수 할당없이 건너뛸수 있다.

------

#### Closure - 익명함수

### 일급함수

다음 조건을 만족해야 일급함수라고 한다.

- 객체가 런타임에도 생성이 가능해야 한다.
- 인자값으로 객체를 전달할 수 있어야 한다.
- 반환값으로 객체를 사용할 수 있어야 한다.
- 변수나 데이터 구조 안에 저장할 수 있어야 한다.
- 할당에 사용된 이름과 관계없이 고유한 구별이 가능해야 한다.

###### 일급함수의 특성

1. 변수나 상수에 함수를 대입할 수 있다.

ex) let fn1 = foo(base: 5)

> ##### 함수를 호출할때 함수의 이름 다음에 함수 호출 연살자를 붙여야 했으나, 굳이 함수의 이름이 아니더라도 함수가 할당된 변수라면 그 변수에 함수 호출연산자() 를 붙여서 함수를 호출할 수 있다.

함수는 어차피 어떤값을 입력받는지와 어떤 값을 반환하는지 뿐이기 때문에 (인자 타입1, 인자 타입2) -> 반환 타입 이런 식으로 축약할 수 있다!!!! 단 아무것도 반환하지 않는 함수일 경우, Void라고 명시해야한다. void는 빈 튜플 타입을 나타내는 값으로 타입 얼리어스로 정의된 단어이다.

2. 함수의 반환 타입으로 함수를 사용할 수 있다.
3. 함수의 인자값으로 함수를 사용할 수 있다.

클로저란 외부 함수 내에서 내부 함수를 반환하고, 내부 함수가 외부 함수의 지역 변수나 상수를 참조할 때 만들어진다. 

스위프트에서 클로저라고 부르는 객체는 다음 세가지 경우 중 하나에 해당한다.

1. 전역함수
2. 중첩함수
3. 클로저 표현식

클로저 표현식은 func 키워드 함수명을 제외한 나머지 부분만 작성하는 경량 문법을 사용한다.

------

#### Property

저장 프로퍼티와 연산 프로퍼티 두 종류가 있다.

##### 저장 프로퍼티

- 입력된 값을 저장하거나 저장된 값을 제공하는 역할
- 상수 및 변수를 사용해서 정의 가능
- 클래스와 구조체에서는 사용이 가능하지만, 열거형에서는 사용할 수 없다.

클래스안에 저장 프로퍼티를 선언시 초기화 하는법

1. init()함수로 초기화 
2. 프로퍼티를 옵셔널 타입으로 바꿔준다.
3. 프로퍼티에 초기값을 할당해준다.

클로저를 이용하여 저장 프로퍼티를 초기화 할때 상수와 변수 모두를 사용할수 있다. 구문의 형식은 다음과 같다.

```swift
var/let 프로퍼티명: 타입 = {

 정의내용

return 반환값

}() 
```

이렇게 정의된 클로저 구문은 클래스나 구조체의 인스턴스가 생성될 때 함께 실행되어 초기값을 반환하고 이후로는 해당 인스턴스 내에서 재실행되지 않는다.

##### 연산 프로퍼티

- 특정 연산을 통해 값을 만들어 제공하는 역할
- 변수만 사용해서 정의 가능
- 클래스, 구조체, 열거형에서 모두 사용가능

##### 프로퍼티 옵저버

프로퍼티의 값이 변경되었을때 프로퍼티의 값이 설정되면 무조건 호출된다.

- willSet - 프로퍼티의 값이 변경되기 직전에 호출되는 옵저버
- didSet - 프로퍼티의 값이 변경된 직후에 호출되는 옵저버

##### 타입 프로퍼티

인스턴스를 따로 생성하지 않고 클래스나 구조체 자체에 값을 저장하게 되며 이를 타입 프로퍼티라고 부른다.

클래스나 구조체 , 열거형 객체 내에 선언하는 것이므로 선언된 객체 내에서만 접근 가능한 범위를 가진다.

정의

```swift
static let/var 프로퍼티명 = 초기값
*or*
class let/var 프로퍼티명 : 타입 {
  get {
    return 반환값
  }
  set {
    
  }
}
```

------

#### Up / Down Casting 

업 캐스팅

- 객체 as 변환할 타입

다운 캐스팅

- 객체 as? 변환할 타입
- 객체 as! 변환할 타입

------

##### 열거형 정의

```swift
enum Direction {
case north
case south
case east, west
}
```

------

## UI

- UIScreen - 기기에 연결되는 물리적인 화면을 정의하는 객체
- UIWindow - 화면 그리기 지원 도구를 제공하는 객체
- UIView - 그리기를 수행할 객체 시트
- UIKit - 화면 구성용 객체들이 들어있는 프레임 워크
  - c/c++ 에서의 #include 와 같으나 import 는 헤더 파일을 반드시 한 번만 부르도록 한다.
  - UIKit 파일은 앱의 사용자 인터페이스를 생성하고 관리하는 기본 객체 정보를 담고있다.
- AppDelegate는 앱 전체의 생명주기 관리를 위임받은 객체인 앱 델리게이트를 구현한 클래스이다. App Delegate 객체는 앱내에서 오직 하나의 인스턴스만 생성되도록 시스템적으로 보장받는다.

------

### AppDelegate

- 앱 전체의 생명 주기 관리를 위임 받는 객체를 가진 클래스

------

##### 뷰의 상태변화 

- viewDidLoad() - 초기화 작업을 할때 ,로드된 직후 호출
- viewWillAppear() - 로드되기 직전에 호출
- viewDidAppear() - 추가되어 화면이 표시되면 호출되는 메서드
- viewWillDisappear() - 뷰가 계층에서 사라지기 직전에 호출되는 메소드
- viewDidDisappear() - 뷰가 계층에서 사라진 후 호출되는 메소드

------

#### 화면 전환 기법

1. 뷰를 이용한 화면 전환
2. 뷰 컨트롤러 직접 호출에 의한 화면 전환

present()로 뷰 컨트롤러를 호출하면 새로운 객체가 생성되는 동시에 기존 화면 위로 표시된다. 

네비게이션 컨트롤러에 의해 화면이 전황되었을 때 이전 화면으로 되돌아가는 메소드는 popViewController()이며, 이 메소드는 이전 화면으로 되돌아갈 때 애니메이션 처리를 할것인지 여부로 인자값으로 입력받는다. 

- 매뉴얼 세그 

자동 액션세그와 달리 수동 실행 세그웨이이다. 

performSegue(withIdentifier: <세그웨이 식별자>, sender: <세그웨이 실행 객체>)

- 커스텀 세그

------

UserDefaults 객체

- UserDefaults 객체를 사용하여 값을 주고받을수 있다.
- UserDefaults는 런타임 환경에서 동작하는 객체.

값을 읽어올 때 

ex) string(forKey:)

값을 저장할 때

ex)  set(_:forKey:)

- standard 속성을 통해 제공되는 표준 사용자 기본 저장소에 데이터를 저장하거나 읽기만 하면된다.
- UserDefaults로 읽어들인 데이터는 옵셔널 타입으로 처리된다.

```swift
let ud = UserDefaults.standard
ud.set(self.email.text, forkey: "email")
ud.set(self.isUpdate.text, forkey: "isUpdate")
ud.set(self.interval.text, forkey: "interval")
//UserDefaults에 저장한 객체는 함께 저장된 키를 통해 구분된다.
```

------

#### Singleton

##### **앱 전체에서 공유될 수 있는 자원들을 캡슐화한 객체** 

특정한 용도의 객체를 하나 만들어서 공통적으로 사용하고 싶을 때 사용하는 방법. 메모리낭비 방지, 데이터 공유 가능. 앱의 생명 주기 동안 하나의 인스턴스만 생성을 보장하는 클래스를 의미. 이는 단순히 하나의 인스턴스 생성을 보장하는 것이 아니라 **앱 전체에서 공유될 수 있는 자원들을 캡슐화한 객체**, 예시) UserDefault, URLSession이 있다.

------

## Delegate Pattern

하나의 객체가 모든 일을 처리하는 것이 아니라 처리해야 할 일 중 일부를 다른 객체에 넘기는 것을 의미.

delegte속성은 델리게이트 메소드가 구현된 객체의 참조 정보를 저장한다.

------

#### 최초 응답자(First Responder)

모바일 기기의 디스플레이에 앱의 콘텐츠를 표현하기 위해 사용하는 UIWindow 객체는 사용자 인터페이스 구조에서 사용자에 가장 가까이 위치한 객체로 사용자로부터 발생하는 터치 관련 이벤트를 내부 객체로 전달하는 역할을 담당한다.

------

#### 테이블 뷰

테이블 뷰 컨트롤러 -> 테이블 뷰 -> 테이블 뷰 셀 -> 컨텐츠 뷰

프로토 타입 셀에는 셀 컨텐츠와 악세서리 뷰가 있다.

프로토타입 셀에는 자동으로 이미지나 텍스트 콘텐츠를 삽입할수 있는 속성이 제공된다. 

필수 구현 메소드 

1. ##### tableView(_: numberOfRowInSection:)

- 테이블 뷰가 생성해야 할 행의 개수
- 이 메소드에 의해 테이블 뷰의 행 수가 결정되는 것.
- 인자로 테이블 뷰의 객체 정보와 섹션정보를 전달한다. 

2. ##### tableView(_: cellForRowAt:)

- 각 행이 화면에 표현해야 할 내용을 구성하는데 사용
- 인자로 테이블 뷰의 객체 정보와 구성할 행에 대한 참조 정보를 전달한다.

3. ##### tableView(_: didSelectRowAt:)

- 특정 행을 선택했을 때 호출되는 메소드
- dequeueReusableCell(withIdentifier:) -> 사용된 테이블 셀 인스턴스가 폐기되지 않고 재사용을 위해

```swift
let cell = tableView.dequeueReusableCell(withIdentifier: "ListCell")!
cell.textLabel?.text = row.title
//만약 테이블 셀의 textLabel 속성에 값이 있으면 하위 속성인 .text에 row.title 값을 대입하고, 없으면 아무것도 처리하지 않는다. -> 옵셔널 체인!
```

------

viewWithTag

------

UIImage(named: ) // 프로젝트 내에 있는 이미지를 읽어 객체를 생성한다.

```swift
var img = UIImage(named: <프로젝트 내 파일 경로>) 
//이미지의 이름뿐만 아니라 원래는 경로설정도 해줘야함.
```

------

##### 테이블 뷰 의 행 높이 결정

1. tableView(_: estimatedHeightForRowAt:)

- 테이블 뷰에서 특정 행의 높이를 설정하고 싶을때 사용하는 메소드
- self.tableView.rowHeight = <원하는 행 높이>

2. 셀프사이징 셀

- estiamtedRowHeight 프로퍼티 -> 셀 전체의 높이를 결정하기 전에 임시로 사용할 셀의 높이를 나타낸다.
- UITableViewAutomaticDimension 객체 -> rowHeight 속성에 대입되어 높이값이 동적으로 설정될 것을 테이블 뷰에 알려주는 역할을 한다.

------

### 네트워크 통신

- 소켓 방식
- 비연결 지향 통신 - http등의 프로토콜. 
- RESTful 방식

www과 같은 분산 하이퍼 미디어 시스템을 위한 소프트웨어 아키텍처의 한 형식. 네트워크 자원을 정의하고 자원에 대한 주소를 관리하는 방법이다. http프로토콜을 바탕으로 필요한 데이터를 별도의 규약 없이 주고받기만 하면된다.

RESTful 시스템은 일반적으로 서버에게 요청하려는 정보를 URI를 통해서 나타낸다. 요청 정보는 URI 단위마다 슬래시로 구분된다. 

일반적으로 서버에 요청하는 정보의 타입은 쓰기 읽기 수정 삭제의 네 가지로 구분된다. 일반적으로 웹에서 사용되는 http 메소드의 종류는 get, post 두가지이다. 데이터를 요청하려면 get을 사용하고, 데이터를 전송하려면 post를 사용한다. 

#### XML 방식과 JSON 방식

- XML 은 태그로 이루어진 마크업 형식. 대신 데이터의 용량이 커질수 있다.
- JSON 은 자바스크립트 언어에서 객체의 속성을 표현하기 위한 방법

#### JSON 방식

데이터 구조를 집합, 리스트 두 종류로 나눌수있다. 

JSON 객체는 {키 : 데이터} 형태로 이루어진 딕셔너리 데이터 집합이다. 

JSON 배열은 [ ] 형태 이다. 데이터를 파싱할 때는 JSONSerialization 객체의 jsonObject() 메소드를 사용하는것이 좋다.

------

##### ViewController 에서 테이블 뷰를 추가하고 싶을 땐,

- tableViewDataSource 와 tableViewDelegate를 상속받아 필요한 메소드를 구현해줘야한다. 
- 클래스(*ViewController*)에 데이터 소스나 델리게이트를 사용하는 객체(*tableView*)가 추가되면 이들 객체가 필요한 메소드를 어디서 찾을수 있는지에대한 객체 참조 정보를 알려줘야한다. 

```swift
self.tableView.dataSource = self
self.tableView.delegate = self
```

------

##### ICon size

보통 탭바는 알파값만을 이용하여 제작하는 편이 좋다.

30 x 30 - sample.png

60 x 60 - sample@2x.png

90 x 90 - sample@3x.png

------

##### Auto-Resizing , Auto-Layout

- 자동 크기 조절

![page75image61698448.jpg](/Users/chokyungjin/Desktop/page75image61698448.jpg) 

![page71image61645552.png](/Users/chokyungjin/Library/Application Support/typora-user-images/page71image61645552.png) 

------

##### iOS 화면 표현구조

- 윈도우 - iOS에서 디바이스의 스크린을 빈틈없이 채우기 위한 객체. 항상 유저 인터페이스 표현 계층의 최상위에 위치. 뷰의 일종이지만 직접 콘텐츠를 가지지는 않으며 콘텐츠를 가진 뷰를 내부에 배치하여 화면에 출력하는 역할만 한다.
- 뷰 - 콘텐츠를 담아 스크린 상에 표시하고, 사용자의 입력에 반응하는 객체. 윈도우와 뷰 사이에는 뷰 컨트롤러를 통해 연결. 뷰 컨트롤러는 뷰의 계층을 관리하여 윈도우에 전달하고, 모바일 디바이스에서 감지된 터치 이벤트를 윈도우로부터 전달받아 처리하는 역할을 한다. 투명 필름이라고 생각하자. 뷰라는 투명 필름위에 콘텐츠나 서브 뷰를 올려놓는다.

------

##### 뷰 컨트롤러 

- 뷰 컨트롤러 - 앱의 근간을 이루는 객체로, 모든 앱은 적어도 하나 이상의 뷰 컨트롤러로 구성된다. 주된 역할은 화면을 구성하는 요소인 뷰를 관리하는 것이지만 단순히 여기서 그치지 않고 화면과 데이터 사이의 상호작용을 관리하는 역할까지 담당한다. 

##### 콘텐츠 뷰 컨트롤러

- UITableVIewController, UICollectionVIewController, UIScrollVIewController, UIVIewController가 있다.
- 화면에 표현할 콘텐츠를 관리하는 컨트롤러다. 기본 클래스는 UIViewController이다. 

##### 컨테이너 뷰 컨트롤러

- 뷰컨과 뷰컨의 연결 관계를 관리하는 컨트롤러이다. 

------

##### addSubView(_:)

- 인자값으로 입력된 객체의 슈퍼 뷰에 추가해주는 역할이다. 원하는 객체를 화면에 배치하려면 이 메소드를 사용해야한다. 

------

##### CGPoint, CGSize,CGRect 구조체

- CGPoint - 위치를 나타낼 때 사용.
- CGSize - 크기를 표현할 때 사용.
- CGRect - CGPoint, CGSize만으론 위치와 크기를 동시에 가지는 객체의 정보를 표현하기엔 충분하지 않다. 2차원 좌표에서 네가지 값을 사용하여 직사각형의 위치와 크기를 표현하는 구조체이다. 

------

##### Frame, Bounds 속성

- frame은 뷰의 위치와 크기를 지정하는데 사용되는 속성. 

```swift
view.frame = CGRect(x:50, y: 70, width: 90, height: 130)
```

- frame의 좌표 기준은 슈퍼 뷰이다. 슈퍼 뷰의 기준점을 원점(0,0)으로 하여 자신을 계산한다.
- bounds에서 좌표 기준은 자기 자신이다. 
- Frame 속성은 뷰 자신의 위치나 크기 등 영역을 설정하는 경우에 사용한다. 
- Bounds 속성은 뷰의 내부에 있는 객체와의 관계에서 사용한다. 

------

UI

- button 의 타이틀을 설정할 때에는 setTitle(_:for:)메소드를 사용해야한다. 
- 화면 전체의 너비를 읽어와 이등분한 값을 적용하고 싶을 때.
  - btn.center = CGPoint(x: self.view.frame.size.width / 2, y: 100)

*액션 메소드를 프로그래밍 방식으로 구현*

##### addTarget(_:action:for:)

- Target - 호출할 대상 메소드가 있는 인스턴스를 가리킨다. 액션 메소드는 보통 뷰 컨트롤러에 정의되기 때문에 target 매개변수에는 뷰 컨트롤러 인스턴스가 전달되는 경우가 대부분이며, 특히 같은 뷰 컨트롤러 내에 액션 메소드가 작성되어 있으면 self를 인자값으로 전달한다. 
- action - 호출할 메소드를 지정하는 매개변수. 매개변수 타입은 Selector, 함수를 직접 지정하는 기능을 가진 일종의 함수 선택자로, 실제로 사용할 때에는 #selector(함수이름) 형태로 작성하면 된다. 
- for - 실행 조건을 지정하는 매개변수. 어떤 조건을 만족했을 때 액션 메소드가 실행되도록 할 것이냐에 관한것.

------

##### IBOutlet 

- 아울렛 변수를 사용하면 시스템은 알아서 스토리보드의 정보를 바탕으로 객체를 초기화 한다음, 이 객체에 대한 참조를 변수에 대입한다. 하지만 아울렛 변수없이 프로그래밍 방식으로 사용하면 직접 객체를 생성해 주어야한다.

------

##### 탭 바  컨트롤러

탭 바가 활성화되는 순간에 탭에 연결된 뷰 컨트롤러의 화면을 읽어드리므로 자동으로 활동화되지않는다. 따라서 didFinish 의 메소드에 탭바 아이템의 초기화코드를 작성하는게 좋다.

```swift
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // Override point for customization after application launch.
        
        if let tbc = self.window?.rootViewController as? UITabBarController {
            if let tabItems = tbc.tabBar.items {
                tabItems[0].image = UIImage(named: "calendar")
                tabItems[1].image = UIImage(named: "file-tree")
                tabItems[2].image = UIImage(named: "photo")
                
                tabItems[0].title = "calendar"
                tabItems[1].title = "file-tree"
                tabItems[2].title = "photo"
            }
        }
        
        return true
    }
// 토글 방식의 탭바 숨기기 
override func touchesEnded(_ touches: Set<UITouch>, with event: UIEvent?) {
        let tabBar = self.tabBarController?.tabBar
        tabBar?.isHidden = (tabBar?.isHidden == true) ? false : true
        //토글 방식의 탭바 숨기기
    }

//탭바가 Didload했을 때 처음 선택되는 탭을 고르는 메소드
self.onTabbarItemClick(self.tabItem01)
// 탭 바에 연결된 뷰 컨트롤러를 전환할 때에는 화면 전환 코드를 작성할 필요가 없다. 단지 원하는 뷰 컨트롤러의 인덱스 번호를 탭 바 컨트롤러의 selectedIndex 속성에 할당하기만 하면 알아서 해줌.
self.selectedIndex = sender.tag

```

------

##### 외형 프록시 객체

- 화면 요소별 속성을 공통으로 적용할 수 있는 객체. 외형 프록시 객체에 속성을 설정해 두면, 해당 타입으로 생성된 모든 객체에 해당속성이 적용된다. 외형 프록시 객체는 대부분의 객체에서 appearance() 메소드를 통해 지원한다. 

```swift
UITabbar.appearance()	//탭바의 외형 프록시 객체
UITabbar.appearance().tintColor = UIColor.white	//탭바 속성의 프록시 객체
```

------

##### 앱 델리게이트 역할

- UIResponder 클래스를 상속받고, UIApplicationDelegate 프로토콜을 구현해야한다.
- 클래스 내부에는 UIWindow 타입의 변수 window가 정의 되어있어야하고 변수이름은 반드시 window어야 한다. 
- @UIApplicationMain 어트리뷰트를 추가하여 시스템에 앱 델리게이트로 인식시키는 과정이 필요하다. @UIApplicationMain 어트리뷰트는 프로젝트 전체를 통틀어 하나의 클래스에만 지정되어야한다. 

------

##### 네비게이션 바 영역

```swift
// 왼쪽 오른쪽에 바 버튼 아이템 객체 생성
let v = UIView()
        v.frame = CGRect(x: 0, y: 0, width: 150, height: 37)
        v.backgroundColor = .brown
        
        let leftItem = UIBarButtonItem(customView: v)
        self.navigationItem.leftBarButtonItem = leftItem
        
let rv = UIView()
        rv.frame = CGRect(x: 0, y: 0, width: 100, height: 37)
        rv.backgroundColor = .brown
        
        let rightItem = UIBarButtonItem(customView: rv)
        self.navigationItem.rightBarButtonItem = rightItem
        
```

------

##### 알림 컨트롤러

- 뷰 컨트롤러 객체를 활용하여 알림창의 배경을 바꿀수있다.

```swift
  let v = UIViewController()
        v.view.backgroundColor = .red
        alert.setValue(v, forKey: "contentViewController")
// 알림 뷰 컨트롤러에서 setValue를 활용하여 UIViewController 객체의 속성에 값을 설정하고, contentViewController 인자를 활용하여 넣어준다.

```

```swift
let alert = UIAlertController(title: nil , message: "기본 메세지", preferredStyle: .alert)
//title 을 nil로 바꾸면 해당하는 영역을 지워버린다. message도 마찬가지
```

------

##### MapKit

- 맵킷 프레임워크 
- CLLocationCoordinate2D - 표시할 위치
- MKCoordinateSpan - 맵의 축척, 지도가 보여줄 넓이
- MKCoordinateRegion - 지도의 영역을 정의

```swift
 let point = MKPointAnnotation()
    point.coordinate = pos
    mapkitView.addAnnotation(point)
//위치를 핀으로 표시해준다.
```

------

##### init(coder:)

- 스토리보드 방식으로 객체를 생성할 때 호출되는 초기화 메소드다. 스토리보드에서 CSButton 클래스 타입의 버튼 객체를 사용하면 이 초기화 메소드가 사용된다.
- 스토리보드에서 사용하는 초기화 메소드는 init(coder: )로 규격화되어 있다. 
- 멤버와이즈 초기화 메소드 - 눈에 보이지않는 자동으로 생성되는 init() 메소드이다. 저장 프로퍼티는 자동으로 생성되지만 클래스는 초기화 메소드가 제공되지 않는다. 

------

##### ?? 연산자

- ( 옵셔널 타입의 값 ) ?? (값이 nil일 때 대신 사용할 값)

- (a != nil) ? a! : b

- a ?? b

- ###### a가 nil이면 b를, a 가 nil이 아니면 옵셔널을 해제한 a!를 리턴한다.

------

##### 프로필 이미지 둥글게 만드는 법

```swift
let defaultImage = UIImage(named: "account.jpg")
        self.profileImageLabel.image = defaultImage
        self.profileImageLabel.frame = CGRect(x: 10, y: 10, width: 50, height: 50)
        
        //프로필 이미지 둥글게 만들기!!!!
        self.profileImageLabel.layer.cornerRadius = (self.profileImageLabel.frame.width / 2)
        self.profileImageLabel.layer.borderWidth = 0
        self.profileImageLabel.layer.masksToBounds = true
```

------

### Foundation

- 원시 데이터 타입 Int ,String, Dictionary 같은...

### UIKit

- 사용자 인터페이스 구성요소
- SiriKit, MapKit, MessageUI

------

### Use Core Data

- 기기 내부의 저장소에 데이터를 저장할 때 쓴느 데이터 저장을 지원하는 객체의 코어 데이터

------

### Main Interface

- 메인스토리 보드의 이름

------

### TableView

```swift
 override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return super.tableView(tableView, numberOfRowsInSection: section)
 }
override func numberOfSections(in tableView: UITableView) -> Int {
        return super.numberOfSections(in: tableView)
    }

// 스토리보드에 static으로 테이블 셀 개수를 설정했을때 부모 클래스에 정의된 메소드를 이용하면 테이블 뷰의 행 개수로 처리하면 된다.
```

------

### UITapGestureRecognizer

- 지정된 객체가 탭 되었을 때 이를 인식하고 지정된 메소드를 호출하는데, 사용자의 입장에서는 터치 이벤트의 액션 메소드 호출과 비슷하게 인식된다. 

---
### Data_Send

```swift
 override func prepare(for segue: UIStoryboardSegue, sender: Any?) {

        let destination = segue.destination	
   //세그에 대한 목적지
        let button = sender as! UIButton	
   // 센더에 대한 옵셔널 강제 해제.(어차피 버튼이니까 강제로 해제해줘도 괜찮다)
        destination.title = button.titleLabel?.text 
   //데이터가 전달된 다음 화면의 네비게이션 바 설정
 } 
```
Stepper

counting 되는값은 Value 프로퍼티로 접근 가능.
Stepper.Value의 리턴 값은 Double.
또한 Stepper의 Minimum, Maximum, Step을 직접 설정할 수 있다.
StackView

```swift
    @IBOutlet weak var stackViewCenterY: NSLayoutConstraint!
//이번에 Constraint를 IBOutlet으로 연결하는걸 배웠는데 정말 꿀팁인듯하다.
 UIView.animate(withDuration: duration, delay: 0.0, options: .init(rawValue: curve), animations: {
            
            self.logoImageView.alpha = 0
            
            // +로 갈수록 y값이 내려가고 -로 갈수록 y값이 올라간다.
            self.stackViewCenterY.constant = -keyboardHeight/2 + 50
        })
//스택뷰 CenterY 잡아와서 constant 계산
```

---

### Data Formatting

```swift
//Data Formatting
@IBAction func buttonTap(_ sender: UIButton) {            
        if userIsInTheMiddleOfTyping {
            //텍스트 필드에 보여주기위한 string input
            input.append(sender.currentTitle!)
            //print(input)
            //실제 계산에 들어가는 string real
            real.append(sender.currentTitle!)
            formatNumber(input: input)
          //여기서 input 값을 formatting으로 변환하고 resultLabel에 넣어줌
            input = "" 
        } else {
            //처음 텍스트에 아무것도 없을 때의logic
            input.append(sender.currentTitle!)
            resultLabel.text = input
            input = ""
        }
        //뒤에 string 으로 인식하기 위해 true로 설정
        userIsInTheMiddleOfTyping = true
        
    }
```



---

### tabBar delegate

```swift
 override func tabBar(_ tabBar: UITabBar, didSelect item: UITabBarItem) {
        
       print( self.selectedIndex)
        if self.selectedIndex == 1 {
            self.navigationController?.navigationBar.topItem?.title = "BoxOffice"
              }
        else if self.selectedIndex == 2{
            self.navigationController?.navigationBar.topItem?.title = "My Diary"
        }
        else if self.selectedIndex == 3{
            self.navigationController?.navigationBar.topItem?.title = "Recommend"
        }
        else {
            self.navigationController?.navigationBar.topItem?.title = "Home"
        }
        
    }
//tabBar didSelect 메소드에서 작성하면 탭바는 뷰 컨트롤러와 작용하는게 아니라 네비게이션 컨트롤러와 작용한다.

```
```swift
func tabBarController(_ tabBarController: UITabBarController, didSelect viewController: UIViewController) {
        print( self.selectedIndex)
               if self.selectedIndex == 1 {
                   self.navigationController?.navigationBar.topItem?.title = "BoxOffice"
                
                     }
               else if self.selectedIndex == 2{
                   self.navigationController?.navigationBar.topItem?.title = "My Diary"
               }
               else if self.selectedIndex == 3{
                   self.navigationController?.navigationBar.topItem?.title = "Recommend"
               }
               else {
                   self.navigationController?.navigationBar.topItem?.title = "Home"
               }
         
    }
//UITabBarControllerDelegate를 선언하고 tabBarController의 didSelect를 해서 뷰 컨트롤러 와 탭바의  작용을 할 수 있게 한다. 그리고 delegate = self 해줄것
```

* UIViewController의 프로퍼티에 navigationController ,tabBarController가 있다.