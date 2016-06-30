<h3>META相关</h3>

<h4>1. 添加到主屏后的标题（IOS）</h4>

<pre><code class='language-javascript'>&lt;meta name="apple-mobile-web-app-title" content="标题"&gt; 
</code></pre>

<h4>2. 启用 WebApp 全屏模式（IOS）</h4>

<p>当网站添加到主屏幕后再点击进行启动时，可隐藏地址栏（从浏览器跳转或输入链接进入并没有此效果）</p>

<pre><code class='language-javascript'>&lt;meta name="apple-mobile-web-app-capable" content="yes" /&gt; 
&lt;meta name="apple-touch-fullscreen" content="yes" /&gt; 
</code></pre>

&lt;!--more--&gt;

<h4>3. 百度禁止转码</h4>

<p>通过百度手机打开网页时，百度可能会对你的网页进行转码，往你页面贴上它的广告，非常之恶心。不过我们可以通过这个meta标签来禁止它：</p>

<pre><code class='language-javascript'>&lt;meta http-equiv="Cache-Control" content="no-siteapp" /&gt;
</code></pre>

<p><a href="http://m.baidu.com/pub/help.php?pn=22&amp;ssid=0&amp;from=844b&amp;bd_page_type=1">百度SiteApp转码声明</a></p>

<h4>4. 设置状态栏的背景颜色（IOS）</h4>

<p>设置状态栏的背景颜色，只有在 <code class='language-javascript'>"apple-mobile-web-app-capable" content="yes"</code> 时生效</p>

<pre><code class='language-javascript'>&lt;meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" /&gt; 
</code></pre>

<p>content 参数：</p>

<ul>
<li>default ：状态栏背景是白色。</li>
<li>black ：状态栏背景是黑色。</li>
<li>black-translucent ：状态栏背景是半透明。 如果设置为 default 或 black ,网页内容从状态栏底部开始。 如果设置为 black-translucent ,网页内容充满整个屏幕，顶部会被状态栏遮挡。</li>
</ul>

<h4>5. 移动端手机号码识别（IOS）</h4>

<p>在 iOS Safari （其他浏览器和Android均不会）上会对那些看起来像是电话号码的数字处理为电话链接，比如：</p>

<ul>
<li>7位数字，形如：1234567</li>
<li>带括号及加号的数字，形如：(+86)123456789</li>
<li>双连接线的数字，形如：00-00-00111</li>
<li>11位数字，形如：13800138000</li>
</ul>

<p><strong>可能还有其他类型的数字也会被识别。我们可以通过如下的meta来关闭电话号码的自动识别：</strong></p>

<pre><code class='language-javascript'>&lt;meta name="format-detection" content="telephone=no" /&gt;
</code></pre>

<p><strong>开启电话功能</strong></p>

<pre><code class='language-javascript'>&lt;a href="tel:123456"&gt;123456&lt;/a&gt;
</code></pre>

<p><strong>开启短信功能：</strong></p>

<pre><code class='language-javascript'>&lt;a href="sms:123456"&gt;123456&lt;/a&gt; 
</code></pre>

<h4>6. 移动端邮箱识别（Android）</h4>

<p>与电话号码的识别一样，在安卓上会对符合邮箱格式的字符串进行识别，我们可以通过如下的meta来管别邮箱的自动识别：</p>

<pre><code class='language-javascript'>&lt;meta content="email=no" name="format-detection" /&gt; 
</code></pre>

<p>同样地，我们也可以通过标签属性来开启长按邮箱地址弹出邮件发送的功能：</p>

<pre><code class='language-javascript'>&lt;a mailto:dooyoe@gmail.com"&gt;dooyoe@gmail.com&lt;/a&gt; 
</code></pre>

<h4>7. 添加智能 App 广告条 Smart App Banner（IOS 6+ Safari）</h4>

<pre><code class='language-javascript'>&lt;meta name="apple-itunes-app" content="app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL"&gt;
</code></pre>

<h4>8. IOS Web app启动动画</h4>

<p>由于iPad 的启动画面是不包括状态栏区域的。所以启动图片需要减去状态栏区域所对应的方向上的20px大小，相应地在retina设备上要减去40px的大小</p>

