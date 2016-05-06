---
layout: post
title: "some kinds of width and height"
date:   2016-05-6 10:14:54
categories: JavaScript
excerpt: 学习笔记
---

* content
{:toc}

## 各种各样的长和宽

---

### clientWidth and cliendHeight

clientWidth 和 clientHeight，顾名思义，用户能够看到的宽度和高度，也就是指可视的宽度和高度。在页面中，一个元素的可视区域就是指width（height）+padding。但是，如果出现了滚动条，那么它也会占据一部分的宽或者高，所以相应的可视区域的宽高就要减去滚动条所占的那部分。
clientWidth 和 clientHeight是DOM节点的只读属性，也就是可以获取但是不能修改的属性，获取得到的值并没有单位（如px,em等）

---

### offsetWidth and offsetHeight

offsetWidth 和 offsetHeight指的是占位宽或者是占位高，与clientWidth 和 clientHeight类似，它们两个也是DOM的只读属性，并不能对它们进行其他的设置。与可视高或者可视宽相比，它们只是多了一个border的值。

---

### offsetLeft and offsetTop

offsetLeft 和 offsetTop是DOM的只读属性，指的是当前元素到定位父级元素的距离（也就是偏移值）。但是，该值有些兼容性问题：
1、IE7以下：如果自身无定位，offsetLeft(offsetTop)是指该元素到body的距离；如果该元素本身有定位，则为到定位父级元素的距离，在该情境下，如果父级元素没有定位，则为到body的距离。

---

### clientLeft and clientTop

这两个值也是只读属性，指的是当前元素周围的边框的宽或者是高。当没有设置border时，则为0；

---

### scrollWidth and scrollHeight

这两个值是只读属性，没有单位，当一个元素的内容超过元素本身设置的宽高时，scrollWidth 和 scrollHeight才可以使用，它们指的是元素本身内容的长度或者宽度（真正的长度或者宽度。）

---

### style.width 和 style.height

它们是可读可写属性，带有单位，指的是元素的样式宽或者样式高。它只能够获取到该元素的行内样式，而并不能获取到该元素最终计算好的样式，这就是在读取属性值得时候和以上只读属性的区别，要获取计算好的样式，需使用obj.currentstyle（IE）和getComputedStyle(IE之外的浏览器)。

---

### scrollLeft and scrollTop

这对属性是可读写的，指的是当元素其中的内容超出其宽高的时候，元素被卷起的高度和宽度。

---

### clientX and clientY

clientX和clientY，这对属性是当事件发生时，鼠标点击位置相对于浏览器（可视区）的坐标，即浏览器左上角坐标的（0,0），该属性以浏览器左上角坐标为原点，计算鼠标点击位置距离其左上角的位置。不管浏览器窗口大小如何变化，都不会影响点击位置的坐标。

---

### screenX and screenY

screenX和screenY是事件发生时鼠标相对于屏幕的坐标，以设备屏幕的左上角为原点，事件发生时鼠标点击的地方即为该点的screenX和screenY值。是相对于屏幕而不是浏览器。

---

### offsetX and offsetY

这一对属性是指当事件发生时，鼠标点击位置相对于该事件源的位置，即点击该div，以该div左上角为原点来计算鼠标点击位置的坐标。

---

### pageX and pageY

该属性是事件发生时鼠标点击位置相对于页面的位置，通常浏览器窗口没有出现滚动条时，该属性和event.clientX及event.clientY是等价的，但是当浏览器出现滚动条的时候，pageX通常会大于clientX，因为页面还存在被卷起来的部分的宽度和高度。

