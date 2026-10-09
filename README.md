# 工程伦理习题库

手机或电脑直接打开：**https://kieran0625.github.io/buaa-engineering-ethics/**

独立仓库：**https://github.com/kieran0625/buaa-engineering-ethics**

第 1–15 讲共 303 道题，包含完整题干、选项、参考答案及原资料解析。

- 按章节、题型、关键词筛选；支持背题与练习模式。
- 支持单选、多选、判断、错题复习、收藏和随机排序。
- 适配手机、平板和电脑，也可下载 index.html 离线打开。
- 练习记录保存在当前浏览器，不会上传；不同设备之间不会自动同步。
- 手机可使用浏览器菜单“添加到主屏幕”，方便下次访问。

## 更新题库

需要 Node.js，无需安装构建依赖。在本仓库根目录操作：

```sh
git clone https://github.com/kieran0625/buaa-engineering-ethics.git
cd buaa-engineering-ethics
```

修改对应 Markdown 资料或 web/ 中的源码后执行：

```sh
node build-site.js
node tests/verify-site.js
```

将源码、资料以及重新生成的 `index.html`、`questions.json` 一起提交到 `main` 分支，GitHub Pages 会自动重新发布。发布设置：**Settings → Pages → Deploy from a branch → main / (root)**；`.nojekyll` 确保按静态文件发布。

浏览器检查使用本机 Chrome 和 `playwright-core`：

```sh
npm install --no-save --package-lock=false playwright-core
node tests/browser-check.js
```

脚本默认使用 macOS 的 Chrome 路径；其他环境通过 `BROWSER_EXECUTABLE` 指定浏览器可执行文件。检查报告与截图输出到 `artifacts/browser-check/`，不会提交到仓库。

## 从个人网站仓库迁移

本项目原位于 [kieran0625.github.io](https://github.com/kieran0625/kieran0625.github.io) 仓库的 `buaa-engineering-ethics/` 子目录，现由本仓库独立维护和部署。题库源码、全部 Markdown 资料、构建脚本和测试脚本均位于本仓库根目录；个人主页仍由原仓库维护。

在线网址保持不变，无需修改收藏夹。同一浏览器、同一浏览器配置中原有的错题、收藏和练习记录继续使用 `engineering-ethics-progress-v1` 本地存储键。不同浏览器或设备之间不自动同步，离线文件的记录与在线网站不共享。

## 文件说明

- index.html：可独立打开的完整网页。
- web/：页面模板、样式和交互源码。
- build-site.js：从原始资料构建题库并交叉核对答案。
- questions.json：结构化题库。
- tests/：数据、逻辑和浏览器检查脚本。
- 各讲 Markdown：题干、选项、答案与解析来源。

数据校验覆盖全部 303 题；Chrome 浏览器已检查 320–1440px 共 10 个尺寸及主要交互。手机尺寸使用浏览器视口模拟，未进行 iOS Safari 真机验证。

答案与解析沿用本地学习资料；原资料中的差异或需核对事项保留在对应题目的资料提示中。
