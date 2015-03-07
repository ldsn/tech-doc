---
title: [前端] wap前端提醒，toast使用方法
time: 2015-03-07
---
    
    var toast = require('ldsn-wap:widget/toast/toast.js');
    
    /**
     * 弹出
     * @param  {string} type  提示类型 success tip error
     * @param  {string} text  提示文本
     * @param  {bool} close 是否手动关闭
     */
    toast(type, text, close);
    toast('seccess', '操作成功！', false)
