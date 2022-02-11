
# **开始angular**

&emsp;<img src="https://avatars.githubusercontent.com/u/139426?s=200&v=4"  height="50" width="50">

<font face="Meiryo UI" size="5" color=#BC8F8F>
 Angular
</font>  

##  
&ensp; https://github.com/angular 

<br/>

## <font face="Meiryo UI" size="4" color=#00008B> 
**Angular项目结构**
</font>  

### **Angular项目目录结构详解**  
https://blog.csdn.net/yuzhiqiang_1993/article/details/71191873

<br/>

<font face="Meiryo UI" size="2" color=#696969>
**首先看一下整体的目录结构**  
</font>

&emsp;<img src="https://github.com/jinnicn/imgdelivery/blob/main/delivery-md/1.png?raw=true" height="450" width="220">

<font face="Meiryo UI" size="2" color=#696969>
首层目录：
</font>

``` bash
#第三方依赖包存放目录
node_modules
#端到端的测试目录  用来做自动测试的
e2e
#应用源代码目录  
src	
#Angular命令行工具的配置文件。后期可能会去修改它，引一些其他的第三方的包  比如jquery等
.angular-cli.json
#karma是单元测试的执行器，karma.conf.js是karma的配置文件
karma.conf.js
#这是一个标准的npm工具的配置文件，这个文件里面列出了该应用程序所使用的第三方依赖包。实际上我们在新建项目的时候，等了半天就是在下载第三方依赖包。下载完成后会放在node_modules这个目录中，后期我们可能会修改这个文件。
package.json
#也是一个做自动化测试的配置文件
protractor.conf.js
#说明文件
README.md
#是tslint的配置文件，用来定义TypeScript代码质量检查的规则，不用管它
tslint.json
``` 

<font face="Meiryo UI" size="2" color=#696969>
src目录：
</font>

``` bash
#包含应用的组件和模块，我们要写的代码都在这个目录
app目录
#资源目录，存储静态资源的  比如图片
assets目录
#环境配置。Angular是支持多环境开发的，我们可以在不同的环境下（开发环境，测试环境，生产环境）共用一套代码，主要用来配置环境的
environments目录
#整个应用的根html，程序启动就是访问这个页面
index.html
#整个项目的入口点，Angular通过这个文件来启动项目
main.ts
#主要是用来导入一些必要库，为了让Angular能正常运行在老版本下	
polyfills.ts
#主要是放一些全局的样式
styles.css
#TypeScript编译器的配置,添加第三方依赖的时候会修改这个文件
tsconfig.app.json
#不用管
tsconfig.spec.json
#也是自动化测试用的
test.ts
#不用管
typings.d.ts
``` 

<font face="Meiryo UI" size="2" color=#696969>
app目录（重点）
</font>

app目录是我们要编写的代码目录。我们写的代码都是放在这个目录。  
一个Angular程序至少需要一个模块和一个组件。  
在我们新建项目的时候命令行已经默认生成出来了。

&emsp;<img src="https://github.com/jinnicn/imgdelivery/blob/main/delivery-md/2.png?raw=true">

```app.component.ts```  
这个文件表示组件，  
组件是```Angular```应用的基本构建模块，可以理解为一段带有业务逻辑和数据的```Html```。  
我们来看看```app.component.ts```中的代码，并解释下代码的意义

```ts
/*这里是从Angular核心模块里面引入了component装饰器*/
import {Component} from '@angular/core';

/*用装饰器定义了一个组件以及组件的元数据  所有的组件都必须使用这个装饰器来注解*/
@Component({
  /*组件元数据  Angular会通过这里面的属性来渲染组件并执行逻辑
  * selector就是css选择器，表示这个组件可以通过app-root来调用，index.html中有个<app-root>Loading...</app-root>标签，这个标签用来展示该组件的内容
  *templateUrl  组件的模板，定义了组件的布局和内容
  *styleUrls   该模板引用那个css样式
  * */
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
/*AppComponent本来就是一个普通的typescript类，但是上面的组件元数据装饰器告诉Angular，AppComponent是一个组件，需要把一些元数据附加到这个类上，Angular就会把AppComponent当组件来处理*/
export class AppComponent {
  /*这个类实际上就是该组件的控制器，我们的业务逻辑就是在这个类中编写*/
  title = '学习Angular';
}
```
<font face="Meiryo UI" size="2" color=#696969>
组件相关的概念：
</font>  

**1.组件元数据装饰器（@Component）**  
简称组件装饰器，用来告知Angular框架如何处理一个TypeScript类.
Component装饰器包含多个属性，这些属性的值叫做元数据，Angular会根据这些元数据的值来渲染组件并执行组件的逻辑

**2.模板（Template）**  
我们可以通过组件自带的模板来定义组件的外观，模板以html的形式存在，告诉Angular如何来渲染组件，一般来说，模板看起来很像html，但是我们可以在模板中使用Angular的数据绑定语法，来呈现控制器中的数据。

**3.控制器（controller）**  
控制器就是一个普通的typescript类，他会被@Component来装饰，控制器会包含组件所有的属性和方法，绝大多数的业务逻辑都是写在控制器里的。控制器通过数据绑定与模板来通讯，模板展现控制器的数据，控制器处理模板上发生的事件

装饰器，模板和控制器是组件的必备要素。还有一些可选的元素，比如：

* **输入属性（@inputs）**  
是用来接收外部传入的数据的,Angular的程序结构就是一个组件树，输入属性允许在组件树种传递数据

* **提供器（providers）：**  
这个是用来做依赖注入的

* **生命周期钩子（LifeCycle Hooks）：**  
一个组件从创建到销毁的过程中会有多个钩子会被触发，类似于Android中的Activity的生命周期

* **样式表：**
组件可以关联一些样式表

* **动画（Animations）：**
Angular提供了一个动画包来帮助我们方便的创建一些跟组件相关的动画效果，比如淡入淡出等

* **输出属性（@Outputs）：**
用来定义一些其他组件可能需要的事件或者用来在组件之间共享数据

简单来说，组件的中关系就如下图所示

&emsp;<img src="https://github.com/jinnicn/imgdelivery/blob/main/delivery-md/3.png?raw=true" height="250" width="600">

<br/>

下面我们来看看模块文件
```app.module.ts```：  
这个文件表示模块。与AppComponent类似，模块也需要装饰器来装饰。
&emsp;<img src="https://github.com/jinnicn/imgdelivery/blob/main/delivery-md/4.png?raw=true" height="470" width="450">

<br/>

<font face="Meiryo UI" size="2" color=#696969>
新项目的目录结构就是这样!
</font>  

#
<br/>



