---
title: "SwiftUI와 UIKit 함께 사용하기"
date: 2025-01-16
categories:
  - iOS
  - Tutorial
tags:
  - iOS
  - Swift
  - SwiftUI
  - UIKit
  - Integration
toc: true
toc_sticky: true
excerpt: "SwiftUI와 UIKit을 프로젝트에서 함께 사용하는 방법을 알아봅시다."
header:
  teaser: /assets/images/swiftui-uikit.jpg # 썸네일 이미지 (선택사항)
---

## SwiftUI와 UIKit 통합

기존 UIKit 프로젝트에 SwiftUI를 도입하는 방법...

```swift
import SwiftUI
import UIKit

class SwiftUIViewController: UIViewController {
    override func viewDidLoad() {
        super.viewDidLoad()

        let swiftUIView = UIHostingController(rootView: ContentView())
        addChild(swiftUIView)
        view.addSubview(swiftUIView.view)

        // Auto Layout 설정
        swiftUIView.view.translatesAutoresizingMaskIntoConstraints = false
        NSLayoutConstraint.activate([
            swiftUIView.view.topAnchor.constraint(equalTo: view.topAnchor),
            swiftUIView.view.leadingAnchor.constraint(equalTo: view.leadingAnchor),
            swiftUIView.view.trailingAnchor.constraint(equalTo: view.trailingAnchor),
            swiftUIView.view.bottomAnchor.constraint(equalTo: view.bottomAnchor)
        ])

        swiftUIView.didMove(toParent: self)
    }
}
```
