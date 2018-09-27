---
layout: post
title: "[DAY-2] TTD Project"
date: 2018-09-26 21:56:59
author: Yongju Jin
categories: project
tag: [android, project, TTD]
---
# MainActivity 작업 \#1
MainActivity 작업을 했다. DataBinding을 처음 써보는거라 구글링하면서 진행하느라 간단한 UI 작업인대도 시간이 오래 걸렸다.

간단한 TextView 에 String 값 넣기 등 간단한 것들은 쉽게쉽게 지나갔다.

생일을 지정하기 위해서 Date Picker 를 활용하는데, 
AS에서 자동완성으로 `DatePickerBindingAdapter`가 보여서 들어가보니 
DataBinding에서 보던 문법이 보였다. 

그래서 최대한 `DatePickerBindingAdapter`를 최대한 사용해보려고 했지만, 결국 어떻게 사용한는지 
몰라서 일단 DatePickerDialog을 띄우고 등록한 리스너로 콜백을 받고, 리스너에서 view model를 호출하는 방식으로 구현하였다. 

TODO: DatePickerBindingAdapter 사용법 알기.

코드를 수정하다가 DataBinding에 view model 을 넘기는게 안되기 시작했다.
덕분에 `??` 같은 문법을 배울 수는 있었지만 아직까지 왜 view model을 setting 하는게 안되는지는 모르겠다.