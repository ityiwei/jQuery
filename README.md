# jQuery
jQuery入门到精通，一些小例子小效果。

//语法结构 

$("#div").stop();//停止当前动画，继续下一个动画 

$("#div").stop(true);//清除元素的所有动画 

$("#div").stop(false, true);//让当前动画直接到达末状态 ，继续下一个动画

$("#div").stop(true, true);//清除元素的所有动画，让当前动画直接到达末状态
//
toggle方法

切换 Hide() 和 Show()

检查每个元素是否可见。

如果元素已隐藏，则运行 show()。如果元素可见，则元素 hide()。这样就可以创造切换效果。

语法 $(selector).toggle(speed,callback)
//
.slideDown()：用滑动动画显示一个匹配元素
注意事项：

下拉动画是从无到有，所以一开始元素是需要先隐藏起来的，可以设置display:none
如 果提供回调函数参数，callback会在动画完成的时候调用。将不同的动画串联在一起按顺序排列执行是非常有用的。
这个回调函数不设置任何参数，但是 this会设成将要执行动画的那个DOM元素，如果多个元素一起做动画效果，
那么要非常注意，回调函数会在每一个元素执行完动画后都执行一次，而不是这组 动画整体才执行一次
//slideToggle
.slideToggle( [duration ] ,[ complete ] )
注意：

display属性值保存在jQuery的数据缓存中，所以display可以方便以后可以恢复到其初始值
当一个隐藏动画后，高度值达到0的时候，display 样式属性被设置为none，以确保该元素不再影响页面布局
//fadeOut
fadeOut()函数用于隐藏所有匹配的元素，并带有淡出的过渡动画效果
.fadeOut( [duration ], [ complete ] )
//fadeToggle
fadeToggle切换fadeOut与fadeIn效果，所谓"切换"，即如果元素当前是可见的，则将其隐藏(淡出)；如果元素当前是隐藏的，则使其显示(淡入)。
fadeIn：淡入效果，内容显示，opacity是0到1
fadeOut：淡出效果，内容隐藏，opacity是1到0

toggle、sildeToggle以及fadeToggle的区别：
toggle：切换显示与隐藏效果
sildeToggle：切换上下拉卷滚效果
fadeToggle：切换淡入淡出效果
当然细节上还是有更多的不同点:

toggle与slideToggle细节区别：
toggle：动态效果为从右至左。横向动作，toggle通过display来判断切换所有匹配元素的可见性
slideToggle：动态效果从下至上。竖向动作，slideToggle 通过高度变化来切换所有匹配元素的可见性
fadeToggle方法

fadeToggle() 方法在 fadeIn() 和 fadeOut() 方法之间切换。
元素是淡出显示的，fadeToggle() 会使用淡入效果显示它们。
元素是淡入显示的，fadeToggle() 会使用淡出效果显示它们。
注释：隐藏的元素不会被完全显示（不再影响页面的布局）

//animate
.animate( properties, options )
options参数

duration - 设置动画执行的时间
easing - 规定要使用的 easing 函数，过渡使用哪种缓动函数
step：规定每个动画的每一步完成之后要执行的函数
progress：每一次动画调用的时候会执行这个回调，就是一个进度的概念
complete：动画完成回调
其中最关键的一点就是：

如果多个元素执行动画，回调将在每个匹配的元素上执行一次，不是作为整个动画执行一次
列出常用的方式：

$('#elem').animate({
    width: 'toggle',  
    height: 'toggle'
  }, {
    duration: 5000,
    specialEasing: {
      width: 'linear',
      height: 'easeOutBounce'
    },
    complete: function() {
      $(this).after('<div>Animation complete.</div>');
    }
  });
















