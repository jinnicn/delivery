
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

**<font face="Meiryo UI" size="2" color=#696969>
首先看一下整体的目录结构
</font>**

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


## <font face="Meiryo UI" size="4" color=#00008B> 
**Angular的启动过程**
</font>  

### **Angular的启动过程**  
https://yuzhiqiang.blog.csdn.net/article/details/71195141

**<font face="Meiryo UI" size="2" color=#696969>
首先看一下整体的目录结构
</font>**


**<font face="Meiryo UI" size="2" color=#696969> 
```main.ts```是整个Angular项目的入口点，那么，Angular项目的启动过程是怎样的呢？
</font>**


* <font face="Meiryo UI" size="2" color=#696969>1.启动时加载了哪个页面。 </font> 
* <font face="Meiryo UI" size="2" color=#696969>2.启动时执行了哪些脚本  </font>
* <font face="Meiryo UI" size="2" color=#696969>3.这些脚本都做了什么  </font>

首先我们看一下```angular-cli.json```(```angular.json```)这个文件，  
之前说到这个文件是命令行工具的配置文件。我们先来看看里面的代码

```ts
{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "project": {
    "name": "test"//项目名称
  },
  "apps": [
    {
      /*指向的是angular应用启动时从哪个目录找资源,默认指向src目录*/
      "root": "src",
      "outDir": "dist",
      /*资源目录*/
      "assets": [
        "assets",
        "favicon.ico"
      ],
      /* index指向Angular应用启动时加载的页面  默认指向src目录中index.html*/
      "index": "index.html",
      /* main属性指向Angular应用启动时加载的脚本  默认指向src目录中的main.ts*/
      "main": "main.ts",
      "polyfills": "polyfills.ts",
      "test": "test.ts",
      "tsconfig": "tsconfig.app.json",
      "testTsconfig": "tsconfig.spec.json",
      "prefix": "app",
      "styles": [
        "styles.css"
      ],
      "scripts": [
        "../node_modules/jquery/dist/jquery.js"
      ],
      "environmentSource": "environments/environment.ts",
      "environments": {
        "dev": "environments/environment.ts",
        "prod": "environments/environment.prod.ts"
      }
    }
  ],
  "e2e": {
    "protractor": {
      "config": "./protractor.conf.js"
    }
  },
  "lint": [
    {
      "project": "src/tsconfig.app.json"
    },
    {
      "project": "src/tsconfig.spec.json"
    },
    {
      "project": "e2e/tsconfig.e2e.json"
    }
  ],
  "test": {
    "karma": {
      "config": "./karma.conf.js"
    }
  },
  "defaults": {
    "styleExt": "css",
    "component": {}
  }
}
```

```root```属性指向的是```Angular```应用启动时从哪个目录找资源,默认指向```src```目录  
```index```指向```Angular```应用启动时加载的页面 默认指向```src```目录中```index.html```  
```main```属性指向```Angular```应用启动时加载的脚本 默认指向```src```目录中的```main.ts```

**<font face="Meiryo UI" size="2" color=#696969>
```main.ts```中的代码
</font>**

```ts
/*开发者模式的配置*/
import { enableProdMode } from '@angular/core';
/*告诉Angular使用哪个模块启动应用*/
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
/*导入主模块*/
import { AppModule } from './app/app.module';
/*倒入环境配置*/
import { environment } from './environments/environment';

/*如果是生产环境  关闭开发者模式*/
if (environment.production) {
  enableProdMode();
}

/*程序的起点，整个程序就是从这里运行的，AppModule指向的是/app/app.module，也就是说程序启动时会去加载/app/app.module这个文件*/
platformBrowserDynamic().bootstrapModule(AppModule);
```

```main.ts```告诉```Angular```主模块是```AppModule```,```Angular```也就知道了去加载```AppModule```。

#

**index.html**中的代码很简单，之前也说过<app-root></app-root> 这个标签就是组件展示的地方。

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>Test</title>
  <base href="/">

  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>
  <app-root>Loading...</app-root>
</body>
</html>
```

#

**下面就是Angular应用的启动过程**

1.Angular应用在启动时首先会去**angular.json**这个配置文件中去寻找要加载的页面和脚本。  
默认是加载**index.html**和**main.ts**
```ts
 "sourceRoot": "src",
 "index": "src/index.html",
 "main": "src/main.ts",
``` 

2.然后去**main.ts**中找到声明指定的主模块，默认的主模块是**app.module**
```ts
// 导入enableProdMode用来关闭angular开发者模式
import { enableProdMode } from '@angular/core';
// 负责从angular浏览器模块中导入platformBrowserDynamic这个方法，
// 这个方法告诉angular使用哪个模块来启动整个应用
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

// 整个应用的主模块
import { AppModule } from './app/app.module';//←主模块
// angular多环境支持
import { environment } from './environments/environment';

if (environment.production) {
  // 如果是工厂模式，就启动enableProdMode来关闭开发者模式
  enableProdMode();
}

// 调用bootstrapModule方法来传入AppModule作为启动模块来启动应用。
platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));
``` 

3.然后去**app.module**中找到指定的主组件，默认的主组件是**app.component**
```ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

import { AppRoutingModule } from './app-routing.module';
/* 导入模块的主组件 */
import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [],
  /* 声明模块的主组件 */
  bootstrap: [AppComponent]
})
export class AppModule { }
``` 

4.然后再去**app.component**中找到指定的选择器，模板和样式等等
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root', //←选择器
  templateUrl: './app.component.html',//←模板
  styleUrls: ['./app.component.sass']//←样式
})
export class AppComponent {
  title = 'angularDemo';
}
``` 
 
5.最后，将组件渲染到**index.html**中的选择器中
 ```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>Test</title>
  <base href="/">

  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>
  <!-- 渲染到loading这里去 -->
  <app-root>Loading...</app-root>
</body>
</html>
```

#

## <font face="Meiryo UI" size="4" color=#00008B> 
**Angular中优雅的处理RxJs自动取消订阅的方式以免出现内存泄露以及多次调用的问题**
</font>  
https://yuzhiqiang.blog.csdn.net/article/details/107443200


#

## <font face="Meiryo UI" size="4" color=#00008B> 
**路由**
</font> 