<pre><code class='language-javascript'>&lt;!-- iPhone --&gt;
&lt;link href="apple-touch-startup-image-320x460.png" media="(device-width: 320px)" rel="apple-touch-startup-image"&gt;
&lt;!-- iPhone (Retina) --&gt;
&lt;link href="apple-touch-startup-image-640x960.png" media="(device-width: 320px) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image"&gt;
&lt;!-- iPad (portrait) --&gt;
&lt;link href="apple-touch-startup-image-768x1004.png" media="(device-width: 768px) and (orientation: portrait)" rel="apple-touch-startup-image"&gt;
&lt;!-- iPad (landscape) --&gt;
&lt;link href="apple-touch-startup-image-748x1024.png" media="(device-width: 768px) and (orientation: landscape)" rel="apple-touch-startup-image"&gt;
&lt;!-- iPad (Retina, portrait) --&gt;
&lt;link href="apple-touch-startup-image-1536x2008.png" media="(device-width: 1536px) and (orientation: portrait) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image"&gt;
&lt;!-- iPad (Retina, landscape) --&gt;
&lt;link href="apple-touch-startup-image-2048x1496.png" media="(device-width: 1536px)  and (orientation: landscape) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image"&gt;
</code></pre>

<p><code class='language-javascript'>（landscape：横屏 | portrait：竖屏）</code></p>

<h4>9. 添加到主屏后的APP图标</h4>

<p>指定web app添加到主屏后的图标路径，有两种略微不同的方式：</p>

<pre><code class='language-javascript'>&lt;!-- 设计原图 --&gt;
&lt;link href="short_cut_114x114.png" rel="apple-touch-icon-precomposed"&gt;
&lt;!-- 添加高光效果 --&gt;
&lt;link href="short_cut_114x114.png" rel="apple-touch-icon"&gt;
</code></pre>

<p>*  apple-touch-icon：在IOS6及以下的版本会自动为图标添加一层高光效果（IOS7开始已使用扁平化的设计风格）
*  apple-touch-icon-precomposed：使用“设计原图图标”</p>

<p><em>效果：</em></p>

<p><img src="http://7u2qrr.com1.z0.glb.clouddn.com/blog_142325268767880.png" alt title /></p>

<p><strong>图标尺寸：</strong></p>

<p>可通过指定size属性来为不同的设备提供不同的图标（但通常来说，我们只需提供一个114 x 114 pixels大小的图标即可 ）</p>

<p><em>官方说明如下</em></p>

<pre><code class='language-javascript'>Create different sizes of your app icon for different devices. If you’re creating a universal app, you need to supply app icons in all four sizes.

For iPhone and iPod touch both of these sizes are required:

57 x 57 pixels

114 x 114 pixels (high resolution)

For iPad, both of these sizes are required:

72 x 72 pixels

144 x 144 (high resolution)
</code></pre>

<h4>10. 优先使用最新版本 IE 和 Chrome</h4>

<pre><code class='language-javascript'>&lt;meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" /&gt; 
</code></pre>

<h4>11.viewport模板</h4>

<pre><code class='language-javascript'>&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
&lt;meta charset="utf-8"&gt;
&lt;meta content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no" name="viewport"&gt;
&lt;meta content="yes" name="apple-mobile-web-app-capable"&gt;
&lt;meta content="black" name="apple-mobile-web-app-status-bar-style"&gt;
&lt;meta content="telephone=no" name="format-detection"&gt;
&lt;meta content="email=no" name="format-detection"&gt;
&lt;title&gt;标题&lt;/title&gt;
&lt;link rel="stylesheet" href="index.css"&gt;
&lt;/head&gt;
&lt;body&gt;
这里开始内容
&lt;/body&gt;
&lt;/html&gt;
</code></pre>

<h3>常见问题</h3>

<h4>1、移动端如何定义字体font-family</h4>

<p>三大手机系统的字体： </p>

<p><strong><em>ios 系统</em></strong></p>

<ul>
<li>默认中文字体是Heiti SC</li>
<li>默认英文字体是Helvetica</li>
<li>默认数字字体是HelveticaNeue</li>
<li>无微软雅黑字体</li>
</ul>

