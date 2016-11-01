# jQuery-pageSwitch-plugin
a simply jQuery plugin like fullpage

一 jquery插件开发的种类
1 给jquery命名下添加新的全局函数，静态方法
jQuery.myPlugin=function(){
	
};
2 对象级别 创建实例调用
$.fn.myPlugin=function(){
	
};

3 选择器插件

二 基本原则：
命名规范：jquery.[插件名].js
this.each遍历所有元素。
插件内部的this志向jquery对象。
所有插件应当以分号结尾，稳妥起见，在插件头部添加分号，避免他人的不规范代码给插件带来影响。
插件应该返回jquery对象，实现链式调用。
使用闭包，以便在插件内部继续使用$


三 基本结构：
;(function($){
   
  function MyPlugin(el,options){
 
  }
  $.fn.extend({
	 myPlugin :function(options){
       //直接写插件代码
       return this;
	 }
  })   
   //r如果需要传递默认参数，直接添加到fn上，不用extend方法扩展
   $.fn.myPlugin =  function (options){
       return this.each(function(){
          new myPlugin($(this),options)
       })
   }	
})(jQuery);
