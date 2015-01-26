#鲁大学生网 - 网络技术部 
###HTML编码规范 

##规范细则（强制部分，需严格遵守）： 
1、doctype
	
* 在html文档第一行添加标准模式声明 <!DOCTYPE html>。

2、语法

	* 属性的定义确保全部用双引号。
	* 其他需要闭合的标签一定要添加结束标签 如： div li 等。
	* 所有标签、属性、属性值必须采用小写，如特殊属性可略过。

3、属性规则

	* 强烈建议为 html 根元素指定 lang 属性，从而为文档设置正确的语言。这将有助于语音合成工具确定其所应该采用的发音，有助于翻译工具确定其翻译时所应遵守的规则 <html lang="zh-cn">。
	* 对属性值使用双引号引用，不要使用单引号。
	* meta 标签添加 X-UA-Compatible属性<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">。
	* 标签中属性和属性值不需要添加空格<img src="/test.jpg">。

4、文件规范

	*统一使用UTF-8 编码 <meta charset="UTF-8">。

5、资源引用

	* 不要指定type属性<link rel="stylesheet" href="code-guide.css"><script src="code-guide.js"></script>。
	* 引入外部 CSS 必须为 link 格式。
	* CSS 文件放至 结束 head 标签前，JavaScript 文件放至结束 body 标签前。
	* 在指向同域的图片、样式表、脚本等的URL中省略协议部分(http:, https:)。
	* 避免直接内嵌第三方脚本、样式表、图片等，必要时可以复制到本地服务器上使用。

6、语义化

	* 根据需要使用合适的标签。
	* 避免在HTML中直接定义style属性，包括运行时的动态添加，除动画之外。
	* 避免在HTML中直接定义JavaScript的onXXX属性。
	* HTML只用来表现信息结构，不要使用样式类标签，比如b, font, center等等。
	* 对图片、视频、Canvas等, 需要定义合适的alt文本。


##最佳实践（不强制部分，开发时推荐）： 
1、属性规则

	* js选择器和css选择器分开，如用js-xxx来标识js钩子。

2、资源引用

	* 在指向同域的图片、样式表、脚本等的URL中省略协议部分(http:, https:)。


3、HTML 校验

	* 使用合法的 HTML 标签，校验地址：http://validator.w3.org/。
