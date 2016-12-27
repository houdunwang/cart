# 购物车
##简介
为了便于商城系统的开发提供了完善的购物车处理类，使商城购物车处理更加方便快捷，程序员只需要专注业务流程而不用关注实现步骤，大大增加了开发效率。
[TOC]
##安装
使用 composer 命令进行安装或下载源代码使用。
```
composer require houdunwang/cart
```
> HDPHP 框架已经内置此组件，无需要安装


##操作
####添加购物车
添加购物车使用 \houdunwang\cart\Cart::add() 方法实现，购物车中的数据会写入到 $_SESSION 超全局数组中。
```
$data = [ 
	'id' 		=> 1, // 商品 ID 
	'name'		=>' 后盾网 PHP 视频教程光盘 ',// 商品名称 
	'num' 		=> 2, // 商品数量 
	'price' 	=> 988, // 商品价格 
	'options'   => []// 其他参数如价格、颜色、可以为数组或字符串 
	'color' 	=> 'red', 
	'size' 	    => 'L' 
]; 
\houdunwang\cart\Cart::add($data); // 添加到购物车 
print_r($_SESSION); 
```

####更新购物车
更新购物车需要传入商品的唯一 SID，同时传入更新的商品数量，
```
$data=array( 
	'sid'=>'4d854bc6',// 唯一 sid，添加购物车时自动生成 
	'num'=>88 
); 
\houdunwang\cart\Cart::update($data); 
```

####购物车中商品数据
```
\houdunwang\cart\Cart::getGoods(); 
```

####购物车所有商品数据
```
\houdunwang\cart\Cart::getAllData(); 
```

####清空购物车

```
\houdunwang\cart\Cart::flush(); 
```

####获得商品总价格
```
echo \houdunwang\cart\Cart::getTotalPrice();
```

####统计购物车中的商品数量
```
\houdunwang\cart\Cart::getTotalNums(); 
```

####获得定单号\houdunwang\cart\Cart::getOrderId()
```
\houdunwang\cart\Cart::getOrderId();
```