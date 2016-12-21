# CoordinatorLayoutDemo
首先是android:fitsSystemWindows这个的用处,就是把Activity状态栏设置成透明模式。
然后在布局文件中，把CollapsingToolbarLayout里要实现沉浸式的控件设置上android:fitsSystemWindows="true"，
如果没有设置(默认为false)，则子布局会位于状态栏下方，未延伸至状态栏。
如图所示有个白色的空白（设置android:fitsSystemWindows="false"或者不设置）

然后就是layout_scrollFlags的属性，里面有五个参数scroll，enterAlways，enterAlwaysCollapsed，snap，exitUntilCollapsed。
参数的具体如下

scroll:所有想滚动出屏幕的view都需要设置这个flag，没有设置这个flag的view将被固定在屏幕顶部。比如说，TabLayout没有设置这个值，将会停留在屏幕顶部。

enterAlways:设置时，向下的滚动会导致该view变成可见，启用快速“返回模式”。

enterAlwaysCollapsed:当你的视图已经设置minHeight属性又使用此标志时，你的视图只能已最小高度进入,只有当滚动视图到达顶部时才扩大到完整高度。

exitUntilCollapsed:滚动退出屏幕，最后折叠在顶端。

sanp:子View的滑动效果的一个吸附效果，子View不会存在局部显示的情况，滚动子View的部分高度，当松开手指时，子View要么向上全部滚出屏幕，要么向下全部滚进屏幕。

最后就是layout_collapseMode的使用，子视图的折叠模式，在子视图设置，有两种方式
“pin”：固定模式，在折叠的时候最后固定在顶端；

“parallax”：视差模式，在折叠的时候会有个视差折叠的效果。

我们现在使用属性app:layout_collapseMode=”parallax”来改变的。

还有一个app:layout_behavior="@string/appbar_scrolling_view_behavior",

它就是指定Behavior的，appbar_scrolling_view_behavior对应的类的名称是：android.support.design.widget.AppBarLayout$ScrollingViewBehavior
