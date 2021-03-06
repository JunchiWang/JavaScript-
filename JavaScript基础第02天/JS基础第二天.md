# JS基础第二天

## 1.今日重点

```
1.运算符(比较运算符,逻辑运算符,赋值运算符)
2.流程控制语句
	单向条件判断(if)
	双向条件判断(if-else)
	多向条件判断(if-else if- else)
	三元运算符
	精准判断(switch)

```

## 2.运算符

### 1.算术运算符

```javascript
+ 加法
- 减法
* 乘法
/ 除法
% 取余

 var x = 5;
 var y = 10;

 console.log(x + y); // 15
 console.log(x * y); // 50
 console.log(x / y); // 0.5
 console.log(x % y); // 5
 // 0不能除数
 console.log(x / 0); // Infinity 
 console.log(x % 0); // NaN
```

### 2.一元运算符

```javascript
++ 自加  就是在自身基础上加1
例如 var a = 1;
	a = a+1;  
	a+=1;
	a++;   //后置++ , 先输出,再计算
	++a;  //前置++  , 先计算,再输出
	//以上四种写法都是加1操作
//就是一个加1问题,要么加1, 要么不加1.不用纠结.

-- 自减 就是在自身基础上减1
```



### 3.关系运算符

```javascript
>    大于
<    小于
>=   大于等于
<=   小于等于
==   等于
===  全等于
!=   不等于
!==  不等于

// ==与===的区别：==只进行值得比较，===类型和值同时相等，则相等
var result = '55' == 55;    // true
var result = '55' === 55;   // false 值相等，类型不相等
var result = 55 === 55;   // true
```

> 注意: 一个等于号表示赋值, 已经被编程语言占用了,所以才用两个等于号表示相等.



### 4.逻辑运算符

```javascript
&& 与运算符  表示并且,多个条件必须
|| 或运算符  表示或者,满足其一即可
!  非运算符  表示取反,类似于非也这句话(购物车中的反选功能)

找工作的条件: 必须满18岁,并且工作经验三年以上
找工作的条件: 必须满18岁,或者工作经验三年
```

### 5.赋值运算符

```javascript
JS中由于一个等于号被用来进行赋值, 也就是存数据,所以表示判断的等于最少两个等号.
 var num = 0;
 num += 5; //相当于  num = num + 5;
 num -= 5; //相当于  num = num - 5;
 num *= 5; //相当于  num = num * 5;
 num /= 5; //相当于  num = num / 5;
 num %= 5; //相当于  num = num % 5;
```

### 6.运算符优先级

```javascript
优先级从高到底
() 优先级最高
一元运算符 ++ -- !
算数运算符 先* / % 后 + -
关系运算符 > >= < <=
相等运算符 == != === !==
逻辑运算符 先&& 后||
赋值运算符

//这些东西想记也记不住的,但是你得知道括号里面的先算就好了.
```



## 3.流程控制语句

### 1. 单向条件判断

```javascript
//如果明天不下雨, 我就去游乐场
//不下雨是条件, 当条件满足时执行,去游乐场
if(条件满足){
    //条件满足时执行
}
```

### 2. 双向条件判断

```javascript
//如果明天不下雨,我就去游乐场,否则,我就在家呆着
if(条件满足){
    //条件满足时执行
}else{
    //条件不满足时执行
}
```

### 3. 多向条件判断

```javascript
//如果你考试得分超过90分 奖励你100块,如果你考试得80分奖励你50块,否则你就得在家补课.
if(条件1满足){
    //执行事情1
}else if(条件2满足){
    //执行事情2
}else{
    //执行最后的结果
}

```

### 4. 精准条件判断

```javascript
 switch (expression) {
   case 常量1:
     语句;
     break;
   case 常量2:
     语句;
     break;
   ....
   case 常量n:
     语句;
     break;
   default:  // 默认语句 即 上面的条件都不成立的时候执行默认语句
     语句;
     break;
 }
```

1. 1. break可以省略，如果省略，代码会继续执行下一个case
   2. switch 语句在比较值时使用的是全等(===)操作符, 因此不会发生类型转换（例如，字符串'10' 不等于数值 10）
2. `对比if/else`if条件可以是范围也可以是具体值，但是switch是具体值判断,不能范围判断

### 5. 三元运算符

```javascript
//三元运算符是双向判断的一个简写方式,因为这个工作中最常用
条件 ? 条件满足执行 : 条件不满足执行;
 // 判断一个年龄是否成年, 当年龄超过18 返回  成年  否则返回未成年
   var age = 19; 
   var msg = age >= 18 ? '成年' : '未成年';
   console.log(msg);
```

### 6.练习

#### 	1.判断闰年

```javascript
  // 判断闰年  平年 
  //能整除4且不能整除100的为闰年.（如2004年就是闰年,1901年不是闰年）
  // 能够被 400 整除的 就是闰年
  //--------------------------------------------------
  // 1. 用户输入年份  并且保存这个年份 
  var year = prompt('请您输入要检测的年份:');
  // 2. 根据这个年份来判断 如果是闰年 弹出 是闰年   否则 弹出 平年
  // %  如果两个数余数是0  说明能够被整除
  if (year % 4 == 0 && year % 100 != 0 || year % 400 == 0) {
  	alert(year + ' 是闰年');
  } else {
  	alert(year + ' 是平年');
  }
```

#### 	2.根据分数划分等级

```javascript
// 接收用户输入的分数
// 1. 接受用户数据
var score = prompt('请输入你的成绩');
// 2.判断
if (score >= 90) {
	alert('宝贝，你是我的骄傲思密达');
} else if (score >= 80) {
	alert('你已经很出色了');
} else if (score >= 60) {
	alert('你的加油了');
} else {
	alert('我不想和你说话，我只想用鞭子和你说话');
}
```

#### 3.查询水果的价格

```javascript
// 查询水果案例  用户输入一个水果，可以弹出该水果的价格
// 1. 接受用户输入水果 并保持
var fruit = prompt('请输入您查询的水果:'); // fruit 水果
// 2. switch判断
switch (fruit) {
    case '苹果':
        alert('3.5元/斤');
        break;
    case '香蕉':
        alert('2.5元/斤');
        break;
    case '榴莲':
        alert('35元/斤');
        break;
    default:
        alert('没有此水果');
        break;
}
```

