
# Node.js版本管理工具 - nvm
## 

### <font face="Meiryo UI" color=#00008B> 
**安装node采用nvm方式安装**
</font>  
https://www.jianshu.com/p/6c32d2078a2d

### <font face="Meiryo UI" color=#00008B> 
**nvm安装和配置**
</font>  
https://www.jianshu.com/p/273241280b72

### <font face="Meiryo UI" color=#00008B> 
**使用nvm安装nodejs**
</font>  
https://blog.csdn.net/hyk521/article/details/107475478

``` bash
#查看可安装node版本
nvm list available
#安装最新node 
nvm install latest 
#安装指定版本的node   
nvm install 16.13.2 
#卸载指定版本的node 
nvm uninstall 16.13.2
#查看已安装的node  
nvm list 或 nvm ls 
#切换到指定的node 版本
nvm use 16.13.2   

#切换版本必须要用管理员模式进入cmd窗口

nvm node_mirror https://npm.taobao.org/mirrors/node/  
nvm npm_mirror https://npm.taobao.org/mirrors/npm/  

``` 


# Node.js管理 - nvm
## 

### <font face="Meiryo UI" color=#00008B> 
**NPM镜像源查看和切换**
</font>  
https://www.cnblogs.com/seeding/p/15219113.html

### <font face="Meiryo UI" color=#00008B> 
**npm管理**
</font>  

``` bash
#npm查看当前版本  
npm -v  
#npm查看所有版本  
npm view npm versions  
#npm更新到最新版  
npm install -g npm

#yarn查看当前版本
yarn -v
#yarn查看所有版本 
npm view yarn versions 
#yarn更新到最新版 
npm install yarn@latest -g

#查看npm当前镜像源 
npm config get registry 
#设置npm镜像源为淘宝镜像
npm config set registry https://registry.npm.taobao.org/  
#查看yarn当前镜像源
yarn config get registry  
#设置yarn镜像源为淘宝镜像
yarn config set registry https://registry.npm.taobao.org/ 
#安装淘宝镜像
npm install -g cnpm -registry=https://registry.npm.taobao.org
``` 

### <font face="Meiryo UI" color=#00008B> 
**镜像源链接切换**
</font>  
``` bash
#查看镜像源使用状态： 
npm get registry 
#全局切换镜像源： 
npm config set registry http://registry.npm.taobao.org
npm config set registry https://registry.npmjs.org 
#全局切换官方镜像源 
npm config set registry http://www.npmjs.org
yarn config set registry https://registry.yarnpkg.com/
``` 

### <font face="Meiryo UI" color=#00008B> 
**nrm 管理镜像源**
</font> 
``` bash
npm install nrm -g
npm install -g nrm
#-g表示全局安装

#显示当前可使用的镜像源列表 
nrm ls

* npm -------- 
https://registry.npmjs.org/ 
yarn ------- 
https://registry.yarnpkg.com/ 
cnpm ------- 
http://r.cnpmjs.org/ 
taobao ----- 
https://registry.npm.taobao.org/ 
nj --------- 
https://registry.nodejitsu.com/ 
npmMirror -- 
https://skimdb.npmjs.com/registry/ 
edunpm ----- 
http://registry.enpmjs.org/
``` 

#### <font face="Meiryo UI" color=#00008B> 
**切换镜像源**
</font>  
nrm use taobao

#### <font face="Meiryo UI" color=#00008B> 
**Node version support policy**
</font>   
https://github.com/sass/node-sass
