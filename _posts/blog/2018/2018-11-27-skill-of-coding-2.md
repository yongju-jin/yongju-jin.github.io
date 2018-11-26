---
layout: post
title: "클린 코드의 비결 유지보수 가능한 코딩의 기술 자바편 #2"
date: 2018-11-27 21:56:59
author: Yongju Jin
categories: book
tag: [coding, book]
---
# 클린 코드의 비결 유지보수 가능한 코딩의 기술 자바편 #2

이 글의 내용은 `클린 코드의 비결 유지보수 가능한 코딩의 기술 자바편` 책을 읽으면서 내용을 정리한 글이다.

## 코드 단위는 간단하게 짜라

> 단위당 분기점은 4개로 제한.

한 function내 분기가 적을 수록 테스트 코드 작성이 쉬워질 거 같다.
아래는 분기를 줄이기 위한 리팩터링 방법이다.

### 1. 리팩터링 기법: 조건을 다형성으로 대체

```kotlin
fun getPrice(brand: Brand): Int {
  return when(brand) {
    BrandA -> 1000
    BrandB -> 500
  }
}
```

```kotlin
class BrandA: Brand() {
  override val price: 1000
}
  
class BrandB: Brand() {
  override val price: 500
}  

val price = brand.price
```

[_refactoring.guru/replace-conditional-with-polymorphism_](https://refactoring.guru/replace-conditional-with-polymorphism)

### 2. 리팩터링 기법: 중첩문을 보호절로 대체 

[_replace-nested-conditional-with-guard-clauses_](https://refactoring.guru/replace-nested-conditional-with-guard-clauses)