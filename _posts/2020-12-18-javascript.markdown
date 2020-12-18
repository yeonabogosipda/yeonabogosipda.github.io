---
layout: post
title: Studying math
date: 2020-12-18 12:00
comments: true
external-url:
categories: programming
---

> 자바스크립트 프로그램의 시작

It's amazing how a simple puzzle installs chaos among mathematicians and philosophers alike. Some would argue that the correct probability is ½: after all, the coin is **fair**, isn't it? Others would say that the correct probability should be ⅓. Think about this problem for a second because the correct answer is... **both**!

As many things in life, it's all a matter of perspective. And the conundrum here lies in the way the problem is phrased. But before going into maths and probability theory, we shall **simulate**:

```scala
var canvas = document.getElementById("myCanvas");
var ctx = canvas.getContext("2d");

var moleX = new Array(100, 100, 200, 200, 300, 300);
var moleY = new Array(100, 250, 100, 250, 100, 250);

var pos = {};
var rand = 0;
var mousePos = {};
var isMoleHit = false;
var acDelta = 0;
var msPerFrame = 50;
var score = 0;
var times = 0;

var backImage = new Image();
backImage.src = "images/background.png";

var holeImage = new Image();
holeImage.src = "images/hole.png";

var moleImage = new Image();
moleImage.src = "images/mole.png";

var hammerImage = new Image();
hammerImage.src = "images/hammer.png";

var hitSound = new Audio('sounds/hit.mp3');
```

```
구조화를 시켜야하는건가?
```