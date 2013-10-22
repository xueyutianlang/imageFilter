## 综述

imageFilter是一个图像处理的类库，用于实现实现图像滤镜与处理，包括明度、饱和度、高斯模糊、做旧效果、四角压暗、灰度、切割等等。

* 版本：1.0
* 作者：茅晓锋(加里)
* 标签：图像处理 canvas html5
* demo：[http://gallery.kissyui.com/imageFilter/1.0/demo/index.html](http://gallery.kissyui.com/imageFilter/1.0/demo/index.html)

## 快速使用

    S.use('gallery/imageFilter/1.0/index', function (S, ImageFilter) {

    	var srcImage = S.get("img");  //页面中需要处理的img节点
        var myImgFilter = new ImageFilter(srcImage); 

        myImgFilter.gray().blur(3); //灰度处理，高斯模糊。所有处理函数均支持链式表达式。
        myImgFilter.render();       //将处理结果渲染回页面

        myImgFilter.destroy();      //销毁组件
    });


## API说明

### 基本处理
- blur
- crop 图像裁剪
- setBrightness 设置亮度
- setContrast 设置对比度
- setOpacity 设置透明度

### 滤镜处理
- mixBrown 对图片混入褐色，显做旧效果
- mixColor 混色(混合方法：变暗)
- reverse 对图片做反色处理（负片效果）
- vignetting 对图片做四角压暗/变亮

### 其它方法
- destroy 销毁组件
- getImageSrc 获取图像的Base64编码
- render 渲染处理后的图片

## 其它说明
- 1.canvas禁止读取跨域图片数据，故无法使用tps地址提供的图片。此处sample使用的是同域图片。
- 2.此功能一般在用户上传图片(e.g.头像/晒图)的场景中使用，借用fileAPI（IE 10.0+）直接读取文件也是个不错的办法。或是在图片上传后由服务器端异步返回解码结果，回填到img节点的src属性，再进行处理。
- 3.为保证体验流畅，建议一次处理一张图片
- 4.兼容性: canvas为IE 9.0+ , fileAPI要求IE10.0+










