# 初始化项目
mkdir wwy-debounce-plugin
cd wwy-debounce-plugin
npm init -y

# 安装vue3和vite的依赖
npm install vite vue@next --save

# index.js中关键的install方法
app.config.globalProperties.$wwydebounce = wwydebounce;

# 打包构建插件
vite build

# 配置 package.json文件
...
"module": "dist/wwy-debounce-plugin.js",
"exports": {
  ".": {
    "import": "./dist/wwy-debounce-plugin.js",
    "require": "./dist/wwy-debounce-plugin.js"
  }
},
...

# 关联远程 Git 仓库
git init
git add *
git commit -m "wwy-done"

git remote add origin https://github.com/yourname/wwy-debounce-plugin.git
git push origin main

# 注册 npm 账号并且登录发布
npm login

# 发布
发布前先看看包名有没有被使用了
npm search wwy-debounce-plugin
然后发布指令如下
npm publish

# 发布成功后在项目中使用
（1）安装插件
npm install wwy-debounce-plugin

（2）在main.js 或 main.ts 文件引入使用插件
import wwyDebouncePlugin from 'wwy-debounce-plugin';

app.use(wwyDebouncePlugin);

然后就可以在页面直接$wwydebounce使用了。


