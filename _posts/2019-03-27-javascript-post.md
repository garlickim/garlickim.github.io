---
layout: post
title:  "자바스크립트에서 사용자 플랫폼을 판단하는 법"
date:   2019-03-27 10:00:00
categories: javascript
tags: featured
---

Javascript에서 사용자 플랫폼(PC/Mobile 여부)를 판단하여 처리하고자 할때 하기 코드를 참고하세요.


```javascript

$(document).ready(function(){
	
	checkUserPlatform();
	
});

// 사용자 플랫폼이 PC인지 Mobile인지 판단하여 그에 따른 로직 처리
function checkUserPlatform(){
	
	var filter = "win16|win32|win64|mac|macintel";
	
	if(navigator.platform){
		if(0 > filter.indexOf(navigator.platform.toLowerCase())){
      // 모바일이면
		} else{
      // PC이면
    }
	}
  
};

```
