# 命名规范

1. [代码仓库命名](ming-ming-gui-fan.md#代码仓库命名)
   * [分组命名](ming-ming-gui-fan.md#1-分组命名)
   * [仓库命名](ming-ming-gui-fan.md#2-仓库命名)
2. [项目结构命名](ming-ming-gui-fan.md#项目结构命名)
   * [项目命名](ming-ming-gui-fan.md#1-项目命名)
   * [目录命名](ming-ming-gui-fan.md#2-目录命名)
   * [模板文件命名](ming-ming-gui-fan.md#3-模板文件命名)
   * [样式文件命名](ming-ming-gui-fan.md#4-样式文件命名)
   * [JS文件命名](ming-ming-gui-fan.md#5-JS文件命名)
3. [公用组件库命名](ming-ming-gui-fan.md#公用组件库命名)
   * [插件库](ming-ming-gui-fan.md#1-插件库)
   * [独立的插件库](ming-ming-gui-fan.md#2-独立的插件库)
   * [组件库](ming-ming-gui-fan.md#3-组件库)
   * [脚手架](ming-ming-gui-fan.md#4-脚手架)
4. [持续集成与项目发布](ming-ming-gui-fan.md#持续集成与项目发布)
   * [Jenkins命名](ming-ming-gui-fan.md#Jenkins命名)
   * [域名划分](ming-ming-gui-fan.md#域名划分)

## 代码仓库命名

项目采用`GitLab`为代码版本管理工具

### 1. 分组命名

以项目为第一维度，建立分组（Group）。

`Group`名称可以是项目英文名或英文缩写，多个英文单词之间用连字符`-`连接。

例：`alibaba-taobao`

### 2. 仓库命名

命名结构：前端为`子项目描述 + 终端`，后端为`子项目描述 + 服务类型`。

* 子项目描述：采用语义化的子项目名，结构建议为`用户群+功能描述`。

用户群通常分为HQ端、B端、C端。功能描述如`admin`、`store`等。

如总部后台`hq-admin`、商户后台`merchant-admin`、用户端微店`c-ministore`。

* 终端：一般分为网页端（web，wap）、手机、pad移动端APP（ios/android/内嵌h5）、微信端（公众号、企业号、小程序、小游戏）和其他一些智能设备（如收银机、电视等）。

使用规则：

手机APP：`mobile`，可细分为`mobile-android`、`mobile-ios`、`mobile-h5`

微信端：`wechat`，可细分为`wechat-h5`、`wechat-miniapp`

pad端：`pad`，可细分为`pad-android`、`pad-ios`、`pad-h5`

pos端：`pos`，可细分为`pos-android`、`pos-ios`、`pos-web`

浏览器端：pc端`web`、手机端`h5`

* 服务类型：`service`Java 服务、`api`Node服务、`job`定时任务...

## 项目结构命名

### 1. 项目命名

小写英文字母，多字母以`-`分隔。

### 2. 目录命名

参照项目命名规则；

有复数结构时，要采用复数命名法。

\[强制\]

```bash
src        # 开发目录
dist        # 产出目录
common        # 公用模块
components    # 公用组件
plugins     # js插件
pages        # 页面
assets        # 图片
styles        # CSS
icons        # iconfont / SVG
static        # 不需编译的外部资源
store        # 状态管理
dao        # 数据层
apis        # ajax request 抽离
mock        # 数据模拟
config        # 配置中心
...
```

### 3. 模板文件命名

参照项目命名规则；

以`.html`结尾。

若使用第三方模板引擎，y以第三方模板引擎规定的方式命名。如`.pug`。

例：`404.html`

### 4. 样式文件命名

参照项目命名规则；

以`.css`结尾。

若使用第三方`CSS`预处理程序，以`CSS`预处理程序规定的方式命名。如`.styl`。

例：`variables.css`、`variables.styl`

### 5. JS文件命名

参照项目命名规则，

以`.js`结尾。若使用`es6`语法的文件要区别于其他JS，以`.es6`结尾。

例：`common_model.js`、`toast.es6`

## 公用组件库命名

### 1. 插件库

命名结构：`公司名/事业名/项目名-plugins`。

### 2. 独立的插件库

命名结构：`公司名/事业名/项目名-功能-sdk`。

### 3. 组件库

命名结构：`公司名/事业名/项目名-components`。

### 4. 脚手架

命名结构：`公司名/事业名/项目名-脚手架名称-cli`。

## 持续集成与项目发布

### Jenkins命名

项目划分与命名与[代码仓库命名](ming-ming-gui-fan.md#代码仓库命名)保持一致。

### 域名划分

* 在公司层面，以项目/事业为基础，建立子域名。层级相当于代码仓库中的`group`。结构为`[group].xxx.com`。
* 以`子项目功能描述`为第一层级域名。若该子项目有不同终端，则以`终端`为第二层域名。如后台管理结构为`[group].xxx.com/hqadmin`。
* 若项目以`Nginx`等代理的形式实现跨域，则以`/api`为接口请求标志，作为最后一层域。如后台管理接口结构为`[group].xxx.com/hqadmin/api`。

