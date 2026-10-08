# Venera 漫画源（修复版）

本仓库是 [venera-app/venera-configs](https://github.com/venera-app/venera-configs) 的修复快照：对其中**无法使用**的漫画源逐一核查并修复，可直接作为 Venera 的本地/在线漫画源目录导入。

## 已修复的源（9 个）

| 源 | 版本 | 问题与修复 |
|---|---|---|
| Picacg | 1.0.6→1.0.7 | 图片 URL 双写 `/static/`（path 已含 `/static/`）导致封面/正文/头像全 404 |
| nhentai | 1.1.0→1.1.1 | 搜索端点 `/search`→`/galleries/search`；封面/章节图改为按 `media_id` 自拼 `i/t.nhentai.net`（v2 API 无 `p.path` 字段）；补语言识别与标签联想 |
| 拷贝漫画 | 1.4.2→1.4.3 | 死域名 `api.copy2000.online`/`api.copy-manga.com` → `api.copymanga.org` |
| 拷贝漫画(多账号) | 1.4.1→1.4.2 | 同上两处死域名 |
| 包子漫画 | 1.1.6→1.1.7 | 默认域名 `bzmgcn.com`(死) → `bzmanga.com` |
| GoDa漫画 | 1.2.1→1.2.2 | web 域名 `godamh.com`(死) → `godamanga.com` |
| 优酷漫画 | 1.0.0→1.0.1 | 全量 `ykmh.net` → `ykmh.com` |
| comick | 1.2.0→1.2.1 | 全量 `comick.art` → `comick.io` |
| 紳士漫畫(wnacg) | 1.0.6→1.0.7 | 兜底默认域名 `wnacg.com` → `wnacg.org` |

## 其余源状态
- **域名经联网确认仍可用（未改）**：漫画柜、漫画人、CCC追漫台、再漫画、爱看漫、hitomi.la、禁漫天堂（运行时自动刷新域名）。
- **需登录/地区网络（代码无坏，取决于你的网络或账号）**：ehentai、MangaDex、Komiic、少年ジャンプ＋、カドコミ、MYCOMIC、嗨皮漫画。
- **自建服务器源（demo 地址为占位，需填自己的）**：Lanraragi、Komga、Kavita。
- **硬编码域名、未核实当前是否存活（建议 App 内实测）**：漫画1234、18漫画、漫小肆、漫蛙吧、H-Comic、jcomic.net、热辣漫画。

## 使用方式
将本仓库作为本地漫画源目录导入 Venera，或在 App 内逐个「导入本地 .js」。
⚠️ 导入后**关闭自动更新**：`.js` 里的 `url` 仍指向 jsdelivr CDN，自动更新会把修复版覆盖回官方旧版。

## 说明
- 修复依据：代码静态审计 + 联网查证当前域名。沙箱网络屏蔽大部分站点，无法真机联调，建议导入后重点自测搜索/打开/看图三处。
- `index.json` 中的版本号已与各 `.js` 实际 `version` 字段同步。
