---
layout: post
title: javascript
date: 2020-12-18 12:00
comments: true
external-url:
categories: programming
---

> 자바스크립트에서 쿠키의 중요성

자바스크립트 쿠키 예제

또다른 쿠키 예제를 만들어보자.

1. name, value, expire값을 받아내는 setCookie 함수를 제작하고, 그 함수가 cookie를 갱신시켜주도록 한다.

2. name을 받으면 그 쿠키값이 무엇인지 알려주는 getCookie 함수를 제작한다.

3. 쿠키가 존재한다면 존재하는 값에 맞게 행동하고, 존재하지 않았다면 쿠키를 만들도록 하는 chkCookie를 제작한다.

4. 쿠키를 삭제하는 함수를 구현한다.

5. 쿠키 기본 문서를 응용하자


```scala
function setCookie(cname, cvalue, exdays) {
	var d = new Date();
	d.setTime(d.getTime() + (exdays * 24 * 60 * 60 * 1000));
	var expires = "expires="+d.toUTCString();
	document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
}

function setCookie(name, value, day) {
        var day = new Date();
        // ms단위기에 1초로 변환->60초->60분->24시간->최종적으로 day
        day.setTime(day.getTime() + (1000 * 24 * 60 * 60 * day));
 
        var expires = "expires=" + day.toUTCString();
        document.cookie = name + "=" + value + ";" + expires + ";path=/";
}
```
```scala
function getCookie(cname) {
		 var name = cname + "=";
		 var ca = document.cookie.split(';');
		 for(var i = 0; i < ca.length; i++) {
			var c = ca[i];
			while (c.charAt(0) == ' ') {
			  c = c.substring(1);
			}
			if (c.indexOf(name) == 0) {
			  return c.substring(name.length, c.length);
			}
		 }
		 return "";
}
 function getCookie(name) {
        var cookieAray = document.cookie.split(";");
 
        for (var i in cookieAray) {
                if(cookieAray[i].split("=")[0].trim() == "username")
                    if (cookieAray[i][cookieAray[i].length - 1] != "=")
                        return cookieAray[i].split("=")[1];
        }
        return "";
}
```
```scala
function checkCookie() {
	var user=getCookie("username");
		  
	if (user != "") {
			alert("Welcome again " + user);
	} else {
			user = prompt("Please enter your name:","");
			 	
			if (user != "" && user != null) {
			setCookie("username", user, 30);
		}
	}
}
function chkCookie() {
            var user = getCookie("username");
 
            if (user != "") {
                alert("또 오셨네요 ? " + user + "님");
            }
            else {
                user = prompt("처음왔군요? 이름이 무엇인가요?", "예) OOO");
 
                if (user != "" && user != null)
                    setCookie("username", user, 365);
            }
}
```
```scala
function deleteCookie() {
            document.cookie = "username =; expires = Wed; 01 Jan 1990";
}
```

쿠키에 대해 좀더깊이 있는 이해가 필요하다.
