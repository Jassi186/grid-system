栅格系统英文名为Grid Systems,(又称为网格系统)。
定义：运用固定的格子，遵循一定的规则，进行页面的布局设计，使布局规范简洁有规则。
栅格系统的工作原理：
栅格系统用于通过一系列的行（row）与列（column）的组合来创建页面布局，内容可放入这些建好的布局中。
工作原理如下：
“行（row）”必须包含在 .container （固定宽度）或 .container-fluid （100% 宽度）中，以便为其赋予合适的排列（aligment）和内补（padding）。
<div class="container"><!-- 水平居中，两边有margin，最小屏幕时，充满父元素 -->
 <div class="row"></div>
</div>
<!-- 或者 -->
<div class="container-fluid"><!-- 默认一直充满整个父元素 -->
 <div class="row"></div>
</div>
通过“行（row）”在水平方向创建一组“列（column）”。但列数之和不能超过平分的总列数（在超过时，多余部分会换行显示），默认12。（使用Less或者Sass可以进行自定义设置）,如下：
<div class="container">
 <div class="row">
  <div class="col-md-2"></div>
  <div class="col-md-6"></div>
  <div class="col-md-4"></div>
 </div>
</div>
你的内容应当放置于“列（column）”内，并且，只有“列（column）”可以作为行（row）”的直接子元素。
类似 .row 和 .col-xs-4 这种预定义的类，可以用来快速创建栅格布局。Bootstrap 源码中定义的 mixin 也可以用来创建语义化的布局。
通过为“列（column）”设置 padding 属性，从而创建列与列之间的间隔（gutter）。通过为 .row 元素设置负值 margin 从而抵消掉为 .container 元素设置的 padding，也就间接为“行（row）”所包含的“列（column）”抵消掉了padding。
负值的 margin就是下面的示例为什么是向外突出的原因。在栅格列中的内容排成一行。
栅格系统中的列是通过指定1到12的值来表示其跨越的范围。例如，三个等宽的列可以使用三个 .col-xs-4 来创建。
如果一“行（row）”中包含了的“列（column）”大于 12，多余的“列（column）”所在的元素将被作为一个整体另起一行排列。
栅格类适用于与屏幕宽度大于或等于分界点大小的设备 ， 并且针对小屏幕设备覆盖栅格类。 因此，在元素上应用任何 .col-md-*栅格类适用于与屏幕宽度大于或等于分界点大小的设备 ， 并且针对小屏幕设备覆盖栅格类。 因此，在元素上应用任何 .col-lg-*不存在， 也影响大屏幕设备。
2.1媒体查询
 在栅格系统中，我们在 Less 文件中使用以下媒体查询（media query）来创建关键的分界点阈值。
/* 超小屏幕（手机，小于 768px） */
/* 没有任何媒体查询相关的代码，因为这在 Bootstrap 中是默认的（还记得 Bootstrap 是移动设备优先的吗？） */
/* 小屏幕（平板，大于等于 768px） */
@media (min-width: @screen-sm-min) { ... }
/* 中等屏幕（桌面显示器，大于等于 992px） */
@media (min-width: @screen-md-min) { ... }
/* 大屏幕（大桌面显示器，大于等于 1200px） */
@media (min-width: @screen-lg-min) { ... }
 我们偶尔也会在媒体查询代码中包含 max-width 从而将 CSS 的影响限制在更小范围的屏幕大小之内。
@media (max-width: @screen-xs-max) { ... }
@media (min-width: @screen-sm-min) and (max-width: @screen-sm-max) { ... }
@media (min-width: @screen-md-min) and (max-width: @screen-md-max) { ... }
@media (min-width: @screen-lg-min) { ... }
