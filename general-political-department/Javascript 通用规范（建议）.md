---
title: Javascript 通用规范（建议）
description: Js前端通用规范，为了更好的合作
author: Edire
time: 2014-02-05 10:30:00
category: Javascript
---

# Javascript 通用规范（建议）
#### 为了更好的进行项目合作，让每个人的代码写出来不至于别人摸不到头脑，建议大家按照一下的规范进行编写代码
        
        /**
         * 简介
         * @author 作者姓名
         * @date 2015-02-04
         * @version 1.0.0
         */
        
        'use strict';
        
        //引用需要用到的组建
        var $ = require(''),
        
        
        //私有方法
        var _pri = {
        	//UI元素集合
        	node: {
        
        	},
        	//接口配置信息
        	api: {
        
        	},
        	//模块模板信息
        	tmpl: {
        	},
        	//默认配置信息
        	conf: {
        
        	},
        	//绑定元素事件
        	bindUI: function () {
        
        	},
        	//事件监听中心
        	listenCenter: {
        
        	},
        	//私有工具类
        	util: {
        
        	}
        }
        
        
        //根据业务需求，写下面
        
        
        /**
         * 如果页面需要加载后运行某些函数
         * 需要定义init()代表初始化 并执行
         */
        var init = function () {
        	
        }
        init();
        
        /**
         * 如果页面需要暴露接口函数
         * 需要定义 一个对象 或者构造函数
         * 一下是在fisp模块化环境下，如果不在fisp模块化环境下可不用鞋module.export
         */
        var _pub = {
            login: function () {},
            isRun: true
        }
        module.export = _pub;
        
        //或者创建构造函数
        function test() {
                this.num = 123;
        }
        test.prototype.func = function () {
                var _this = this;  //要把this复制给 _this
                console.log(_this.num);
        }
        module.export = test;
        
####具体用法

（未完待续）
        
