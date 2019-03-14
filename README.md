# 总结了7中圣杯布局的解决方法 

1.基础float解决方法
```
<style type="text/css">
	.container > div{
		height: 100px;
	}
	.left{
		float:left;
		width: 300px;
		background: red;
	}
	.middle{
		background: yellow;
	}
	.right{
		float: right;
		width: 300px;
		background: blue;
	}
</style>
<div class="container">
	<div class="left"></div>
	<div class="right"></div>
	<div class="middle"></div>
</div>
```

*这里需要注意的是HTML中 是按照 左右中 排列的*


剩余六种方式的HTML结构都是如下这种形式的，下面就只写CSS
```
<div class="container">
	<div class="left"></div>
	<div class="middle"></div>
	<div class="right"></div>
</div>
```

2.绝对定位解决方法

```
<style type="text/css">
	.container > div{
		height: 100px;
		position: absolute;
	}
	.left{
		left:0;
		width: 300px;
		background: red;
	}
	.middle{
		left:300px;
		right: 300px;
		background: yellow;
	}
	.right{
		right: 0;
		width: 300px;
		background: blue;
	}
</style>
```
3.Flexbox解决方式

```
<style type="text/css">
	.container{
		display: flex;
	}
	.container > div{
		height: 100px;
	}
	.left{
		width: 300px;
		background: red;
	}
	.middle{
		flex:1;
		background: yellow;
	}
	.right{
		width: 300px;
		background: blue;
	}
</style>
```
4.table解决方式

```
<style type="text/css">
	.container{
		display: table;
		width: 100%;
	}
	.container > div{
		height: 100px;
		display: table-cell;
	}
	.left{
		width: 300px;
		background: red;
	}
	.middle{
		background: yellow;
	}
	.right{
		width: 300px;
		background: blue;
	}
</style>
```
5.grid解决方式

```
<style type="text/css">
	.container{
		display: grid;
		width: 100%;
		grid-template-rows: 100px;
		grid-template-columns: 300px auto 300px;
	}
	.left{
		background: red;
	}
	.middle{
		background: yellow;
	}
	.right{
		background: blue;
	}
</style>
```
6.calc()计算解决方法

```
<style type="text/css">
	.container>div{
		height: 100px;
	}
	.left,.middle,.right{
		float:left;
	}
	.left,.right{
		width: 300px;
	}
	.left{
		background: red;
	}
	.middle{
		width: calc(100% - 600px);
		background: yellow;
	}
	.right{
		background: blue;
	}
</style>
```
7.padding解决方法

```
<style type="text/css">
	.container{
		width: 100%;
		padding:0 300px;
		box-sizing: border-box;
	}
	.container>div{
		height:100px;
		float:left;
	}
	.left{
		width: 300px;
		margin-left:-300px;
		background: red;
	}
	.middle{
		width: 100%;
		background: yellow;	
	}
	.right{
		width: 300px;
		margin-right:-300px;
		background: blue;
	}
</style>
```
