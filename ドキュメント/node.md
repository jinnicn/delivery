
**node 版本管理工具 - nvm**

https://www.jianshu.com/p/6c32d2078a2d
安装node采用nvm方式安装
使用 NVM 安装 nodejs
https://blog.csdn.net/hyk521/article/details/107475478
nvm install latest // 安装最新node
nvm install 8.2.1 // 安装指定版本的node
nvm uninstall 8.2.1 // 卸载指定版本的node
nvm list 或 nvm ls // 查看已安装的node
nvm use 10.15.3 // 切换到指定的node 版本
nvm node_mirror https://npm.taobao.org/mirrors/node/
nvm npm_mirror https://npm.taobao.org/mirrors/npm/
// npm查看当前版本 npm -v // npm查看所有版本 npm view npm versions // npm更新到最新版 npm install -g npm
// yarn查看当前版本 yarn -v // yarn查看所有版本 npm view yarn versions // yarn更新到最新版 npm install yarn@latest -g
npm config get registry // 查看npm当前镜像源 npm config set registry https://registry.npm.taobao.org/ // 设置npm镜像源为淘宝镜像 yarn config get registry // 查看yarn当前镜像源 yarn config set registry https://registry.npm.taobao.org/ // 设置yarn镜像源为淘宝镜像
NPM镜像源查看和切换 
https://www.cnblogs.com/seeding/p/15219113.html
镜像源链接切换
//查看镜像源使用状态： npm get registry //全局切换镜像源： npm config set registry http://registry.npm.taobao.org
npm config set registry https://registry.npmjs.org //全局切换官方镜像源 npm config set registry http://www.npmjs.org
yarn config set registry https://registry.yarnpkg.com/
nrm 管理镜像源
npm install nrm -g
npm install -g nrm
//-g表示全局安装
//显示当前可使用的镜像源列表 nrm ls
* npm -------- https://registry.npmjs.org/ yarn ------- https://registry.yarnpkg.com/ cnpm ------- http://r.cnpmjs.org/ taobao ----- https://registry.npm.taobao.org/ nj --------- https://registry.nodejitsu.com/ npmMirror -- https://skimdb.npmjs.com/registry/ edunpm ----- http://registry.enpmjs.org/
切换镜像源
nrm use taobao
Node version support policy
https://github.com/sass/node-sass
