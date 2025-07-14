---
title: "iOS 개발자로 살아가기 - 3년차 회고"
date: 2025-01-15
categories:
  - iOS
  - Career
tags:
  - iOS
  - Swift
  - RxSwift
  - 회고
toc: true
toc_sticky: true
---

## 들어가며

안녕하세요! 3년차 iOS 개발자 윤형찬입니다.
아이나비시스템즈에서 블랙박스 앱 개발을 담당하고 있습니다.

## 주요 경험

### 1. RxSwift + MVVM으로 대규모 리뉴얼

```swift
// ViewModel 예시
class BlackboxViewModel {
    let disposeBag = DisposeBag()
    
    // Input
    let viewDidLoad = PublishRelay<Void>()
    
    // Output
    let isLoading = BehaviorRelay<Bool>(value: false)
    let blackboxData = BehaviorRelay<[BlackboxModel]>(value: [])
    
    init(useCase: BlackboxUseCase) {
        // 바인딩 로직
    }
}
