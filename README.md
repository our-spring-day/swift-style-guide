# swift-style-guide

> __Manna__ 프로젝트 협업 Swift 스타일 가이드입니다. 프로젝트 현황에 따라서 수시 변동될 수 있습니다.

##코드 레이아웃

###코드 들여쓰기
- 코드의 들여쓰기는 탭(tab)으로 구분합니다.

###네이밍

####클래스
- 클래스 이름에는 UpperCamelCase를 사용합니다.

####함수
-  lowerCamelCase를 사용합니다.
- Action 함수의 네이밍은 '주어 + 동사 + 목적어' 형태를 사용합니다.
	- *Tap(눌렀다 뗌)*은 UIControlEvents의 .touchUpInside에 대응하고, *Press(누름)*는 .touchDown에 대응합니다.
	- will~은 특정 행위가 일어나기 직전이고, did~는 특정 행위가 일어난 직후입니다.

####변수
- lowerCamelCase를 사용합니다.

####상수
- lowerCamelCase를 사용합니다.

### 주석
- //를 사용해서 문서화에 사용되는 주석을 남깁니다.

```swift
// 사용자 프로필을 그려주는 뷰
class ProfileView: UIView {

    // 사용자 닉네임을 그려주는 라벨
    var nameLabel: UILabel!
}
```
- // MARK:를 사용해서 연관된 코드를 구분짓습니다.
Objective-C에서 제공하는 #pragma mark와 같은 기능으로, 연관된 코드와 그렇지 않은 코드를 구분할 때 사용합니다.

```swift
// MARK: Init

override init(frame: CGRect) {
  // doSomething()
}

deinit {
  // doSomething()
}


// MARK: Layout

override func layoutSubviews() {
  // doSomething()
}


// MARK: Actions

override func menuButtonDidTap() {
  // doSomething()
}
```


###프로그래밍 권장사항
- 가능하다면 변수를 정의할 때 함께 초기화하도록 합니다. Then을 사용하면 초기화와 함께 속성을 지정할 수 있습니다.

```swfit
let label: UILabel = {
  let label = UILabel()
  label.textAlignment = .center
  label.textColor = .black
  label.text = "Hello, World!"
  return label
}()
```