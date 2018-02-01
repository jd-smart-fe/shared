# Guide

> 欢迎补充更多合理的规范

## 代码提交规范

### 提交代码时应遵守的 commit 规范

每一个 commit 都应该清晰明了，commit 的描述应和提交的改动一致。同时为了提高 commit 质量，故进行以下约定：

* feat：新功能（feature）
* fix：修补bug
* docs：文档（documentation）
* style： 格式（不影响代码运行的变动）
* refactor：重构（即不是新增功能，也不是修改bug的代码变动）
* test：增加测试
* chore：构建过程或辅助工具的变动

例如：

```
$ git commit -m "feat: add a new feature in button component"
```

## 代码格式规范

使用 EditorConfig 来规范代码格式

配置文件内容如下:
```
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
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

使用 ESLint 来进行代码风格检测。

团队目前以 airbnb 代码风格为基准。

使用 [eslint-g](https://github.com/pspgbhu/eslint-g) 来自动生成 `.eslintrc.json` 文件。

```bash
$ sudo npm i -g eslint-g    # 安装
$ cd my-project             # 进入项目根目录
$ esg -r react              # 生成 react 的 eslintrc 规则，并安装相应依赖
```
更多配置请查看 [eslint-g 文档](https://github.com/pspgbhu/eslint-g)