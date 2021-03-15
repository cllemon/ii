---
title: 开发环境的配置和搭建
summary: 记录平常工作中需要用到的一些工具、环境配置等（FE + Mac）
date: 2021-02-04
author: Wooden Kite
location: HuaiNan.AnHui
---

## VS Code

[一个 xxx 的代码编辑器](https://code.visualstudio.com/)，详细请[查看文档](https://code.visualstudio.com/docs)。

### 主题配置

```json
// 亮色调系（推荐 👏）
{
  "workbench.colorTheme": "Solarized Light",
  "workbench.iconTheme": "vscode-great-icons"
}
// 暗色调系
{
  "workbench.colorTheme": "One Dark Pro",
  "workbench.iconTheme": "vscode-icons"
}
```

### 扩展插件  🎉

<br>

1. <span style="color: #607D8B;">如果你需要为 VS Code 提供中文（简体）语言包，你可以安装</span><br>
  [Chinese (Simplified) Language Pack for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-zh-hans)

2. <span style="color: #607D8B;">如果你需要在你的代码里高亮颜色字符，你可以安装 </span><br>
   [Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)

3. <span style="color: #607D8B;">如果你需要在你的代码里突出显示 TODO，FIXME 和其他注释，你可以安装 </span><br>
   [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)

4. <span style="color: #607D8B;">如果你需要在你的代码里降低英文拼写错误率，你可以安装 </span><br>
  [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

5. <span style="color: #607D8B;">如果你需要在你写代码时引入文件时智能补全路径，你可以安装 </span><br>
  [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)

6. <span style="color: #607D8B;">如果你需要在 VS Code 里集成：查看git日志，文件历史记录，比较分支或提交，你可以安装 </span><br>
  [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)

7. <span style="color: #607D8B;">如果你需要在浏览代码时知道每行代码所关联的 Git 提交信息，你可以安装 </span><br>
  [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

8. <span style="color: #607D8B;">如果你需要 GitHub 样式的 Markdown 预览以及 Markdown 文档格式检查，你可以安装 </span><br>
  [Markdown Preview Github Styling](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles)
  [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

9. <span style="color: #607D8B;">如果你使用的是 react 框架，你可以安装 </span><br>
  [js-jsx-snippets](https://marketplace.visualstudio.com/items?itemName=skyran.js-jsx-snippets)
  [vscode-styled-jsx](https://marketplace.visualstudio.com/items?itemName=blanu.vscode-styled-jsx)

10. <span style="color: #607D8B;">如果你使用的是 vue 框架，你可以安装 </span><br>
  [vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)
  [Vue 3 Support - All In One](https://marketplace.visualstudio.com/items?itemName=Wscats.vue)

11. <span style="color: #607D8B;">将 ESLint、Prettier 集成到 VS Code 中</span><br>
  [eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)<br>
  [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)<br>
  <span style="color: #9E9E9E;font-size: 13px;">> 该扩展优先使用工作区中安装的 eslint/prettier 库，若未安装则尝试使用全局安装的</span>

### 推荐配置 👠

```json
{
  /* 主题 */
  "workbench.colorTheme": "Solarized Light",
  "workbench.iconTheme": "vscode-great-icons",

  /* 编辑器 */
  "editor.minimap.maxColumn": 30,
  "editor.minimap.side": "left",
  "editor.minimap.showSlider": "always",
  "editor.fontSize": 14,
  "editor.fontWeight": 600,
  "editor.tabSize": 2,
  "editor.showFoldingControls": "always",

  /* terminal */
  "terminal.integrated.fontSize": 13,
  "terminal.integrated.fontWeight": 500,
  "terminal.integrated.shell.osx": "/bin/zsh",
  "terminal.integrated.cursorStyle": "line",

  /* other */
  "javascript.updateImportsOnFileMove.enabled": "always",
  "typescript.updateImportsOnFileMove.enabled": "always",
  "workbench.editor.tabSizing": "shrink",
  "workbench.fontAliasing": "antialiased",
  "workbench.startupEditor": "none",
  "workbench.settings.editor": "json",
  "files.insertFinalNewline": true,
  "files.trimTrailingWhitespace": true,
  "files.exclude": {
    "**/.EXCL_*": false,
    "**/.DS_Store": true,
    "**/.git": true,
  },
  "files.watcherExclude": {
    "**/.git/objects/**": true,
    "**/.git/subtree-cache/**": true,
    "**/node_modules/**": true,
    "**/.hg/store/**": true,
    "**/dist/**": true
  },

  /* eslint prettier */
  ""
}
```

## 终端 -- iTerm 2 + oh my zsh

```sh
iTerm 2

安装

配置

https://github.com/sirius1024/iterm2-with-oh-my-zsh
```

## Vim

```sh
https://github.com/cocopon/iceberg.vim
```

## Git

```sh
# 安装

# ssh

# 使用
```

## Node

```sh
node

npm / yarn

nvm

nrm
```

## Chrome Extends

```sh
插件必备。。。

```

## 翻译工具

```sh
有道
Google 翻译
```

## 文档相关工具

```sh
Typora

one tips
```

## 其它工具

```sh
foxmail

wx

qq music
```

> 迁移中....

<!-- http://fe.surge.sh/guide/VSCode.html#vscode-%E8%AE%BE%E7%BD%AE -->
<!-- https://github.com/i5ting/i5ting-mac-init -->
