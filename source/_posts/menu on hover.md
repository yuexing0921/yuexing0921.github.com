---
title: 鼠标hover弹menu
date: 2016-10-20 16:21:27
categories:
- menu
tags:
- 动态menu
---
##### 前端开发经常碰到动态menu的开发，比如说，列表页，搜索下拉框等等。。。

###### 鼠标hover第一层，右边弹出第二层，再hover第二层，弹出第三层，依次类推。
需求很简单，当然代码也简单


```html
<ul >
<li >
  <a href="">一级菜单</a>
  <ul >
	<li>
	  <a href="#" target="_blank">二级菜单</a>
	  <ul >
		<li>
		  <a href="#" target="_blank">三级菜单</a>
		  <ul >
			<li><a href="#" target="_blank">四级菜单</a></li>
		  </ul>
		</li>
	  </ul>
	</li>
	<li>
	  <a href="">二级菜单</a>
	  <ul >
		<li><a href="">三级菜单</a></li>
	  </ul>
	</li>
  </ul>
</li>
<li >
  <a href="">一级菜单</a>
  <ul >
	<li>
	  <a href="">二级菜单</a>
	  <ul >
		<li><a href="">三级菜单</a></li>
	  </ul>
	</li>
	<li>
	  <a href="">二级菜单</a>
	  <ul >
		<li><a href="">三级菜单</a></li>
	  </ul>
	</li>
  </ul>
</li>
 <li>一级菜单</li>
</ul>

```

```scss
ul{
  background: #000000;opacity: 0.6;
  font-size: 14px;
  li{
    position: relative;height: 20px;line-height: 20px;margin-left: 10px;cursor: pointer;
    width: 100px;
  }
  a{
    &:hover{color:$mainColor;}
  }
}
ul{
  display: inline-block;
  >li{
    >ul{
      display: none;position: absolute;background: #000000;opacity: 0.8;
      left: 60px;top: 0;
    }
    &:hover{
      >ul{display: block;}
    }
  }
}

```