<p><strong><em>android 系统</em></strong></p>

<ul>
<li>默认中文字体是Droidsansfallback</li>
<li>默认英文和数字字体是Droid Sans</li>
<li>无微软雅黑字体</li>
</ul>

<p><strong><em>winphone 系统</em></strong></p>

<ul>
<li>默认中文字体是Dengxian(方正等线体)</li>
<li>默认英文和数字字体是Segoe</li>
<li>无微软雅黑字体</li>
</ul>

<p>各个手机系统有自己的默认字体，且都不支持微软雅黑
如无特殊需求，手机端无需定义中文字体，使用系统默认
英文字体和数字字体可使用 Helvetica ，三种系统都支持</p>

<pre><code class='language-javascript'>* 移动端定义字体的代码 */
body{font-family:Helvetica;}
</code></pre>

<h4>2、移动端字体单位font-size选择px还是rem</h4>

<p>对于只需要适配手机设备，使用px即可</p>

<p>对于需要适配各种移动设备，使用rem，例如只需要适配iPhone和iPad等分辨率差别比较挺大的设备</p>

<p>rem配置参考：</p>

<pre><code class='language-javascript'>html {font-size:10px}
@media screen and (min-width:480px) and (max-width:639px) {
    html {
        font-size: 15px
    }
}
@media screen and (min-width:640px) and (max-width:719px) {
    html {
        font-size: 20px
    }
}
@media screen and (min-width:720px) and (max-width:749px) {
    html {
        font-size: 22.5px
    }
}
@media screen and (min-width:750px) and (max-width:799px) {
    html {
        font-size: 23.5px
    }
}
@media screen and (min-width:800px) and (max-width:959px) {
    html {
        font-size: 25px
    }
}
@media screen and (min-width:960px) and (max-width:1079px) {
    html {
        font-size: 30px
    }
}
@media screen and (min-width:1080px) {
    html {
        font-size: 32px
    }
}
</code></pre>

<h4>3、移动端touch事件(区分webkit 和 winphone)</h4>

<p>当用户手指放在移动设备在屏幕上滑动会触发的touch事件</p>

<p><strong><em>以下支持webkit</em></strong></p>

<ul>
<li>touchstart——当手指触碰屏幕时候发生。不管当前有多少只手指</li>
<li>touchmove——当手指在屏幕上滑动时连续触发。通常我们再滑屏页面，会调用event的preventDefault()可以阻止默认情况的发生：阻止页面滚动</li>
<li>touchend——当手指离开屏幕时触发</li>
<li>touchcancel——系统停止跟踪触摸时候会触发。例如在触摸过程中突然页面alert()一个提示框，此时会触发该事件，这个事件比较少用</li>
</ul>

<p><strong><em>以下支持winphone 8</em></strong></p>

<ul>
<li>MSPointerDown——当手指触碰屏幕时候发生。不管当前有多少只手指</li>
<li>MSPointerMove——当手指在屏幕上滑动时连续触发。通常我们再滑屏页面，会调用css的html{-ms-touch-action: none;}可以阻止默认情况的发生：阻止页面滚动</li>
<li>MSPointerUp——当手指离开屏幕时触发</li>
</ul>

<h4>4、移动端click屏幕产生200-300 ms的延迟响应</h4>

<p>移动设备上的web网页是有300ms延迟的，玩玩会造成按钮点击延迟甚至是点击失效。</p>

<p>以下是历史原因：</p>

<p>2007年苹果发布首款iphone上IOS系统搭载的safari为了将适用于PC端上大屏幕的网页能比较好的展示在手机端上，使用了双击缩放(double tap to zoom)的方案，比如你在手机上用浏览器打开一个PC上的网页，你可能在看到页面内容虽然可以撑满整个屏幕，但是字体、图片都很小看不清，此时可以快速双击屏幕上的某一部分，你就能看清该部分放大后的内容，再次双击后能回到原始状态。</p>

<p>双击缩放是指用手指在屏幕上快速点击两次，iOS 自带的 Safari 浏览器会将网页缩放至原始比例。</p>

