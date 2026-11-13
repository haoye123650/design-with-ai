# Design with AI — 公开发布版 hub

这个文件夹里的东西**可以直接丢到 GitHub Pages**，传上去就是能用的网站。

## 里面有什么

| 文件 | 作用 |
|---|---|
| `index.html` | 网站本体（单文件，无外部依赖，不用改路径） |
| `robots.txt` | 防索引（**注意**：project 子路径下爬虫不读它，真正生效的是 HTML 里的 meta 标签） |
| `.nojekyll` | 关掉 GitHub 的 Jekyll 处理，避免莫名其妙的构建问题 |

## 和设计稿的区别（`../hub-preview.html`）

| | 设计稿 | 这一版 |
|---|---|---|
| 学生名 | Cooper Mao / Lucas Wu … | **C. Mao / L. Wu …**（只留首字母 + 姓氏）|
| 防索引 | 无 | `<meta name="robots" content="noindex, nofollow">` |
| 分享元信息 | 无 | og:title / og:description（发给家长时能出预览卡片）|
| 老师中文名 | Sam Zhang 张恩豪 | 只留 Sam Zhang |
| 里程碑状态 | PRE-W1 和 W4 都标"已完成" | PRE-W1 已完成，**W4 标为"当前"** |
| 手机适配 | 无 | 加了 640px 断点（导航、表格、间距）|
| 隐私条款 | 2 条 | 6 条，新增"只显示首字母缩写""本页未公开发布" |

**为什么用首字母缩写**：GitHub Pages 免费账号只能挂公开仓库，全名会公开且被搜索引擎收录，而且删掉也没用——commit 历史会留存。缩写既解决这个问题，视觉上也更整齐。

---

## 发布步骤（5 步，约 5 分钟）

1. 注册 / 登录 [github.com](https://github.com)
2. 右上 **+** → **New repository**
   - Repository name: `design-with-ai`
   - 选 **Public**（免费账号必须公开才能用 Pages）
   - 点 **Create repository**
3. **Add file** → **Upload files** → 把 `index.html`、`robots.txt`、`.nojekyll` **三个文件一起拖进去**
   - 注意 `.nojekyll` 是隐藏文件，macOS 里按 `Cmd + Shift + .` 才能看到
   - 如果拖不进去就跳过它，不影响
   - 然后点 **Commit changes**
4. **Settings** → 左侧 **Pages**
   - Source: `Deploy from a branch`
   - Branch: **main** / 文件夹选 **/ (root)**
   - 点 **Save**
5. 等 1–2 分钟，刷新这个页面，顶部会出现网址：

```
https://你的用户名.github.io/design-with-ai/
```

---

## 以后怎么更新（每 2–3 周一次）

1. 在仓库页点 `index.html` → 右上铅笔图标（编辑）
2. 改学生 tile 的状态文字，比如把 `<div class="status">coming soon</div>` 改成 `<div class="status">W4 &middot; Portrait</div>`
3. 底部 **Commit changes**
4. 等 1 分钟自动生效

**加图片时**：把图片一起传到仓库（比如建个 `img/` 文件夹），然后 tile 里写
`<img src="img/xxx.jpg" style="width:100%;border-radius:8px">`。
**别用本机绝对路径**，线上找不到。
学生作品放进 `students/<slug>/`（例如 `work-1.jpg`），在该页对应格子里启用预留的 `<img>` 或 `<video>`。

---

## ⚠️ 上线前必做两件事

**1. 用教室那台电脑实测能不能打开**

`*.github.io` 在国内访问不稳定。你 Mac 上能打开不代表教室网络能打开——上课要投屏的话，这个必须提前验证。

打不开的话有两手准备：
- 换 Cloudflare Pages（同样是免费静态托管，国内相对稳）
- 或者放到你自己的阿里云（最稳，但要绑备案域名；注意阿里云 OSS 默认域名访问 HTML 会强制下载，必须用自定义域名）

**2. 确认学生名用缩写这件事，可以跟学校报备一下**

理由很干净："公开页面只显示首字母缩写，无全名、无照片、无联系方式，且已设置不被搜索引擎收录。"

---

## 最后一步（可选）

上线后如果发现要**给家长看**而不是给公众看，还有更稳的做法：
把仓库改成 **私有**（需要 GitHub Pro，约 $4/月），Pages 就会变成"只有拿到链接的人能看"，
比公开发布更适合学生内容。或者干脆走 Google Sites 的 share-with-link。
