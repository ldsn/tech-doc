---
title: '[前端] 上传组件使用 upload'
time: '2015-03-07'
---

         
         /**
          * 文件上传插件
          * @param  {string} btnId   上传按钮id
          * @param  {object} event   事件
          *                          FilesAdded
          *                          // 文件添加进队列后,处理相关的事情
          *                          BeforeUpload
          *                          文件上传前
          *                          UploadProgress
          *                          文件上传中，可做滚动条
          *                          FileUploaded
          *                          单个文件上传后
          *                          Error
          *                          文件上传错误
          *                          UploadComplete
          *                          文件列表上传结束
          *                          Key
          *                          文件名字，需要带目录 folderName/fileName.suffix
          * @param  {string} maxSize 上传最大限制 1mb 2mb
          */
         
        var upload = require('common:widget/upload/upload.js');
        upload('upload-img',
        {
            'FilesAdded': function(up, files) {
                plupload.each(files, function(file) {
                    // 文件添加进队列后,处理相关的事情
                });
            },
            'BeforeUpload': function(up, file) {
                   // 每个文件上传前,处理相关的事情
            },
            'UploadProgress': function(up, file) {
        
                   // 每个文件上传时,处理相关的事情
            },
            'FileUploaded': function(up, file, info) {
            },
            'Error': function(up, err, errTip) {
                   //上传出错时,处理相关的事情
            },
            'UploadComplete': function() {
                   //队列文件处理完毕后,处理相关的事情
            },
            'Key': function(up, file) {
                // 若想在前端对每个文件的key进行个性化处理，可以配置该函数
                // 该配置必须要在 unique_names: false , save_key: false 时才生效
                if(file.type == 'image/jpeg' || file.type == 'image/png'){
                  var nameSuffix = file.name.substring(file.name.lastIndexOf('.'));
                  var key = 'userUpload/' + Date.parse(new Date()) + nameSuffix;
                  // do something with key here
                  console.log('ok')
                  return key
                } else {
                  console.log('shit')
                }
            }
        }, '3mb');
