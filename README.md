# GitHub-Sped-Aggregation-Station
GitHub 下载与 Git Clone 加速聚合站。纯前端单文件，零依赖，输入任意 GitHub 链接，一次生成 **CDN 下载链接** 与 **Git Clone 链接**。

---

## 特性

- **CDN + Clone 同时输出**：任何 GitHub 链接都会同时生成下载组与 Clone 组，不做规则筛选。
- **全镜像聚合**：CDN（jsDelivr / raw.githack.com / statically.io）+ gh-proxy 系代理前缀 + gitclone.com / 域名替换型 Clone 镜像。
- **文件页自动转 Raw**：`github.com/user/repo/blob/...` 自动补全为 `raw.githubusercontent.com/...` 再套 CDN。
- **一键复制**：单条复制、整组复制、整组 Clone 命令复制。
- **深浅主题**：跟随系统，手动切换并持久化到 `localStorage`。
- **纯前端**：单 HTML 文件，无后端、无构建、无第三方依赖。

---

## 快速开始

1. 下载 `index.html`。
2. 双击用浏览器打开，或点击链接在线体验
3. 粘贴 GitHub 链接，点击「解析并加速」。

也支持直接回车或粘贴后自动解析。


## 部署提示
[https://github.com/zhi-xiaoer/GitHub-Sped-Aggregation-Station/wiki/部署提示](https://github.com/zhi-xiaoer/GitHub-Sped-Aggregation-Station/wiki/%E9%83%A8%E7%BD%B2%E6%8F%90%E7%A4%BA)

---

## 支持的链接

| 输入 | 识别为 | 生成 |
|---|---|---|
| `raw.githubusercontent.com/user/repo/ref/file` | Raw 文件 | CDN + 代理下载 + Clone + 代理 Clone |
| `github.com/user/repo/blob/ref/file` | 文件页 → Raw | 同上（自动转 Raw） |
| `github.com/user/repo/releases/download/tag/file` | Release 资产 | 代理下载 + Clone + 代理 Clone |
| `github.com/user/repo/archive/...` | 源码归档 | 代理下载 + Clone + 代理 Clone |
| `github.com/user/repo` | 仓库 | CDN（默认 `main` 分支）+ Clone + 代理 |
| `github.com/user/repo.git` | 仓库 | 同上 |

> [!NOTE]
> Gist 暂不支持，请使用 `gist.githubusercontent.com` 的 Raw 链接。

---

## 镜像源

**CDN（Raw 文件专用）**

| 名称 | 说明 |
|---|---|
| jsDelivr | `cdn.jsdelivr.net/gh/...`，单文件 ≤20MB |
| raw.githack.com | Raw 文件 CDN |
| statically.io | Raw 文件 CDN |

**gh-proxy 代理前缀**

`gh-proxy.com` · `ghproxy.net` · `ghfast.top` · `ghproxy.homeboyc.cn` · `moeyy.cn/gh-proxy` · `ghp.ci` · `ghps.cc` · `github.akams.cn` · `gh-proxy.org` · `v4.gh-proxy.org` · `cdn.gh-proxy.org`

**Git Clone**

| 名称 | 形态 | 示例 |
|---|---|---|
| gitclone.com | 去协议前缀 | `https://gitclone.com/github.com/user/repo.git` |
| hub.nuaa.cf | 域名替换 | `https://hub.nuaa.cf/user/repo.git` |
| githubfast.com | 域名替换 | `https://githubfast.com/user/repo.git` |

以上代理前缀同时可用于 Clone：`https://gh-proxy.com/https://github.com/user/repo.git`。

---



## 说明

- 镜像可用性随第三方服务状态变化，失效属正常现象，切换其他节点即可。
- CDN 对仓库根链接使用默认分支 `main` 生成，若仓库默认分支不同（如 `master`），请改用具体文件链接。
- jsDelivr 单文件上限约 20MB，大文件请走代理前缀。
- 所有转换在浏览器本地完成，不上传任何链接。

---

## License

MIT
