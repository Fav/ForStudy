---
layout: post
title: cesium-Animation
tags: cesiumjs
categories: cesiumjs文档
---

调用方法 new Cesium.AnimationViewModel(clockViewModel)

### 属性
***
+ Cesium.AnimationViewModel.defaultDateFormatter : AnimationViewModel~DateFormatter 
+ Cesium.AnimationViewModel.defaultTicks : Array.<Number>
+ clockViewModel : ClockViewModel
+ dateFormatter : AnimationViewModel~DateFormatter
+ dateLabel : String
+ faster : Command 
+ multiplierLabel : String
+ pauseViewModel : ToggleButtonViewModel
+ playForwardViewModel : ToggleButtonViewModel
+ playRealtimeViewModel : ToggleButtonViewModel
+ shuttleRingAngle : Number
+ shuttleRingDragging : Boolean
+ slower : Command
+ snapToTicks : Boolean (Default Value:  false)
+ timeLabel : String

### 方法
***
+ getShuttleRingTicks() → Array.<Number>
+ setShuttleRingTicks(positiveTicks)

positiveTicks	Array.<Number>	The list of known positive clock multipliers to associate with the shuttle ring.

### 类型定义
***
+ DateFormatter(date, viewModel) → String

	date →  JulianDate

+ TimeFormatter(date, viewModel) → String

	date	JulianDate