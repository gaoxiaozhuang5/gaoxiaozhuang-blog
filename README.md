# 📦 博客已迁移

> **本仓库已停用。博客已迁移到根域名: <https://xiaozhuanggao.github.io/>**

---

## 迁移信息

| 项目 | 旧 | 新 |
|---|---|---|
| 仓库 | `xiaozhuanggao/blog` | `xiaozhuanggao/xiaozhuanggao.github.io` |
| 域名 | `xiaozhuanggao.github.io/blog/` | `xiaozhuanggao.github.io/` |
| Pages | 已禁用 | GitHub Actions workflow 自动部署 |
| CI | — | `.github/workflows/pages.yml` |

## 访问新博客

👉 **<https://xiaozhuanggao.github.io/>**

## 为什么迁移

把博客放在 GitHub 用户主页仓库(`xiaozhuanggao.github.io`),可以省掉 `/blog/` 前缀:

- 域名更短更好记
- 文章 URL 更简洁:`/2026/MM/DD/hash/` 而不是 `/blog/2026/MM/DD/hash/`
- 简历 PDF 直链:`/downloads/gaoxiaozhuang-resume.pdf`

## 旧链接兼容

GitHub Pages CDN 缓存过期后(10 分钟内),**旧 `/blog/` 链接将自动 404**。请更新书签为新域名。

如有人通过旧链接访问,GitHub 会返回 404。建议在外部链接中把 `xiaozhuanggao.github.io/blog/xxx` 替换为 `xiaozhuanggao.github.io/xxx`。

---

**作者**:高晓庄 <gaoxiaozhuang@bingosoft.net>
