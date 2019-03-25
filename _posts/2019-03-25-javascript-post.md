---
layout: post
title:  "IOS 웹브라우저에서 Click Event가 안될 때"
date:   2019-03-25 11:00:00
categories: javascript
tags: featured
---

Javascript 사용 중, 아이폰에서 Click 이벤트가 작동하지 않는 경우가 있습니다. <br>
click 이벤트를 거는 경우, cursor 속성을 지정하면 문제가 해결 됩니다.

---------------------------------------

~~~
<ul id="ul_box">
    <li onclick="javascript:alert('success');" style="cursor: pointer;"></li>
    <li onclick="javascript:alert('success');" class="clickable"></li>
</ul>

<style>
    .clickable
    {
        cursor: pointer;
    }
</style>
~~~

li tag 두가지 방식 중, 선택하여 사용하시면 됩니다.
