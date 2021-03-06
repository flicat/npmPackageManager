## NPM Package Manager
##### npm包版本检查，自动安装

- 如何使用？
> 将文件放到根目录下，与`package.json`同级
```
├ node_modules
├ checkVersion.js
└ package.json
```
> 修改package.json，添加一行npm命令
```
  "scripts": {
    // ... 其他命令
    "check-version": "node checkVersion.js"
  },
```
> 在开发和构建命令前添加版本检查命令
```
  "scripts": {
    "check-version": "node checkVersion.js",
    "serve": "npm run check-version && vue-cli-service serve",
    "build": "npm run check-version && vue-cli-service build"
  },
```

```
version

    精确匹配某个版本

    如：1.1.2，表示必须依赖 1.1.2 版

>version

    大于某个版本

    如：>1.1.2，表示必须大于 1.1.2 版

>=version

    大于或等于某个版本

    如：>=1.1.2，表示可以等于 1.1.2，也可以大于 1.1.2 版本

<version

    小于某个版本

    如：<1.1.2，表示必须小于 1.1.2 版本

<=version

    小于或等于某个版本

    如：<=1.1.2，表示可以等于 1.1.2，也可以小于 1.1.2 版本

~version

    当前版本号为起始版本，以倒数第二个版本号+1（次版本号 Y）为递增版本，可更新 [起始，结束) 范围内的所有版本号。
    如：~1.2.3 代表 >=1.2.3 <1.(2+1).0 即 >=1.2.3 <1.3.0

^version

    更新主版本号，如果版本号为 0，则往下取非 0 版本号递增，作为最大版本号。

    如：^1.2.3 // 代表 >=1.2.3 <2.0.0

x 标识符

    x 的位置表示任意版本

    如：1.2.x，表示可以 1.2.0，1.2.1，.....，1.2.n

* 标识符

    任意版本，"" 也表示任意版本

    如：*，表示 >=0.0.0 的任意版本

version1 - version2

    大于等于 version1，小于等于 version2

    如：1.1.2 - 1.3.1，表示包括 1.1.2 和 1.3.1 以及他们件的任意版本
```
