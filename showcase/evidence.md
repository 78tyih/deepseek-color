# Evidence — deepseek-color

Updated: 2026-10-05

## Observed（实查）

| 声明 | 证据 |
|---|---|
| 5 套色卡存在且含 5 色 | `templates/palettes/palettes.json`（结构化数据）+ `p1–p5 *.html/*.png` |
| 12 个版式骨架 | `templates/*.html` 12 个文件（10 骨架 + 2 分享海报） |
| 骨架零本地依赖 | grep 全部 templates：0 个 `../` 引用，仅 Google Fonts CDN（1–2 处） |
| 8 个换肤实例 | `templates/skins/*.html` 8 个（5×hero + 3 组合） |
| 在线渲染可用 | docs/ 副本经 GitHub Pages 提供服务；showcase 的 iframe 直接加载仓库文件（上线后 curl 验证 200） |

## Inferred（自述/目检，附复核方式）

| 声明 | 复核方式 |
|---|---|
| 换肤 = 覆盖 6 个 CSS 变量 | 逐个 diff skins/*.html 的 `:root` 块；未用工具断言 |
| 可安装到 4 个 Agent 平台 | README 安装路径为文档自述，未在每平台端到端跑通 |
| 配色纪律 70/25/5 在非 DeepSeek 色系同样成立 | 方法论推断，未做反例实验 |

## Unknown

- 「改 1 个变量全站换强调色」在 12 个骨架上是否 100% 生效（抽检 hero/poster，未逐页验证）
- 各骨架在移动端 viewport 的表现（模板未声明响应式断点）
