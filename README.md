# GitHub Pages 部署步骤

本包已适配 GitHub Pages。只上传本包文件，不上传本机平台完整包、data 文件夹或价格备份。

## 1. 创建仓库

登录 GitHub，点右上角 `+` → `New repository`，仓库名例如 `ad600s-price-platform`，选择 `Public`，勾选 `Add a README file`，点 `Create repository`。

GitHub Free 使用公开仓库发布 Pages。此包是空数据模板，不包含你的价格排期、备注或抓取示例。

## 2. 上传网页

进入仓库，点 `Add file` → `Upload files`，上传本包解压后的 `index.html` 和 `.nojekyll`，点 `Commit changes`。若系统隐藏 `.nojekyll`，可在仓库用 `Add file` → `Create new file` 创建同名空文件；本项目不依赖它也能显示网页。

文件应直接放在仓库根目录，确保能在仓库首页看到 `index.html`。不要上传ZIP，也不要把整个文件夹再包一层。

## 3. 启用 Pages

打开仓库 `Settings` → 左侧 `Pages`：

- `Source` 选择 `Deploy from a branch`
- `Branch` 选择 `main`
- 文件夹选择 `/ (root)`
- 点击 `Save`

等待发布完成，可在 `Actions` 看 `pages build and deployment` 的执行结果，再回到 `Settings` → `Pages` 点 `Visit site`。一般几分钟，最长可能约10分钟。

地址形如 `https://你的GitHub用户名.github.io/ad600s-price-platform/`，以 Pages 显示的地址为准。

## 4. 恢复价格记录

在新网站点 **恢复备份**，选择从本机平台“下载备份”导出的JSON，确认后等待顶部显示 **已保存 · 本浏览器**。同目录之外另外提供的迁移备份也可用于恢复。

不要把JSON备份上传到GitHub。公开Pages网页可被他人打开，价格数据通过浏览器导入并保存在该浏览器，不会发送到GitHub，也不会自动同步给他人或另一台设备。

## 以后使用和更新

- 日常改价、改备注：在网页操作即可，自动保存到当前浏览器，不必重新上传网页。
- 换设备或浏览器：先“下载备份”，再到新设备“恢复备份”。清理网站数据前也应备份。
- 更新页面功能：只替换仓库的 `index.html`，等待重新发布。更新前先下载备份，保留同一仓库地址。
- GitHub Pages不运行本平台的Node/SQLite服务。多人实时共用一套数据，需要额外数据库和登录权限。

官方说明：https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
