---
title: ldev 全局通用方法
description: ldev是全局的方法，主要包括事件监听、hash操作、模板引擎
citagory: product-doc
time: 2015-02-08 18:16:00
---
# ldev 全局通用方法

模板引擎

      var tpl = '<a href="<%=url%>"><%=string%></a>';
      var data = {url:"http://www.ldustu.com/",string:"鲁大学生网"};
      ldev.tmpl(tpl, data);
      //以上代码执行后将变为 <a href="http://www.ldustu.com">鲁大学学生网</a>

事件监听

      需要在响应服务模块的static/message.js 下创建事件
        ldev.message.create(name);
        
      在事件触发的地方使用
        //name 是需要触发的事件名称，param是参数
        ldev.message.trigger(name, param);
        
      时间监听，事件发生的地方
        //name 是事件的名称，func是函数，一个时间名称可绑定多个函数
        ldev.message.listen(name, param);

hash操作

      获取hash
        ldev.hash(name);
        
      添加hash
        ldev.hash(name, value);
        
      删除hash
        ldev.hash(name, null);
