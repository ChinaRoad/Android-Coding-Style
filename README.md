#Android代码规范
##目录
* [介绍](#介绍)
    * 为什么需要编码规范?
* [命名](#命名)
    * 包命名
    * 类和接口命名
    * 方法的命名
    * 控件全局变量命名
    * 非控件全局变量命名
    * 临时变量命名
    * 成员变量命名
    * 方法形参命名
    * 常量命名
    * 异常命名
    * layout命名
    * id命名
    * 资源命名
* [注释](#注释)
    * 文件注释
    * 类注释
    * 方法注释
    * 类成员变量和常量注释
    * xml注释
    * 其它注释
* [代码风格](#代码风格)
    * 缩进
    * 空行
    * 行宽
* [规约](#规约)
    * 方法
    * 参数返回值
    * 神秘的数
    * 控制语句
    * 异常的捕捉处理
    * 访问控制
* [Eclipse配置方法](#Eclipse配置方法)
    * 导入方法
    * 格式化模板
* [附录](#附录)
    * 量词列表：量词后缀说明
    * 动画文件
    * layout中id命名缩写表
    * 建议
    * 常见英文缩写

##介绍
  * 编码规范对于程序员而言尤为重要，有以下几个原因： 
    * 一个软件的生命周期中，80%的花费在于维护 
    * 几乎没有任何一个软件，在其整个生命周期中，均由最初的开发人员来维护
    * 编码规范可以改善软件的可读性，可以让程序员尽快而彻底地理解新的代码
    * 如果你将源码作为产品发布，就需要确任它是否被很好的打包并且清晰无误

##命名
  * 包命名
    
    命名规则：一个唯一包名的前缀总是全部小写的ASCII 字母并且是一个顶级域名，通常是com，edu，gov，net，org。包名的后续部分根据不同机构各自内部的命名规范而不尽相同。这类命名规范可能以特定目录名的组成来区分项目(project)，或注册名(login names)。
    例如： com.llt.pp.activities
    
    <font color=red>规约：包命名必须以com.llt开始，后面跟有项目名称（或者缩写）,再后面为模块名或层级名称。如：com.llt.项目缩写.模块名  com.llt.pp.user如：com.llt.项目缩写.层级名 com.llt.pp.activities</font>


  * 类和接口命名
    
    命名规则：类名是个一名词，采用大小写混合的方式，每个单词的首字母大写。尽量使你的类名简洁而富于描述。使用完整单词，避免缩写词(除非该缩写词被更广泛使用，像 URL，HTML)  
    接口一般要使用able、ible、er 等后缀
    
    例如：
    ```java
    class Raster {
    }
    ```
    
    <font color=red>规约：类名必须使用驼峰规则，即首字母必须大写，如果为词组，则每个单词的首字母也必须要大写，类名必须使用名词，或名词词组。要求类名简单，不允许出现无意义的单词（如 class XXXActivity）。如：class BookMarkAdd 正确如：class AddBookReadPlanActivity  错误！ 应为 class BookReadPlanAdd</font>


  * 方法的命名
    
    命名规则：方法名是一个动词，采用大小写混合的方式，第一个单词的首字母小写，其后单词的首字母大写。
    
    例如：
    ```java
    public void run() {
        ...
    }

    public void getBookName() {
        ...
    }
    ```
    
    类中常用方法的命名：
    * 类的获取方法（一般具有返回值）一般要求在被访问的字段名前加上get，如getFirstName()，getLastName()。一般来说，get前缀方法返回的是单个值，find前缀的方法返回的是列表值。
    * 类的设置方法（一般返回类型为void）：被访问字段名的前面加上前缀 set，如setFirstName(),setLastName().
    * 类的布尔型的判断方法一般要求方法名使用单词 is或has 做前缀，如isPersistent()，isString()。或者使用具有逻辑意义的单词，例如equal 或equals。
    * 类的普通方法一般采用完整的英文描述说明成员方法功能，第一个单词尽可能采用动词，首字母小写，如openFile()，addCount()。
    * 构造方法应该用递增的方式写。（参数多的写在后面）
    * toString()方法：一般情况下，每个类都应该定义toString()
    
     
  * 控件全局变量命名
    
    命名规则：以m开头，如果本身就是以m开头，则不需要，再加上控件类型缩写，在加上功能，m后面的单词全部首字母大写，例如mBtnLogin, mImgAvaar

  * 非控件全局变量命名
   
    命名规则：以m开头, 如果本身就是以m开头，则不需要，加上功能， 再m后面的单词全部首字母大写，如果是一个集合，在加上集合的缩写，例如 mBookName mBookList
    
  * 临时变量命名
  
    命名规则：临时变量通常被取名为 i，j，k，m 和 n，它们一般用于整型；c，d，e，它们一般用于字符型。

    例如：
    ```java
    void fun() {
        for(int i=0; i++; i<10) {
            ...
        }
    }
    ```
 
  * 成员变量命名
  
    命名规则：以"_"开头，其它规则和全局变量一样，例如fun(){String _UserName; int _DoorNo}
    
    例如：
    ```java
    void fun() {
        String _UserName;
        int _DoorNo;
    }
    ```

  * 方法形参命名
    
    命名规则：以p开关，其它规则和全局变量一样，如果单词本身就是以p开头，则不需要
    
    例如：
    ```java
    void fun(String pName, String park) {
        ...
    }
    //常用方法名称
    void initXX(); //初始化相关方法,使用init为前缀标识，如初始化布局initView()
    void checkXX(); //做判断返回值为boolean型的请使用is或check为前缀标识
    void getXX(); //返回某个值的方法，使用get为前缀标识
    void processXX(); //对数据进行处理的方法，尽量使用process为前缀标识
    void displayXX(); //弹出提示框和提示信息，使用display为前缀标识
    void saveXX(); //与保存数据相关的，使用sav为e前缀标识
    void resetXX(); //对数据重组的，使用reset前缀标识
    void clearXX(); //清除数据相关的
    void removeXXX(); //清除数据相关的
    void drawXXX(); //绘制数据或效果相关的，使用draw前缀标识
    ```

  * 常量命名
    
    命名规则：类常量的声明，应该全部大写，单词间用下划线隔开。
    例如：
    ```java
    class MyImageView {
        static final int MIN_WIDTH = 4; 
        static final int MAX_WIDTH = 999;   
    }
    ```

  * 异常命名
    
    <font color=red>规约：自定义异常的命名必须以Exception为结尾。已明确标示为一个异常。</font>


  * layout命名
    
    <font color=red>规约：layout xml 的命名必须以 全部单词小写，单词间以下划线分割，并且使用名词或名词词组，即使用 项目名缩写_模块名_功能名称 来命名。如：pp_act_main.xml正确 main.xml错误！</font>

 
  * id命名
    
    <font color=red>规约：规约：layout 中所使用的id必须以全部单词小写，单词间以下划线分割，并且使用名词或名词词组，即使用 控件名_功能名称，并且要求能够通过id直接理解当前组件要实现的功能。如：某TextView @+id/tv_bookName </font>


  * 资源命名
    
     <font color=red>规约：layout中所使用的所有资源（如drawable,style等）命名必须以全部单词小写，单词间以下划线分割，并且尽可能的使用名词或名词组，即使用 模块名_用途 来命名。如果为公共资源，如分割线等，则直接用用途来命名act_divider.png</font>

##注释

  Java 程序有两类注释：实现注释(implementation comments)和文档注释(document comments)。实现注释是使用/*...*/和//界定的注释。文档注释(被称为"doc comments")由/**...*/界定。文档注释可以通过javadoc 工具转换成HTML 文件。
  
  * 文件注释
    所有的源文件都应该在开头有一个注释，其中列出类名、版本信息、日期和版权声明。
    如下：
    ```xml
     /**
      * 文件名 
      * 包含类名列表
      * 版本信息，版本号
      * 创建日期。
      * 版权声明
      */
    ```

  * 类注释
  
    每一个类都要包含如下格式的注释，以说明当前类的功能等。
    如下：
    ```xml
     /**
      * 类名
      * @author 作者
      * 实现的主要功能
      * 创建日期
      * 修改者，修改日期，修改内容。
      */
    ```

  * 方法注释
  
    每一个方法都要包含 如下格式的注释 包括当前方法的用途，当前方法参数的含义，当前方法返回值的内容和抛出异常的列表。
    如下：
    ```xml
     /**
      * 
    * 方法的一句话概述
    * 方法详述（简单方法可不必详述）
    * @param s 说明参数含义
    * @return 说明返回值含义
    * @throws IOException 说明发生此异常的条件
    * @throws NullPointerException 说明发生此异常的条件
    */
    ```

  * 类成员变量和常量注释
  
    成员变量和常量需要使用java doc形式的注释，以说明当前变量或常量的含义
    如下：
    ```xml
     /**
      * XXXX含义
      */
    ```

  * XML注释
  
    <font color=red>规约：如果当前layout 或资源需要被多处调用，或为公共使用的layout（若list_item），则需要在xml写明注释。要求注释清晰易懂。</font>

##代码风格

  * 缩进
  
   <font color=red>规约：不允许使用Tab进行缩进，使用空格进行缩进，推荐缩进为2空格。</font>


  * 空行
   
   空行将逻辑相关的代码段分隔开，以提高可读性。 下列情况应该总是使用空行： 

    * 一个源文件的两个片段(section)之间
    * 类声明和接口声明之间
    * 两个方法之间
    * 方法内的局部变量和方法的第一条语句之间
    * 一个方法内的两个逻辑段之间，用以提高可读性 
    
    <font color=red>规约：通常在 变量声明区域之后要用空行分隔，常量声明区域之后要有空行 分隔，方法声明之前要有空行分隔。</font>
    
  * 行宽
    
    无特别规定，因为现在的显示器都比较大，所以推荐使用120进行设置。

##规约
  * 方法
    * 一个方法尽量不要超过15行，如果方法太长，说明当前方法业务逻辑已经非常复杂，那么就需要进行方法拆分，保证每个方法只作一件事。
    * <font color=red>不要使用 try catch 处理业务逻辑！！！</font>
    * 
  * 参数和返回值
    * 一个方法的参数尽可能的不要超过4个！
    * 如果一个方法返回的是一个错误码，请使用异常！！
    * 尽可能不要使用null， 替代为异常 或者使用空变量 如返回 List 则可以使用Collections.emptyList()
    * 
  * 神秘的数
    代码中不允许出现单独的数字，字符！如果需要使用数字或字符，则将它们按照含义封装为静态常量！（for语句中除外）
    
  * 控制语句
    * 判断中如有常量，则应将常量置于判断式的右侧。如：
        ```java
        if (true == isAdmin())...
        ```
    * 尽量不使用三目条件的嵌套。
    * 所有if 语句必须用{}包括起来,即便是只有一句：
      ```java
        if (true){
            //do something......
        }
        if (true)
            i = 0; //不要使用这种
      ```
    * 对于循环：
      ```java
        //不推荐方式____________________________________________
        while(index < products.getCount()){
          //每此都会执行一次getCount()方法，
        //若此方法耗时则会影响执行效率
        //而且可能带来同步问题，若有同步需求，请使用同步块或同步方法
        }
        //推荐方式______________________________________________
        //将操作结构保存在临时变量里，减少方法调用次数
        final int count = products.getCount();
           while(index < count){
        }
      ``` 
    * 异常的捕捉处理
      * 通常的思想是只对错误采用异常处理：逻辑和编程错误，设置错误，被破坏的数据，资源耗尽，等等。
      * 通常的法则是系统在正常状态下以及无重载和硬件失效状态下，不应产生任何异常。
      * 最小化从一个给定的抽象类中导出的异常的个数。对于经常发生的可预计事件不要采用异常。不要使用异常实现控制结构。
      * 若有finally 子句，则不要在try 块中直接返回，亦不要在finally 中直接返回。

  * 控制语句
     
      * 若没有足够理由，不要把实例或类变量声明为公有。通常，实例变量无需显式的设置(set)和获取(gotten)，通常这作为方法调用的边缘效应 (side effect)而产生。  
      
      * 一个具有公有实例变量的恰当例子，是类仅作为数据结构，没有行为。亦即，若你要使用一个结构(struct)而非一个类(如果java 支持结构的话)，那么把类的实例变量声明为公有是合适的。


##Eclipse配置方法
  
  * 导入方法
  
  在eclipse 的preferences 中，选择 java->code style->code Template 中选择 Import，选择codetemplates.xml
   
  <font color=red>但是注意修改 类注释 和 文件注释 的作者名称为自己的！</font>

  * 格式化模板
  在eclipse 的preferences 中，选择 java->code style->formatter 中选择 Import，选择formatter.xml  


##PS
  * 量词列表：量词后缀说明
 
    * First  一组变量中的第一个
    * Last   一组变量中的最后一个
    * Next   一组变量中的下一个变量
    * Prev   一组变量中的上一个
    * Cur    一组变量中的当前变量
 

  * 动画文件
  
    * fade_in：淡入
    * fade_out：淡出
    * push_down_in：从下方推入
    * push_down_out：从下方推出
    * push_left：推向左方
    * push_right：推向右方
    * slide_in_from_top：从头部滑动进入
    * zoom_enter：变形进入
    * slide_in：滑动进入
    * shring_to_middle：中间缩小

  * layout中id命名缩写表
    
    * LinearLayout：ll
    * RelativeLayout：rl
    * TextView：txtView
    * Button：btn
    * ImageButton：imgBtn
    * ImageView：imgView
    * CheckBox：chk
    * RadioButton：rdoBtn
    * DatePicker：dtPk
    * EdtText：edtTxt
    * TimePicker：tmPk
    * ProgressBar：proBar
    * SeekBar：skBar
    * AutoCompleteTextView：autoTxt
    * ZoomControls：zmCtl
    * VideoView：vdoView
    * RantingBar：ratBar
    * Tab：tab
    * Spinner：spn
    * ScrollView：sclVi
    * TextSwitch：txtSwt
    * ImageSwitch：imgSwt
    * ListView：lV
    * ExpandableList：epdLt
    * MapView：mapView;

  * 建议
    * java代码中不出现中文，最多注释中可以出现中文
    * 局部变量命名、静态成员变量命名
    * 只能包含字母，单词首字母除第一个外，都为大写，其他字母都为小写
    * 常量命名只能包含字母和_，字母全部大写，单词之间用_隔开
    * 图片尽量分拆成多个可重用的图片
    * 服务端可以实现的，就不要放在客户端
    * 引用第三方库要慎重，避免应用大容量的第三方库，导致客户端包非常大
    * 处理应用全局异常和错误，将错误以邮件的形式发送给服务端
    * 图片的.9处理
    * 使用静态变量方式实现界面间共享要慎重
    * Log(系统名称模块名称接口名称，详细描述)
    * 单元测试（逻辑测试、界面测试）
    * 不要重用父类的handler，对应一个类的handler也不应该让其子类用到，否则会导致message.what冲突
    * activity中在一个View.OnClickListener中处理所有的逻辑
    * strings.xml中使用%1$s实现字符串的通配如果多个Activity中包含共同的UI处理，那么可以提炼一个CommonActivity，把通用部分叫由它来处理，其他activity只要继承它即可
    * 如果所开发的为通用组件，为避免冲突，将drawable/layout/menu/values目录下的文件名增加前缀
    * 数据一定要效验，例如“字符型转数字型，如果转换失败一定要有缺省值、服务端响应数据是否有效判断
    
  * 常见英文缩写
    
    * icon：ic(主要用于app图标)
    * color：cl(主要用于颜色值)
    * divider：di(主要用于分割线，不仅包括ListView中的divider，还包括普通布局中的线)
    * selector：sl(主要用于某一View多种状态，包括ListView和按钮的selector)
    * background：bg(主要用于布局和子布局的背景)
    * buffer：buf
    * control：ctrl
    * delete：del
    * document：doc
    * error：err
    * increment：inc
    * length：len
    * library：lib
    * message：msg
    * password：pwd
    * position：pos
    * server：srv
    * string：str
    * temp：tmp
    * window：win






