



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
>   > Intent大致可以分为两种：显示Intent和隐式Intent。
>
>   ​

> * 6、Activity中有一个startActivityForResult()方法也用于启动活动，但是这个方法期望这活动销毁的时候能够返回一个结果给上一个活动。startActivityForResult()方法接收两个参数，一个参数还是intent，第二个参数是请求码，用于在之后的回调中判断数据来源。
>
>   > setResult()方法是专门向上一个活动返回数据的，该方法接收两个参数，第一个参数用于向上一个活动处理返回结果，一般只使用RESULT_OK或RESULT_CANCELED这两个值，第二个参数则把带有数据的intent传递回去。
>   >
>   > 如果我们是使用startActivityForResult()方法来启动活动的，在活动被销毁之后会回调上一个活动的onActivityResult()方法。
>   >
>   > 按下back键调用的方法：
>   >
>   > ```java
>   > @Override
>   > public void onBackPressed(){
>   >   
>   > }
>   > ```
>   >
>   > ​

> * 7、Activity中有一个onSaveInstanceState()回调方法，这个方法可以保证在活动被回收之前一定会被调用，因此我们可以通过这个方法来解决活动被回收时临时数据得不到保存的问题。
>
>   onSaveInstanceState()方法会携带一个Bundle类型的参数，Bundle提供了一系列的方法用于储存数据，比如可以使用putString()方法保存字符串，使用putIntent()方法保存整形数据，以此类推。每个保存方法需要传入两个参数，一个参数是键，用于后面从Bundle中取值，第二个参数是真正要保存的内容，例如：
>
>   ```java
>   @Override
>   protected void onSaveInstanceState(Bundle outState){
>     super.onSaveInstanceState(outState);
>     String tempData = "something you just typed";
>     outState.putString("data_key", tempData);
>   }
>   ```
>
>   ​

## 常用控件的使用

> * 1、TextView
>
>   > 我们使用android:gravity来指定文字的对齐方式，可选值有top、bottom、left、right、center等，可以用“|”来同时指定多个值，指定center效果等同于center_vertical|center_horizontal,表示文字在垂直和水平方向都居中对齐。
>   >
>   > 通过android：textSize属性指定文字的大小，通过android：textColor属性可以指定文字的颜色，在android中文字字体大小用sp作为单位。

> * 2、Button
>
>   > 系统对Button中的所有英文字母自动进行大写转换，如果这不是你想要的效果，可以使用android：textAllCaps="false"来禁用这一默认特性。

> * 3、EditText
>
>   > 我们使用android：hint属性来指定一段提示性文本，通过android：maxlines指定EditText的最大行数，这样当输入超过最大行数时，文本就会向上滚动，EditText则不会继续拉伸。

> * 4、ImageView
>
>   > ImageView是用于在界面上展示图片的一个控件，使用android：src属性给ImageView指定了一张图片。可以通过调用ImageView的setImageResource()方法更改ImageView显示的图片。

> * 5、ProgressBar
>
>   > ProgressBar用于在界面上显示一个进度条，表示我们的程序正在加载一些数据

> * 6、Android控件的可见属性，所有的Android控件都具有这个属性，可以通过android：visibility进行指定，可选值有3种：visible、invisible、和gone。visible表示控件是可见的，这个值是默认值，不指定android：visibility时，空间都是可见的，invisible表示控件不可见，但是它仍然占据着原来的位置和大小，可以理解成控件变成透明状态了，gone则表示空间不见不可见，而且不再占用任何屏幕空间，我们可以通过代码来设置控件的可见性，使用的是setVisibility()方法，可以传入View.VISIBLE、View.INVISIBLE和View.GONE这三种值。