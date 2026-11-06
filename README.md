# 个人学术主页 · GitHub Pages 版

这个文件夹就是可以整包上传到 GitHub 的版本。需要上传的是这 4 样（README.md 只是说明，传不传都行）：

```
index.html      网页模板（负责排版，一般不用改）
content.json    所有文字内容（改这里就行）
files/          放 PDF 等附件（简历已在 files/cv.pdf）
.nojekyll       告诉 GitHub 不要用 Jekyll 处理，别删
```

## 怎么发布

1. 登录 GitHub，右上角 **+** → **New repository**
2. Repository name 填 `你的用户名.github.io`（例如 `mingyuanzhang.github.io`），选 **Public**，不要勾选任何初始化文件，点 **Create repository**
3. 在新仓库页面点 **uploading an existing file**，把这个文件夹里的**全部内容**拖进去（注意：要拖 `index.html`、`content.json`、`files` 文件夹、`.nojekyll` 本身，不要多套一层文件夹），点 **Commit changes**
4. 打开仓库 **Settings** → 左侧 **Pages** → Source 选 **Deploy from a branch**，Branch 选 **main**、目录选 **/(root)**，点 **Save**
5. 等 1～2 分钟，页面顶部会显示网址：`https://你的用户名.github.io/`

如果仓库名不是 `用户名.github.io`（比如叫 `academic-homepage`），网址就是
`https://你的用户名.github.io/academic-homepage/`，同样能正常访问。

## 以后怎么改内容

1. 本地改 `content.json`（用 VS Code 或记事本，注意逗号和引号）
2. 双击本地项目里的「启动预览.bat」看效果
3. 回到 GitHub 仓库，点进 `content.json` → 右上角铅笔图标编辑，或者 **Add file → Upload files** 覆盖上传
4. Commit 后等约 1 分钟，线上自动更新，网址不变

## 放新的 PDF

把 PDF 放到 `files/` 文件夹，然后在 `content.json` 里写相对路径，例如：

```json
{ "label": "PDF", "href": "files/paper-2026.pdf", "download": true }
```

文件不存在时链接会自动隐藏，不会出现死链。

## 换配色

`content.json` 里 `site.theme` 可选：`green` `lightblue` `navy` `lightgreen` `deepgreen` `red` `orange` `purple` `graphite`。
