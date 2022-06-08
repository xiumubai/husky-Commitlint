# preitter + eslint

## preitter

1. 安装

```
npm install --save-dev --save-exact prettier
// or
yarn add --dev --exact prettier
```

2. 创建一个空配置文件，让编辑器和其他工具知道你正在使用 Prettier：

`echo {}> .prettierrc.json`

添加内容

```json
{ "singleQuote": true }
```

3. 创建一个.prettierignore[3]文件，让 Prettier CLI 和编辑器知道哪些文件不能格式化，example：

```
# Ignore artifacts:
dist
build
.husky
```

4. 配置编辑器（VScode 为例）

IDE 中安装 Prettier-Code Formater[4] 插件：
找到 IDE 中设置模块，搜索 format On Save，勾上这个就可以了。

在 test.js 当中添加

`const test = "test";`

现在当我们 Ctrl + S 保存代码时，插件就会帮助我们自动格式化了
