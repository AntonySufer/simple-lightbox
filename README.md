# simple-lightbox
Simple Lightbox 照片放大插件，模仿微信 


1、引入文件
<link rel="stylesheet" href="css/simplelightbox.min.css">
<script src="js/jquery.min.js"></script>
<script src="js/simple-lightbox.min.js"></script>

2、HTML
<div class="dowebok">
    <a href="images/image1.jpg">
        <img src="images/thumbs/thumb1.jpg" alt="" title="第一张图片描述">
    </a>
    <a href="images/image2.jpg">
        <img src="images/thumbs/thumb2.jpg" alt="" title="第二张图片描述">
    </a>
    <a href="images/image3.jpg">
        <img src="images/thumbs/thumb3.jpg" alt="" title="第三张图片描述">
    </a>
    ...
</div>

3、JavaScript
$(function(){
    $('.dowebok a').simpleLightbox();
});
/***************************************************/
   //开启图片放大 插件
        openMPimg : function(){
        	 var $gallery = $('.gallery a').simpleLightbox({
                     close:false,
                     nav:true,
                     fileExt:"", //所有格式
                     docClose :true,
                     imgClose : true, //点击图片是否关闭  默认false
                     widthRatio : 0.8,//图像宽度于屏幕宽度的的比例
                     heightRatio : 0.8 //图像宽度于屏幕高度的的比例
                     });
                 
                 //Lightbox 开启后的事件 ,修复手机端点击空白区无法关闭bug
                 $gallery.on("shown.simplelightbox",function(){
                     $(".sl-overlay").on("click",function(){
                         $gallery.close();
                     });
                       //点击图片关闭,方法在lightbox库
                      $gallery.imgCloseFun();
                 });
       
      }


overlay 布尔值 true 显示遮罩 
spinner 布尔值 true 显示 Loading 效果 
nav 布尔值 true 显示左右导航 
navText 数组 [‘&larr;’,’&rarr;’] 左右导航的文本 
captions 布尔值 true 显示标题/描述 
captionsData 字符串 title 标题/描述来源，可指定 title 或 data-title 
close 布尔值 true 显示关闭按钮 
closeText 整数 123456 关闭按钮的文本 
fileExt 正则表达式 ‘png|jpg|jpeg|gif’ 限制图片格式 
animationSpeed 整数 250 动画过度时间 
preloading 布尔值 true 预加载图片 
enableKeyboard 布尔值 true 键盘支持，方向键控制，Esc 退出 
loop 布尔值 true 循环 
docClose 布尔值 true 点击空白处关闭 
swipeTolerance 整数 50 移动设备上滑动多少像素开始切换 
className 字符串 simple-lightbox 添加 class 
widthRatio 浮点数 0.8 图像宽度于屏幕宽度的的比例 
heightRatio 浮点数 0.9 图像宽度于屏幕高度的的比例 

自定义事件


名称

说明


show.simplelightbox Lightbox 开启前的事件 
shown.simplelightbox Lightbox 开启后的事件 
close.simplelightbox Lightbox 关闭前的事件 
closed.simplelightbox Lightbox 关闭后的事件 

例如：
$('.dowebok a').on('open.simplelightbox', function(){
    alert('准备开启 Simple Lightbox');
});

公共方法


名称

说明


open 开启 Lightbox 
close 关闭 Lightbox 
next 显示下一个 
prev 显示上一个 
destroy 销毁 Lightbox 


