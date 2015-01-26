#鲁大学生网 - 网络技术部
###JavaScript编码规范 

##规范细则（强制部分，需严格遵守）：

1、语言规范

	* 遵守EcmaScript 5的strict约束模式。形式为在一个文件或function的开头声明"use strict"。
	* 所有变量都必须使用var声明。
	* 使用NAMES_LIKE_THIS这样的形式定义常量。
	* 任何语句结束的分号都不要省略，包括函数体的结束处。
	* 异常可以使用，包括自定义异常，但慎用try/catch。
	* 对原始数据类型boolean, number, string，不要使用封装类，需要类型转换时可以使用。
	* eval()仅在必要情况下作对反序列化使用。
	* with() {}不允许使用。
	* this仅限在对象的构造函数、对象方法及创建闭包时使用。
	* for-in循环仅限在遍历object/map/hash的键值时使用，不能在遍历数组元素时使用。
	* 推荐使用字面量，包括字符串、数组、对象，非必要情况下不要使用String、Array或Object的构造函数；字符串的字面量定义不要使用多行字符串，及一个字符串字面量中避免出现分行符号\。

2、格式规范

	* 驼峰式命名函数、变量、类和方法。
	* 常量大写加下划线连接。
	* 命名空间以点连接。
	* 私有属性和方法前缀下划线。
	* 不要在单元操作符比如delete, typeof, void或者关键词return, throw等中使用。
	* 优先使用单引号，非必要情况下不使用双引号。



##最佳实践（不强制部分，开发时推荐）： 
1、语言规范

	* 使用JsLint校验，规则统一说明。
	* 注释中可以使用@const来声明常量，但一般NAMES_LIKE_THIS已经暗示这是常量，不要使用关键字const，IE是文盲。
	* 嵌套函数可以使用，但出于代码可读性考虑，不推荐使用。
	* 逻辑块中的函数声明不允许使用
		if ( x ) {
		function foo() {}
		}
		推荐： 
		if ( x ) {
		var foo = function() {}
		}
	* 出于可移植性的考虑，推荐优先使用标准用法，非必要情况下尽可能不依赖于任何非标准用法或依赖库的写法。
	* 不推荐多重继承，优先使用对象组合。
	* 推荐使用的方法和属性初始化方式：
	* delete关键字应该尽量避免使用，除非需要从一个对象的一个需要迭代的键值中去掉某个属性(key in obj).
	* 闭包小心使用，闭包对他外围的scope保留着引用指针，如果该闭包又被某个DOM元素引用，可能会导致循环引用和内存泄漏。
	* 不要使用数组作为map/hash使用，即，不允许使用数字以外的key作为对数组元素的引用。
	* 不要覆盖内建对象的原型prototype

2、格式规范

	* 可选参数使用opt_前缀
	* 可变参数的最后一个参数命名为var_args. 代码中不应该直接引用var_args，而是通过arguments数组使用。
	* 可选和可变参数也可以通过@param注释声明。
	*  
	* Getters and Setters不鼓励使用；如果使用，getter中不允许改变外部可观察的一些状态；对boolean类型的getter，使用isFoo()形式更为自然。
	* 全局代码必须使用命名空间；遵守团队的命名空间规则，子命名空间勿抛开父命名空间独立自创；内外有别，勿和外部代码使用同一命名空间；对长命名空间可以使用别名（局部变量）以提高可读性；不要在全局域中对命名空间使用别名，仅在函数逻辑块中使用。
	* 自定义toString()方法，强烈推荐，利于调试，无副作用。
	* 延迟初始化
	* 显式声明scope，提高代码可读性。
	* 使用JSDoc格式的注释；行内注释使用双斜线//，使用完整的句子描述，首字母大写，与双斜线用一个空格分离，以句号结束； 可见性(私有或受保护声明) 鼓励使用，可以通过JSDoc的@private 和 @protected 声明；JavaScript Types 鼓励使用JSDoc的type声明参数或返回值类型。

3、编译

	* 使用r.js和uglify等。

4、安全

	* 

5、小技巧

boolean表达式中以下均为false:

	* null
	* undefined
	* '' (空串)
	* 0 (数字)
	* 但以下为true:
	* '0' (字符串)
	* {} (空对象)
	* 应用实例

其他容易引起直觉错误的boolean表达式：

	* Boolean('0') == true
	* '0' != true
	* 0 != null
	* 0 == []
	* 0 == false
	* Boolean(null) == false
	* null != true
	* null != false
	* Boolean(undefined) == false
	* undefined != true
	* undefined != false
	* Boolean([]) == true
	* [] != true
	* [] == false
	* Boolean({}) == true
	* {} != true
	* {} != false

三元表达式( ?: )

		if (val != 0) {
		return foo();
		} else {
		return bar();
		}

	* 可以简写
		return val ? foo() : bar(); 
更多请参考：

<http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml>
<https://github.com/adamlu/javascript-style-guide>
