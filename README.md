# spm alipay suite

-------

## 安装

先安装 spm2

```
$ npm install spm -g
```

安装支付宝前端工具

```
$ npm install spm-alipay-suite -g
```

如果你的环境需要 `sudo`，请先阅读这篇文章：http://aralejs.org/docs/installation.html

安装完后可以检查下你的环境

```
$ spm check
```

## Package.json

spm2 的 `package.json` 和 spm 略不相同，需要修改才能用这个工具。

查看[package.json](http://docs.spmjs.org/en/package)


## 支付宝套装收罗的功能有：

- spm 包管理工具 ([文档](http://docs.spmjs.org/en/index))

- `spm build` 构建插件 

- `spm deploy` 部署插件 ([文档](https://github.com/spmjs/spm-alipay-suite/#spm-deploy))

- `spm init` 初始化插件以及 Arale 和 Alice 的初始化模板 ([文档](https://github.com/spmjs/spm-init/blob/master/README-zh.md))

- `spm status` 模块发布状态检测插件 ([文档](https://github.com/spmjs/spm-alipay-suite/#spm-status))

- `spm zip` 打成 zip 包 ([文档](https://github.com/spmjs/spm-alipay-suite/#spm-zip))

- `spm check` 检查 spm 配置环境和相关插件的版本是否正确

- `spm test` 使用 totoro 跑测试用例

- `spm test-src` 使用 phantomjs 跑测试用例，使用 src 代码

- `spm test-dist` 使用 phantomjs 跑测试用例，使用 dist 代码

- `spm build-doc` 生成文档到 _site 目录下

- `spm publish-doc` 将文档发布到源上

- `spm coverage` 执行覆盖率工具，生成页面到 _site/coverage.html

- `nico` 静态文件构建工具

- nico 所用到的 Arale 和 Alice 的静态文档模板

- stylus 编译功能（当 src 目录中有 *.styl 文件时，`spm build` 会自动构建出对应的 css 文件）

- check-online 构建时检测该模块是否已发到线上

- [peaches](http://peaches.io) 雪碧图片合并工具（还未添加）


## 具体使用说明

### spm zip

在发布流程中需要将文件打包上传，`spm zip` 会在当前目录生成 zip 包。

**注意：包内的目录结构 `family/name/version/filename`，所以要在 assets 目录上传。**

### spm deploy

执行 `spm deploy` 将 dist 目录下的文件部署到静态服务器，默认部署到 http://assets.dev.alipay.net。

如果要部署到某台服务器，执行 `spm deploy --target p631`。

如果要指定服务器密码，执行 `spm deploy --password admin`。

如果要部署源上某个组件，执行

```
$ spm deploy arale/base
$ spm deploy arale/base@1.0.0
```

### spm status

检查某个模块的发布状态，包括 dev、test、和线上三个环境。

```
$ spm status arale/widget
$ spm status arale/widget@1.0.3

$ spm status arale              // 检测 arale 下所有模块
$ spm status arale --error      // 只打印出报 404 的模块
```
