



### android笔记

## 第一章

> * 1、Log.d( )的用法：Log.g( )方法中传入两个参数：第一个参数是tag，主要用于对打印信息进行过滤；第二个参数是mag，即想要打印的具体内容。

> * 2、Toast的用法：Toast通过静态方法makeText( )创建出一个Toast对象，然后调用show( )将Toast显示出来就可以了，makeText( )方法需要传入三个参数。第一个参数是Context，也就是Toast要求的上下文，由于活动本身就是一个Context对象，因此这里直接传入当前类名.this即可。第二个参数是Toast显示的文本内容，第三个参数是Toast显示的时长，有两个内置常量可以选择Toast.LENGTH_SHORT和Toast.LENGTH_LONG。

> * 3、在活动中使用Menu:    
>
>   ```java
>   public boolean onCreateOptionsMenu(Menu menu){
>     getMenuInflater().inflate();
>     return true;
>   }
>   ```
>
>   ```java
>   public boolean onOptionsItemSelected(MenuItem item){
>     switch(item.getItemId()){
>       case :
>         break;
>       default:
>     }
>     return true; 
>   }
>   ```

> * 4、Activity类提供了一个finish()方法，我们在活动中调用一下这个方法就可以销毁当前活动。

> * 5、Intent是Android程序中各组件之间进行交互的一种重要方式，它不仅可以指明当前组件想要执行的动作，还可以在不同组件之间传递数据。Intent一般可被用于启动活动、启动服务以及发送广播等场景。
>
> * > * Intent大致可以分为两种：显示Intent和隐式Intent。
>
>   ​