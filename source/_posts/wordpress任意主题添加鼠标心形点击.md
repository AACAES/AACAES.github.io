---
title: wordpress任意主题添加鼠标心形点击
date: 2017-05-27 14:41:40
tags:
---
这个似乎教程也不少？我看到的是针对hexo架构Next主题的教程，几乎教程都是针对某些特定的主题，其实这个方法对于wordpress也可以，另外任何主题都行。
操作步骤如下：





1. ### 新建.js 
在`/home/wwwroot/www.applecaes.xyz/wp-content/themes/flat/assets/js/`目录下新建love.js（只要是.js即可，名字随便起），代码如下：

    `  !function(e,t,a){function n(){c(".heart{width: 10px;height: 10px;position: fixed;background: #f00;transform: rotate(45deg);-webkit-transform: rotate(45deg);-moz-transform: rotate(45deg);}.heart:after,.heart:before{content: '';width: inherit;height: inherit;background: inherit;border-radius: 50%;-webkit-border-radius: 50%;-moz-border-radius: 50%;position: fixed;}.heart:after{top: -5px;}.heart:before{left: -5px;}"),o(),r()}function r(){for(var e=0;e<d.length;e++)d[e].alpha<=0?(t.body.removeChild(d[e].el),d.splice(e,1)):(d[e].y--,d[e].scale+=.004,d[e].alpha-=.013,d[e].el.style.cssText="left:"+d[e].x+"px;top:"+d[e].y+"px;opacity:"+d[e].alpha+";transform:scale("+d[e].scale+","+d[e].scale+") rotate(45deg);background:"+d[e].color+";z-index:99999");requestAnimationFrame(r)}function o(){var t="function"==typeof e.onclick&&e.onclick;e.onclick=function(e){t&&t(),i(e)}}function i(e){var a=t.createElement("div");a.className="heart",d.push({el:a,x:e.clientX-5,y:e.clientY-5,scale:1,alpha:1,color:s()}),t.body.appendChild(a)}function c(e){var a=t.createElement("style");a.type="text/css";try{a.appendChild(t.createTextNode(e))}catch(t){a.styleSheet.cssText=e}t.getElementsByTagName("head")[0].appendChild(a)}function s(){return"rgb("+~~(255*Math.random())+","+~~(255*Math.random())+","+~~(255*Math.random())+")"}var d=[];e.requestAnimationFrame=function(){return e.requestAnimationFrame||e.webkitRequestAnimationFrame||e.mozRequestAnimationFrame||e.oRequestAnimationFrame||e.msRequestAnimationFrame||function(e){setTimeout(e,1e3/60)}}(),n()}(window,document);`

2. ### Wordpress操作
wordpress在/home/wwwroot/www.applecaes.xyz/wp-content/themes/flat/footer.php 文件的最下方，添加

    `<script src="http://www.applecaes.xyz/wp-content/themes/flat/assets/js/love.js"></script>`

    enjoy!




3. ### hexo操作
hexo在Blog\themes\next\layout\_layout.swig文件的最下方，```</body>```前面添加


    `<script type="text/javascript" src="/js/src/love.js"></script>`

	enjoy!