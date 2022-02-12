# 开始Angular

## 1安装
### 1.1 安装VSCode

### <font face="Meiryo UI" color=#00008B> 
**下载VSCode**
</font>   
https://code.visualstudio.com/

### <font face="Meiryo UI" color=#00008B> 
**默认安装**
</font>   
 *设定管理员启动*

### <font face="Meiryo UI" color=#00008B> 
**解决vscode无法使用ng命令的问题**
</font>  
https://www.php.cn/tool/vscode/450803.html  
<font face="Meiryo UI" size="3" color=#BC8F8F>

//*安全策略问题说明*  
</font>
https://docs.microsoft.com/zh-CN/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2
``` bash
#右键左下角开始按钮选择Windows PowerShell（管理员）（A）
set-ExecutionPolicy RemoteSigned
输入A
``` 



### 1.2 安装Angular脚手架
### <font face="Meiryo UI" color=#00008B> 
**使用vscode创建angular2应用**
</font>  
https://blog.csdn.net/yuanyuanhefangfang/article/details/105231750

``` bash
#在终端中全局安装angular cli
npm install -g @angular/cli

#使用angular cli的命令创建新angular2项目骨架
ng new projectname

#使用命令ng serve 启动angular应用
ng serve

#访问http://localhost:4200/
http://localhost:4200/
``` 

#

### <font face="Meiryo UI" color=#00008B> 
**VSCode插件**
</font>  

**必须**  
//引用填充和跳转到定义（html中进行引用补全）  
Angular Language Service

//Angular TypeScript Snippets for VS Code  
Angular Snippets

//HTML Snippets  
HTML Snippets  



**推荐**   
//markdownlint  
markdownlint



**未验证**  
TSLint：Typescript语法检查  
Prettier：代码格式化  
IntelliJ IDEA Keybindings：IDEA风格的快捷键  
Angular 7 Snippets：Angular语法填充（标签）  
Angular Files：生成Angular的文件模板（Component、Module、Pipe等等）  
Angular Follow Selector：文件跳转（Component跳转到html、scss文件）  
Angular Language Service：  
Debugger for Chrome：调试Angular代码  
Material Icon Theme（文件图标）
One Dark Pro（主题）
