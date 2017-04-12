

# android笔记

## 第一章

1. 1、Log.d( )的用法：Log.g( )方法中传入两个参数：第一个参数是tag，主要用于对打印信息进行过滤；第二个参数是mag，即想要打印的具体内容。
2. 2、Toast的用法：Toast通过静态方法makeText( )创建出一个Toast对象，然后调用show( )将Toast显示出来就可以了，makeText( )方法需要传入三个参数。第一个参数是Context，也就是Toast要求的上下文，由于活动本身就是一个Context对象，因此这里直接传入当前类名.this即可。第二个参数是Toast显示的文本内容，第三个参数是Toast显示的时长，有两个内置常量可以选择Toast.LENGTH_SHORT和Toast.LENGTH_LONG。
3. 3、在活动中使用Menu： 

​              public boolean onCreateOptionsMenu(Menu menu){

​      	      		getMenuInflater().inflate();

​      			return true;

​     		}



   		public boolean onOptionsItemSelected(MenuItem item){

​	     		switch(item.getItemId()){

​	   		 case                :

​                         	break;

​           		 default:

​           		 }

​           		 return true;
