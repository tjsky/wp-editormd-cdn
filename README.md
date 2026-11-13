# WP Editor.md · 静态资源（CDN）

[WP Editor.md](https://github.com/tjsky/WP-Editor.md) 维护版的编辑器静态资源，供插件设置里的
「Editor.md 静态资源地址」指向使用。

本仓库不含插件代码，只有前端资源（JS / CSS / 字体 / emoji 图片），内容与 GitHub Release
里的安装包 `wp-editormd-x.y.z.zip` 中 `assets/` **逐字节一致** —— 这一点决定了
`integrity` 哈希能不能对上。

## 怎么用

在 WordPress 后台 → **设置 → WP Editor.md → 编辑器风格**：

| 字段 | 填什么 |
| --- | --- |
| Editor.md 静态资源地址 | `https://cdn.jsdelivr.net/gh/tjsky/wp-editormd-cdn@10.5.4` |
| 静态资源完整性校验 | `integrity-core-10.5.4.txt` 的内容（可选，推荐） |

地址末尾**不要**加 `/assets` —— 插件自己拼。地址里的 `@10.5.4` 是 tag，锁定在该版本，
不会被后续更新影响。

## 目录

```
assets/                      插件运行时加载的全部静态资源（2026 个文件，约 23 MB）
integrity-10.5.4.txt         全量哈希清单（每个文件一行）
integrity-core-10.5.4.txt    精简哈希清单（插件实际会加载的 41 个文件，推荐填这个）
```

`assets/` 里不只有 JS / CSS：emoji 图片、KaTeX 字体、CodeMirror 主题都在里面，
使用自建镜像时必须整目录同步，不能只挑 `.js` / `.css`。

## 版本约定

* 分支 `main` 始终是**最新发布版本**的资源（覆盖式更新）。
* 每次发版打一个与插件版本号一致的 tag（如 `10.5.2`），插件默认值与文档都指向具体 tag。
* **不要**在 jsDelivr 侧开任何会改写内容的优化（压缩、图片重编码、JS 美化）——
  `integrity` 校验的是字节，内容变了哈希就对不上，浏览器会直接拒绝加载。

## 授权

资源来自 [tjsky/WP-Editor.md](https://github.com/tjsky/WP-Editor.md)（上游为
[LuRenJiasWorld/WP-Editor.md](https://github.com/LuRenJiasWorld/WP-Editor.md)），
沿用 **GNU GPL v3 or later**，见 [LICENSE](LICENSE)。
其中 `assets/Editormd` 部分原始作者为 [@pandao](https://github.com/pandao)（MIT，随包分发于 GPLv3 之下），
其余第三方组件（KaTeX / Mermaid / Prism.js / CodeMirror 等）版权与许可见各自目录内的说明。
