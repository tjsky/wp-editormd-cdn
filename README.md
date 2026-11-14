# WP Editor.md · 静态资源

[WP Editor.md](https://github.com/tjsky/WP-Editor.md) 的编辑器静态资源，供插件设置中的
「Editor.md 静态资源地址」使用。

仓库只包含前端资源（JS、CSS、字体、emoji 图片），不含插件代码。内容与 GitHub Release
安装包 `wp-editormd-x.y.z.zip` 里的 `assets/` 一致。

## 使用

WordPress 后台 → **设置 → WP Editor.md → 编辑器风格**：

| 字段 | 填写内容 |
| --- | --- |
| Editor.md 静态资源地址 | `https://cdn.jsdelivr.net/gh/tjsky/wp-editormd-cdn@10.5.4` |
| 静态资源完整性校验 | `integrity-core-10.5.4.txt` 的内容（可选） |

地址写到版本号为止，插件会自行拼接 `/assets`。末尾的 `10.5.4` 是 tag，内容固定在该版本。

## 文件

| 路径 | 说明 |
| --- | --- |
| `assets/` | 插件加载的全部静态资源，2026 个文件，约 23 MB |
| `integrity-10.5.4.txt` | 全量哈希清单，每个文件一行 |
| `integrity-core-10.5.4.txt` | 精简哈希清单，收录插件实际加载的 41 个文件 |

`assets/` 内含 emoji 图片、KaTeX 字体与 CodeMirror 主题，自建镜像时需整目录同步。

## 版本

- `main`：最新发布版本的资源，随版本更新覆盖。
- tag：与插件版本号对应，如 `10.5.4`。

`10.5.3` 的资源与同版本安装包不一致，该版本不要填写完整性校验。

## 授权

资源来自 [tjsky/WP-Editor.md](https://github.com/tjsky/WP-Editor.md)（上游
[LuRenJiasWorld/WP-Editor.md](https://github.com/LuRenJiasWorld/WP-Editor.md)），沿用
**GNU GPL v3 or later**，见 [LICENSE](LICENSE)。

`assets/Editormd` 部分原始作者为 [@pandao](https://github.com/pandao)（MIT，随包分发于
GPLv3 之下）。其余第三方组件（KaTeX、Mermaid、Prism.js、CodeMirror 等）的版权与许可
见各自目录内的说明。
