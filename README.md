# Vue 3 + TypeScript + Vite
## 一、创建vite+vue项目
```
npm init vite
√ Project name: ... vite-vue3-electron-example  --项目名称
√ Select a framework: » Vue --选择vue模板
√ Select a variant: » TypeScript --选择TypeScript脚本语言
```

## 二、安装依赖并运行
```
  cd vite-vue3-electron-example
  npm install
  npm run dev
```
---
通过上面两步就完成了一个vite+vue3+typeScript项目的初始化。


## 三、集成electron
1. 安装electron依赖（如果连接超时，使用镜像源安装）
```
 npm add --dev electron
```

以下两个文件参考[官网快速入门教程](https://www.electronjs.org/zh/docs/latest/tutorial/quick-start)

2. 添加electron入口文件 [main.js](main.js)

3. 添加electron预加载文件[preload.js](preload.js)

4. 修改[package.json](package.json)
```
删除属性："type": "module"
添加属性："main": "main.js"
scripts里增加脚本： "electron:serve": "electron ." 
```
5. 修改[main.js](main.js)
```
mainWindow.loadFile('index')
换成：
mainWindow.loadURL('http://127.0.0.1:5173/')
```

## 四、运行项目
1. 启动vite
```
npx vite
```
2. (新启一个终端)启动electron
```
npm run electron:serve
```
恭喜您，第一个electron启动成功！