<p>原因就出在浏览器需要如何判断快速点击上，当用户在屏幕上单击某一个元素时候，例如跳转链接<code class='language-javascript'>&lt;a href="#"&gt;&lt;/a&gt;</code>，此处浏览器会先捕获该次单击，但浏览器不能决定用户是单纯要点击链接还是要双击该部分区域进行缩放操作，所以，捕获第一次单击后，浏览器会先Hold一段时间t，如果在t时间区间里用户未进行下一次点击，则浏览器会做单击跳转链接的处理，如果t时间里用户进行了第二次单击操作，则浏览器会禁止跳转，转而进行对该部分区域页面的缩放操作。那么这个时间区间t有多少呢？在IOS safari下，大概为300毫秒。这就是延迟的由来。造成的后果用户纯粹单击页面，页面需要过一段时间才响应，给用户慢体验感觉，对于web开发者来说是，页面js捕获click事件的回调函数处理，需要300ms后才生效，也就间接导致影响其他业务逻辑的处理。</p>

<p><strong>解决方案：</strong></p>

<ul>
<li><a href="https://github.com/ftlabs/fastclick">fastclick</a>可以解决在手机上点击事件的300ms延迟</li>
<li>zepto的touch模块，tap事件也是为了解决在click的延迟问题</li>
</ul>

<p><strong>触摸事件的响应顺序</strong></p>

<pre><code class='language-javascript'>1、ontouchstart 
2、ontouchmove 
3、ontouchend 
4、onclick
</code></pre>

<p>解决300ms延迟的问题，也可以通过绑定ontouchstart事件，加快对事件的响应</p>

<h4>5、什么是Retina 显示屏，带来了什么问题</h4>

<p><code class='language-javascript'>retina</code>：一种具备超高像素密度的液晶屏，同样大小的屏幕上显示的像素点由1个变为多个，如在同样带下的屏幕上，苹果设备的retina显示屏中，像素点1个变为4个</p>

<p>在高清显示屏中的位图被放大，图片会变得模糊，<code class='language-javascript'>因此移动端的视觉稿通常会设计为传统PC的2倍</code></p>

<p>那么，前端的应对方案是：</p>

<p>设计稿切出来的图片长宽保证为偶数，并使用backgroud-size把图片缩小为原来的1/2</p>

<pre><code class='language-javascript'>//例如图片宽高为：200px*200px，那么写法如下
.css{width:100px;height:100px;background-size:100px 100px;}
</code></pre>

<p>其它元素的取值为原来的1/2，例如视觉稿40px的字体，使用样式的写法为20px</p>

<pre><code class='language-javascript'>.css{font-size:20px}
</code></pre>

<h4>6、ios系统中元素被触摸时产生的半透明灰色遮罩怎么去掉</h4>

<p>ios用户点击一个链接，会出现一个半透明灰色遮罩, 如果想要禁用，可设置-webkit-tap-highlight-color的alpha值为0，也就是属性值的最后一位设置为0就可以去除半透明灰色遮罩</p>

<pre><code class='language-javascript'>a,button,input,textarea{-webkit-tap-highlight-color: rgba(0,0,0,0;)}
</code></pre>

<h4>7、部分android系统中元素被点击时产生的边框怎么去掉</h4>

<p>android用户点击一个链接，会出现一个边框或者半透明灰色遮罩, 不同生产商定义出来额效果不一样，可设置-webkit-tap-highlight-color的alpha值为0去除部分机器自带的效果</p>

<pre><code class='language-javascript'>a,button,input,textarea{
    -webkit-tap-highlight-color: rgba(0,0,0,0;)
    -webkit-user-modify:read-write-plaintext-only; 
}
</code></pre>

<p><em>-webkit-user-modify有个副作用，就是输入法不再能够输入多个字符</em></p>

<p>另外，有些机型去除不了，如小米2</p>

<p>对于按钮类还有个办法，不使用a或者input标签，直接用div标签</p>

<h4>8、winphone系统a、input标签被点击时产生的半透明灰色背景怎么去掉</h4>

<pre><code class='language-javascript'>&lt;meta name="msapplication-tap-highlight" content="no"&gt;
</code></pre>

<h4>9、webkit表单元素的默认外观怎么重置</h4>

