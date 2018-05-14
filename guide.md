# Guide

> 欢迎补充更多合理的规范

## Git 相关

### 代码提交规范

关于 Git 的 commit, 务必保证其原子性, 描述信息务必要准确描述这次代码改动所做的事情.

在此基础之上, 提交代码时应遵守以下写法, 这也是开源社区较为推崇的一种写法, 最早从 Angular 社区传播开来. 格式为 `<type>(<scope>): <subject>`, 例如:

* feat：新功能（feature）
* fix：修补 bug
* docs：文档（documentation）
* refactor：性能或结构上的优化，并未带来功能的逻辑变化
* chore：构建过程或辅助工具的变动
* comments: 修改代码注释
* log: 修改代码 log
* remove: 已删除的功能
* test：增加测试
* deploy: 上线部署（比如需要在本地 build 资源）
* ~~style： 格式（比如：空格，空行的删除，log 的增删等）~~


三个部分中 *type* 和 *subject* 必不可少, *scope* 根据实际情况来. 如果某个 Git 仓库包含了几个大业务块, 而我们的 commit 往往只是其中一个业务块中的一部分需求, 这个情况下将 scope 补充上较好.

举个🌰：

```
$ git commit -m "feat: add a new feature in button component"
```


### 补充性规范

关于 git 库创建的*标题*, *描述*, *README.md*, 每一块信息都务必填写准确, README.md 要做到能完善描述整个项目, 原则上对于一个从为接触过项目的同学, 在看完 REAME.md 之后即可对项目有一个了解, 不允许留白, 也不允许出现 test 字样, 同时也不要保持脚手架生成项目时的默认 README.md 内容, 务必对其做出恰当的修改.

## 代码格式规范

使用 EditorConfig 来规范代码格式

配置文件内容如下:
```
indent_style = space                # 使用空格缩进
indent_size = 2                     # 缩进长度 2 空格
end_of_line = lf                    # Unix 换行符
charset = utf-8                     # 编码格式 UTF-8
trim_trailing_whitespace = true     # 删除行位空格
insert_final_newline = true         # 文件尾部添加一个空行
```

### 在 vscode 中使用 EditorConfig

1. `npm install -g editorconfig`

2. 在 vscode 插件中心安装 **EditorConfig for VS Code**

3. 配置 vscode 用户设置
    1. 在 vscode 中按下 `cmd + shift + p` 输入 `user settings` 回车，
    2. files.trimFinalNewlines 和 files.trimTrailingWhitespace 值设为 true

4. 生成 `.editorconfig` 文件。
    - 在项目根目录下手动建立 `.editorconfig` 文件，并配置规则。
    - 或，`cmd + shift + p` 输入 `generator .editorconfig` 由 vscode 建立文件，并检查配置。

5. Enjoy It.


## 代码风格规范

使用 ESLint 来进行代码风格检测。[查看团队常用 eslintrc 配置](https://github.com/pspgbhu/eslint-g/tree/master/rc)

在本地部署 ESLint 开发环境：

1. 安装 ESLint npm 包
```js
$ npm install -g eslint
```

2. 在代码编辑器插件中心下载 eslint 插件，以获得在编辑器内实时监测代码风格的功能。

3. 使用 Vue 或 React 脚手架时，请启用 ESLint，以获取编译时的代码风格检测功能。

4. 配置适合项目的 ESLint 规则，并安装对应 npm 包到项目下。(推荐使用工具 [eslint-g](https://github.com/pspgbhu/eslint-g) 来完成该步骤)

[eslint-g](https://github.com/pspgbhu/eslint-g) 可以帮助你生成 **Nodejs**, **Vue**, **React** 和 **浏览器通用环境** 下的团队常用的 ESLint 配置，同时还会帮助你安装对应的 npm 依赖包。


```bash
$ sudo npm i -g eslint-g    # 安装，会在终端中增加 esg 命令。
$ cd my-project             # 进入项目根目录
$ esg -r react -i yarn      # 生成 react 的 eslintrc 规则，并使用 yarn 安装相应依赖
```
更多配置请查看 [eslint-g 文档](https://github.com/pspgbhu/eslint-g)
