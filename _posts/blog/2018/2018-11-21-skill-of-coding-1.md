---
layout: post
title: "클린 코드의 비결 유지보수 가능한 코딩의 기술 자바편 #1"
date: 2018-11-21 21:56:59
author: Yongju Jin
categories: book
tag: [coding, book]
---
# 클린 코드의 비결 유지보수 가능한 코딩의 기술 자바편 #1

이 글의 내용은 `클린 코드의 비결 유지보수 가능한 코딩의 기술 자바편` 책을 읽으면서 내용을 정리한 글이다.

## 코드 단위를 짧게 하라.

> 코드 단위는 15라인을 넘기지 않게 작성  
> 작은 단위는 이해, 테스트, 재사용이 쉬워 유지보수성이 좋아짐

여기서 단위는 method 혹은 function 으로 생각하면 될 것 같음.  
만약 functions의 라인이 15라인을 넘어가게 된다면 리팩터링을 통해서 15랑인 이하로 맞추는 것이 좋음.

아래는 functions의 라인수를 줄이기 위해서 사용되는 리팩터링 기법이다.

### 1. 리팩터링 기법: 메서드 추출  

리팩터링 전

```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)

    supportFragmentManager.beginTransaction().run {
        add(R.id.fragment, HomeFragment())
        commit()
    }
}
```

리팩터링 후

```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)

    addFragment(HomeFragment())
}

fun addFragment(fragment: Fragment) {
    supportFragmentManager.beginTransaction().run {
        add(R.id.fragment, fragment)
        commit()
    }
}
```

[_refactoring.guru/extract-method_](https://refactoring.guru/extract-method)

### 2. 리팩터링 기법: 메서드를 메서드 객체로 대체

[_refactoring.guru/replace-method-with-method-object_](https://refactoring.guru/replace-method-with-method-object)