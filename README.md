#flex scss

##flex版本说明

因为flex经历了大概三个版本的变化才发展至今，这里我们把三大版本按照时间的顺序分为old，middle和现在的标准版。

old版本常见于移动端浏览器，所以只需添加webkit前缀即可，middle版本出现在ie10浏览器中，只需添加ms前缀即可，而标准版本则需要添加webkit和moz前缀。

关于三大版本对比的详细资料可参考：

英文版 - [Designing CSS Layouts With Flexbox Is As Easy As Pie](http://coding.smashingmagazine.com/2013/05/22/centering-elements-with-flexbox/)

中文版 - [Flexbox制作CSS布局易如反掌 ](http://www.w3cplus.com/css3/designing-css-layout-with-flexbox.html)

关于标准版本的详细资料可参考：

英文版 - [Dive into Flexbox](http://weblog.bocoup.com/dive-into-flexbox/)

中文版 - [深入了解 Flexbox 伸缩盒模型](深入了解 Flexbox 伸缩盒模型 )

##使用方法

通过`$flexOld`和`$flexMid`变量来控制是否支持old版本和middle版本。默认为`true`都支持，如果不需要支持，直接覆写为`false`即可。

###说明

* old版本不支持的有：align-content和align-self两个属性，flex-wrap取值为wrap-reverse，justify-content取值为space-around
* old版本和middle版本都不支持flex-flow(flex-wrap和flex-direction的缩写)
* 最后关于伸缩性flex的定义不一样，如只传一个数字单位则可以达到三种语法一致，其余的则不可。

###调用方法

	// display:flex
	// flex | inline-flex
	@include display-flex();  
	
	// flex-direction
	// row | row-reverse | column | column-reverse
	@include flex-direction();
	
	// flex-wrap
	// nowrap | wrap | wrap-reverse
	// old版本不支持wrap-reverse
	@include flex-wrap();
	
	// flex-flow
	// flex-direction || flex-wrap
	@include flex-flow();
	
	// order
	// number
	@include order();
	
	// justify-content
	// flex-start | flex-end | center | space-between | space-around
	@include justify-content();
	
	// align-items
	// flex-start | flex-end | center | baseline | stretch
	@include align-items();
	
	// align-content
	// stretch | flex-start | flex-end | center | space-between | space-around
	// old不支持
	@include align-content();
	
	// align-self
	// auto | flex-start | flex-end | center | baseline | stretch
	// old不支持
	@include align-self();
	
	// flex
	// initial | auto | none | number
	// 只传入数字则三大版本都支持
	@include flex();