<pre><code class='language-javascript'>.css{-webkit-appearance:none;}
</code></pre>

<h4>10、webkit表单输入框placeholder的颜色值能改变么</h4>

<pre><code class='language-javascript'>input::-webkit-input-placeholder{color:#AAAAAA;}
input:focus::-webkit-input-placeholder{color:#EEEEEE;}
</code></pre>

<h4>11、webkit表单输入框placeholder的文字能换行么</h4>

<p><em>ios可以，android不行~</em></p>

<h4>12. 关闭iOS键盘首字母自动大写</h4>

<p>在iOS中，默认情况下键盘是开启首字母大写的功能的，如果启用这个功能，可以这样：</p>

<pre><code class='language-javascript'>&lt;input type="text" autocapitalize="off" /&gt;
</code></pre>

<h4>13. 关闭iOS输入自动修正</h4>

<p>和英文输入默认自动首字母大写那样，IOS还做了一个功能，默认输入法会开启自动修正输入内容，这样的话，用户经常要操作两次。如果不希望开启此功能，我们可以通过input标签属性来关闭掉：</p>

<pre><code class='language-javascript'>&lt;input type="text" autocorrect="off" /&gt; 
</code></pre>

<h4>14. 禁止文本缩放</h4>

<p>当移动设备横竖屏切换时，文本的大小会重新计算，进行相应的缩放，当我们不需要这种情况时，可以选择禁止：</p>

<pre><code class='language-javascript'>html {
　　      -webkit-text-size-adjust: 100%;
}
</code></pre>

<p>需要注意的是，PC端的该属性已经被移除，该属性在移动端要生效，必须设置 &#8216;meta viewport&#8217;。</p>

<h4>15. 移动端如何清除输入框内阴影</h4>

<p>在iOS上，输入框默认有内部阴影，但无法使用 box-shadow 来清除，如果不需要阴影，可以这样关闭：</p>

<pre><code class='language-javascript'>input,
textarea {
　　border: 0; /* 方法1 */
　　-webkit-appearance: none; /* 方法2 */
}
</code></pre>

<h4>16. 快速回弹滚动</h4>

<p>我们先来看看回弹滚动在手机浏览器发展的历史：</p>

<ul>
<li>早期的时候，移动端的浏览器都不支持非body元素的滚动条，所以一般都借助 iScroll;</li>
<li>Android 3.0/iOS解决了非body元素的滚动问题，但滚动条不可见，同时iOS上只能通过2个手指进行滚动；</li>
<li>Android 4.0解决了滚动条不可见及增加了快速回弹滚动效果，不过随后这个特性又被移除；</li>
<li>iOS从5.0开始解决了滚动条不可见及增加了快速回弹滚动效果</li>
</ul>

<p>在iOS上如果你想让一个元素拥有像 Native 的滚动效果，你可以这样做：</p>

<pre><code class='language-javascript'>    .xxx {
        overflow: auto; /* auto | scroll */
        -webkit-overflow-scrolling: touch;
    }
</code></pre>

<p><em>PS：iScroll用过之后感觉不是很好，有一些诡异的bug，这里推荐另外一个 iDangero Swiper，这个插件集成了滑屏滚动的强大功能（支持3D），而且还有回弹滚动的内置滚动条，官方地址：</em></p>

<p><a href="http://www.idangero.us/sliders/swiper/index.php">iDangero</a></p>

<h4>17. 移动端禁止选中内容</h4>

<p>如果你不想用户可以选中页面中的内容，那么你可以在css中禁掉：</p>

<pre><code class='language-javascript'>.user-select-none {
  -webkit-user-select: none;  /* Chrome all / Safari all */
  -moz-user-select: none;     /* Firefox all （移动端不需要） */
  -ms-user-select: none;      /* IE 10+ */      
}
</code></pre>

<h4>18. 移动端取消touch高亮效果</h4>

<p>在做移动端页面时，会发现所有a标签在触发点击时或者所有设置了伪类 :active 的元素，默认都会在激活状态时，显示高亮框，如果不想要这个高亮，那么你可以通过css以下方法来进行全局的禁止：</p>

<pre><code class='language-javascript'>html {
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
</code></pre>

<p>但这个方法在三星的机子上无效，有一种妥协的方法是把页面非真实跳转链接的a标签换成其它标签，可以解决这个问题。</p>

<h4>19. 如何禁止保存或拷贝图像（IOS）</h4>

<p>通常当你在手机或者pad上长按图像 img ，会弹出选项 存储图像 或者 拷贝图像，如果你不想让用户这么操作，那么你可以通过以下方法来禁止：</p>

<pre><code class='language-javascript'>img { -webkit-touch-callout: none; }
</code></pre>

<h4>20.模拟按钮hover效果</h4>

<p>移动端触摸按钮的效果，可明示用户有些事情正要发生，是一个比较好体验，但是移动设备中并没有鼠标指针，使用css的hover并不能满足我们的需求，还好国外有个激活css的active效果，代码如下，</p>

<pre><code class='language-javascript'>&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
&lt;meta charset="utf-8"&gt;
&lt;meta content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no" name="viewport"&gt;
&lt;meta content="yes" name="apple-mobile-web-app-capable"&gt;
&lt;meta content="black" name="apple-mobile-web-app-status-bar-style"&gt;
&lt;meta content="telephone=no" name="format-detection"&gt;
&lt;meta content="email=no" name="format-detection"&gt;
&lt;style type="text/css"&gt;
a{-webkit-tap-highlight-color: rgba(0,0,0,0);}
.btn-blue{display:block;height:42px;line-height:42px;text-align:center;border-radius:4px;font-size:18px;color:#FFFFFF;background-color: #4185F3;}
.btn-blue:active{background-color: #357AE8;}
&lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;

&lt;div class="btn-blue"&gt;按钮&lt;/div&gt;

&lt;script type="text/javascript"&gt;
document.addEventListener("touchstart", function(){}, true)
&lt;/script&gt;
&lt;/body&gt;
&lt;/html&gt;
</code></pre>

<p>兼容性ios5+、部分android 4+、winphone 8</p>

<p>要做到全兼容的办法，可通过绑定ontouchstart和ontouchend来控制按钮的类名</p>

<pre><code class='language-javascript'>&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
&lt;meta charset="utf-8"&gt;
&lt;meta content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no" name="viewport"&gt;
&lt;meta content="yes" name="apple-mobile-web-app-capable"&gt;
&lt;meta content="black" name="apple-mobile-web-app-status-bar-style"&gt;
&lt;meta content="telephone=no" name="format-detection"&gt;
&lt;meta content="email=no" name="format-detection"&gt;
&lt;style type="text/css"&gt;
a{-webkit-tap-highlight-color: rgba(0,0,0,0);}
.btn-blue{display:block;height:42px;line-height:42px;text-align:center;border-radius:4px;font-size:18px;color:#FFFFFF;background-color: #4185F3;}
.btn-blue-on{background-color: #357AE8;}
&lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;

&lt;div class="btn-blue"&gt;按钮&lt;/div&gt;

&lt;script type="text/javascript"&gt;
var btnBlue = document.querySelector(".btn-blue");
btnBlue.ontouchstart = function(){
    this.className = "btn-blue btn-blue-on"
}
btnBlue.ontouchend = function(){
    this.className = "btn-blue"
}
&lt;/script&gt;
&lt;/body&gt;
&lt;/html&gt;
</code></pre>

<h4>21.屏幕旋转的事件和样式</h4>

<p><strong>事件</strong></p>

<p>window.orientation，取值：正负90表示横屏模式、0和180表现为竖屏模式；</p>

<pre><code class='language-javascript'>window.onorientationchange = function(){
            switch(window.orientation){
                case -90:
                case 90:
                alert("横屏:" + window.orientation);
                case 0:
                case 180:
                alert("竖屏:" + window.orientation);
                break;
            }
} 
</code></pre>

<p><strong>样式</strong></p>

<pre><code class='language-javascript'>//竖屏时使用的样式
@media all and (orientation:portrait) {
    .css{}
}

//横屏时使用的样式
@media all and (orientation:landscape) {
    .css{}
}
</code></pre>

<h4>22.audio元素和video元素在ios和andriod中无法自动播放</h4>

<p>应对方案：触屏即播</p>

<pre><code class='language-javascript'>$('html').one('touchstart',function(){
    audio.play()
})
</code></pre>

<h4>23.摇一摇功能</h4>

<p>HTML5 deviceMotion：封装了运动传感器数据的事件，可以获取手机运动状态下的运动加速度等数据。</p>

<h4>24.手机拍照和上传图片</h4>

<p><code class='language-javascript'>&lt;input type="file"&gt;</code>的accept 属性</p>

<pre><code class='language-javascript'>&lt;!-- 选择照片 --&gt;
&lt;input type=file accept="image/*"&gt;
&lt;!-- 选择视频 --&gt;
&lt;input type=file accept="video/*"&gt;
</code></pre>

<p>使用总结：</p>

<ul>
<li>ios 有拍照、录像、选取本地图片功能</li>
<li>部分android只有选取本地图片功能</li>
<li>winphone不支持</li>
<li>input控件默认外观丑陋</li>
</ul>

<h4>25. 消除transition闪屏</h4>

<pre><code class='language-javascript'>.css{
    /*设置内嵌的元素在 3D 空间如何呈现：保留 3D*/
    -webkit-transform-style: preserve-3d;
    /*（设置进行转换的元素的背面在面对用户时是否可见：隐藏）*/
    -webkit-backface-visibility: hidden;
}
</code></pre>

<p><strong>开启硬件加速</strong></p>

<ul>
<li>解决页面闪白</li>
<li><p>保证动画流畅</p>

<pre><code class='language-javascript'>.css {
   -webkit-transform: translate3d(0, 0, 0);
   -moz-transform: translate3d(0, 0, 0);
   -ms-transform: translate3d(0, 0, 0);
   transform: translate3d(0, 0, 0);
}
</code></pre></li>
</ul>

<p>设计高性能CSS3动画的几个要素</p>

<ul>
<li>尽可能地使用合成属性transform和opacity来设计CSS3动画，</li>
<li>不使用position的left和top来定位</li>
<li>利用translate3D开启GPU加速</li>
</ul>

<h4>26. android 上去掉语音输入按钮</h4>

<pre><code class='language-javascript'>input::-webkit-input-speech-button {display: none}
</code></pre>

<h3>框架</h3>

<h4>1. 移动端基础框架</h4>

<ul>
<li><a href="http://zeptojs.com/">zepto.js</a> 语法与jquery几乎一样，会jquery基本会zepto~</li>
<li><p><a href="http://cubiq.org/iscroll-5">iscroll.js</a> 解决页面不支持弹性滚动，不支持fixed引起的问题~ 实现下拉刷新，滑屏，缩放等功能~</p></li>
<li><p><a href="http://underscorejs.org/">underscore.js</a> 该库提供了一整套函数式编程的实用功能，但是没有扩展任何JavaScript内置对象。</p></li>
<li><a href="https://github.com/ftlabs/fastclick">fastclick</a> 加快移动端点击响应时间</li>
<li><a href="http://daneden.github.io/animate.css/">animate.css</a> CSS3动画效果库</li>
</ul>

<h4>2. 滑屏框架</h4>

<p>适合上下滑屏、左右滑屏等滑屏切换页面的效果</p>

<ul>
<li><a href="https://github.com/peunzhang/slip.js">slip.js</a></li>
<li><a href="https://github.com/peunzhang/iSlider">iSlider.js</a></li>
<li><a href="https://github.com/peunzhang/fullpage">fullpage.js</a></li>
</ul>

<h4>3.瀑布流框架</h4>

<ul>
<li><a href="http://masonry.desandro.com/">masonry</a></li>
</ul>

<h3>工具推荐</h3>

<ul>
<li><a href="http://caniuse.com/">caniuse</a> 各浏览器支持html5属性查询</li>
<li><a href="http://paletton.com/#uid=1000u0kllllaFw0g0qFqFg0w0aF">paletton</a> 调色搭配</li>
</ul>

<p><a href="http://ljinkai.github.io/2015/06/06/mobile-web-skill/">查看链接</a></p>

<p>个人博客： <a href="http://ljinkai.github.io/">http://ljinkai.github.io/</a></p>