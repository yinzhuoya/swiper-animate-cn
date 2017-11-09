# swiper-animate-cn
- Swiper Animate is Swiper Chinese network to provide for the widget to quickly create CSS3 animations within Swiper, suitable for Swiper2.x and Swiper3.x. This plugin does not work in loop mode
- Swiper Animate是Swiper中文网提供的用于在Swiper内快速制作CSS3动画效果的小插件，适用于Swiper2.x,Swiper3.x和Swiper4.x 。
此插件不适用于loop模式

1. 引入模块
```
require('swiper-animate/animate.min.css')
var swiperAnimateCache = require('swiper-animate').swiperAnimateCache;
var swiperAnimate = require('swiper-animate').swiperAnimate;
var clearSwiperAnimate = require('swiper-animate').clearSwiperAnimate;
```
2. 初始化
```
<script>        
//Swiper3.x、Swiper2.x
  var mySwiper = new Swiper ('.swiper-container', {
    onInit: function(swiper){ //Swiper2.x的初始化是onFirstInit
      swiperAnimateCache(swiper); //隐藏动画元素 
      swiperAnimate(swiper); //初始化完成开始动画
    }, 
    onSlideChangeEnd: function(swiper){ 
      swiperAnimate(swiper); //每个slide切换结束时也运行当前slide动画
    } 
  }) 

//Swiper4.x
  var mySwiper = new Swiper ('.swiper-container', {
    on:{
      init: function(){
        swiperAnimateCache(this); //隐藏动画元素 
        swiperAnimate(this); //初始化完成开始动画
      }, 
      slideChange: function(){ 
        swiperAnimate(this); //每个slide切换结束时也运行当前slide动画
      } 
    }
  })        
</script>
  ```

3. 在需要运动的元素上面增加类名  ani   ，和其他的类似插件相同，Swiper Animate需要指定几个参数：
- swiper-animate-effect：切换效果，例如 fadeInUp 
- swiper-animate-duration：可选，动画持续时间（单位秒），例如 0.5s
- swiper-animate-delay：可选，动画延迟时间（单位秒），例如 0.3s
```
<div class="swiper-slide">
<p class="ani" swiper-animate-effect="fadeInUp" swiper-animate-duration="0.5s" swiper-animate-delay="0.3s">内容</p>
</div>
```
4.[demos](http://www.swiper.com.cn/usage/animate/index.html)
