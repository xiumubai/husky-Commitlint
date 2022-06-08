# husky-Commitlint

husky7.0.1 + commitlint 配置提交代码检查和规范模板

## husky 安装

1、项目内安装
`npm i lint-staged husky -save-dev `
2、创建.husky/目录并指定该目录为 git hooks 所在的目录

```
{
  "scripts": {
      "prepare": "husky install"
  }
}

```

3、添加 git hooks

`npx husky add .husky/pre-commit "npm run lint"`

4、规范 commit message 信息

`npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"' `

## husky 使用

随便 commit 一下

`git commit -m "feat: pre-commit优化"`

报错信息如下：

```
npm ERR! Missing script: "lint"
npm ERR!
npm ERR! Did you mean this?
npm ERR!     npm link # Symlink a package folder
npm ERR!
npm ERR! To see a list of scripts, run:
npm ERR!   npm run

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/janney/.npm/_logs/2022-06-08T05_34_04_938Z-debug-0.log
husky - pre-commit hook exited with code 1 (error)
```

## commitlint 安装与配置

`npm i @commitlint/cli @commitlint/config-conventional -D`

到目前为止我们还没有配置 `npm run lint` 这个命令，所以 commit 的时候回报错

在 pre-commit 文件中把`npm run lint`注释了就可以了。

现在我们按照 commit 的规范来提交，就可以成功的提交代码了
