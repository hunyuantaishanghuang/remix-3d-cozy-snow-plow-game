# Cozy Plow · 治愈扫雪星球 (雪かき惑星)

一款基于 **Three.js** 与 **程序化 WebAudio 音频引擎** 构建的 3D 微型球体扫雪与 Boss 激战游戏，支持单人畅玩与 **WebSocket 多人实时联机协作**。

---

## ✨ 游戏特色

- **3D 球面重力与物理扫雪**：在 135,000 簇蓬松积雪覆盖的微型星球（樱雪星、抹茶星、极光星）上自由驾驶，实时开辟雪道并将积雪卷入身后的巨型雪球中。
- **4 位专属扫雪驾驶员**：
  - 🦊 **小狐狸 绀酱 (Kon-Chan)** — 狐火螺旋：引爆 360° 狐火旋风，大范围融雪并灼烧附近 Boss。
  - 🐻 **巨熊 铁男 (Kuma-Tetsu)** — 千钧践踏：液压重踏冲击波，震碎周围积雪并眩晕范围内的 Boss。
  - 🐰 **雪兔 诺瓦 (Usagi-Nova)** — 极光冲刺：200% 超音速极光滑行，低温冰刃开辟超宽雪道。
  - 🐸 **蛤蟆 仙人 (Gama-Sennin)** — 蛤蟆吸积风暴：召唤忍术漩涡，将四周积雪瞬间吸入雪球。
- **Boss 蓄力破招机制**：迎战赤鬼推土兽、寒霜巨魔像、黑羽天狗、雪国大将军。当 Boss 进入蓄力预警（⚠️）时，按 `[空格键]` 掷出雪球即可触发 **蓄力反击破招 (Counter Breaker)**，造成高额伤害并使其眩晕！
- **程序化治愈系环境音乐**：零外部音频依赖，纯 WebAudio 实时合成的毛毡钢琴、钢片琴、温暖合成器铺底与清脆踏雪音效。
- **WebSocket 4人联机协作**：支持创建房间码、复制邀请链接与好友同屏扫雪、合击 Boss。

---

## 🎮 操作说明

| 按键 | 功能 |
| :--- | :--- |
| `W / A / S / D` 或 `方向键` | 控制扫雪车在星球表面行驶转向（移动端支持右下角虚拟摇杆） |
| `空格键 (Space)` 或 `鼠标左键` | **通用雪球猛掷**：向前掷出拖拽的雪球（雪球越大伤害越高，可打断 Boss 蓄力） |
| `E` | **驾驶员专属绝技**：释放当前角色的特技并获得加速与范围清雪 |
| `1` / `2` | 消耗星星金币升级 **铲刀宽度** / **行驶速度**（最高 Lv.6） |
| `F1 ~ F4` | 快速切换 4 位驾驶员 |
| `P` | 打开多人联机房间面板 |
| `I` | 展开 / 收起无尽周目统计与 8 项成就面板 |
| `M` | 切换音乐 / 静音 |
| `H` | 隐藏 / 显示游戏界面 (HUD) |
| `N` | 当积雪清除达到 90% 且击败当前关卡所有 Boss 后，进入下一关 |
| `Q` | 打开本轮结算战报 |

---

## 🚀 本地运行与构建

### 1. 安装依赖
```bash
npm install
```

### 2. 启动开发服务器（含多人联机 WebSocket 后端）
```bash
npm run dev
```
启动后访问 `http://localhost:3000`。

### 3. 构建生产版本
```bash
npm run build
```

---

## 📦 部署到你的 GitHub 仓库与 GitHub Pages

本项目已内置 `.github/workflows/deploy.yml` 自动部署工作流，推送到你的 GitHub 仓库后即可自动发布到 **GitHub Pages**。

### 方式一：在 AI Studio 右上角一键导出到 GitHub（推荐）
1. 点击 AI Studio 界面右上角的 **Export / GitHub 图标**。
2. 授权你的 GitHub 账号，输入新仓库名称（例如 `cozy-plow-cn`），点击创建并推送。
3. 打开你的 GitHub 仓库页面，进入 **Settings → Pages**。
4. 在 **Build and deployment → Source** 下拉菜单中选择 **GitHub Actions**。
5. 等待 Actions 自动构建完成（约 1 分钟），即可通过 `https://<你的GitHub用户名>.github.io/<仓库名>/` 在线游玩！

### 方式二：使用 Git 命令行推送到你的 GitHub
如果你将代码下载到了本地，或者在终端中配置了 GitHub 远程仓库：

```bash
# 1. 初始化 Git 仓库并提交代码
git init
git add .
git commit -m "feat: 汉化治愈扫雪星球并配置 GitHub Pages 自动部署"

# 2. 绑定你在 GitHub 上新建的空仓库地址（请替换为你的用户名和仓库名）
git branch -M main
git remote add origin https://github.com/<你的GitHub用户名>/<你的仓库名>.git

# 3. 推送到 GitHub
git push -u origin main
```

> **提示**：GitHub Pages 静态托管模式下，游戏会自动以 **单人 + AI 队友模式** 流畅运行；如需启用 **WebSocket 多人实时联机**，可将整个项目一键部署至 Render、Railway、Fly.io 或 Google Cloud Run（运行命令 `npm start`）。
