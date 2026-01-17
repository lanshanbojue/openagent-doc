# 开源智能助手官网

> **赛博朋克终端风格** · 令人难忘的视觉体验 · 完全静态单文件

## 🎨 设计理念

这是一个**赛博朋克终端风格**的开源智能助手官网，采用独特的暗色系美学设计：

### 核心视觉特征

- **配色方案**：深黑(#0a0a0a) + 霓虹绿(#00ff41) + 等离子蓝(#00d4ff) + 警告橙(#ff6b00)
- **字体选择**：JetBrains Mono (编程字体) + VT323 (像素字体)
- **视觉元素**：
  - Matrix 数字流动态背景
  - CRT 扫描线效果
  - 故障艺术标题动画
  - 终端窗口风格组件
  - 悬浮3D卡片效果

### 差异化设计

✗ **避免**：紫色渐变、Inter字体、白色背景
✓ **采用**：终端美学、霓虹配色、像素字体、科技感动画

## 📦 页面结构

```
├── 导航栏 - 固定顶部，半透明模糊背景
├── Hero 区域 - 故障艺术标题 + 终端窗口
├── 功能特性 - 6个核心功能卡片（悬浮3D效果）
├── 下载中心 - 5个平台下载入口
├── 在线试用 - 模拟终端窗口
├── GitHub 社区 - 统计数据展示
└── 页脚 - 链接和版权信息
```

## 🚀 快速开始

### 本地预览

由于是纯静态 HTML 文件，最简单的预览方式：

```bash
# 使用 Python 内置服务器
python -m http.server 8017

# 或使用 Node.js
npx serve .

# 或直接用浏览器打开 index.html
```

访问：http://localhost:8017

### 部署到 GitHub Pages（免费 + 自定义域名）

#### 步骤 1：推送到 GitHub

```bash
# 1. 在 GitHub 创建新仓库（名称随意，如：open-agent-website）

# 2. 添加远程仓库（替换为你的仓库地址）
git remote add origin https://github.com/your-username/open-agent-website.git

# 3. 推送代码
git branch -M main
git push -u origin main
```

#### 步骤 2：配置自定义域名

1. **修改 CNAME 文件**

编辑 `CNAME` 文件，填入您的域名：
```
your-domain.com
# 或带 www
# www.your-domain.com
```

2. **提交 CNAME 文件**
```bash
git add CNAME
git commit -m "chore: 添加自定义域名"
git push
```

3. **在 GitHub 仓库设置中启用 Pages**

   - 进入仓库 → Settings → Pages
   - Source 选择: Deploy from a branch
   - Branch 选择: main / root
   - 保存

4. **配置域名 DNS**

在您的域名提供商添加 DNS 记录：

| 类型 | 名称 | 值 | TTL |
|------|------|-----|-----|
| A | @ | 185.199.108.153 | 3600 |
| A | @ | 185.199.109.153 | 3600 |
| A | @ | 185.199.110.153 | 3600 |
| A | @ | 185.199.111.153 | 3600 |
| CNAME | www | your-username.github.io | 3600 |

> GitHub Pages 的 4 个 IP 地址都要添加

5. **等待生效**

- DNS 传播通常需要 10分钟 - 48小时
- GitHub 仓库的 Pages 页面会显示状态
- 生效后访问 `https://your-domain.com`

#### 步骤 3：启用 HTTPS（可选但推荐）

在 GitHub Pages 设置中：
- Enforce HTTPS: 勾选
- GitHub 会自动配置 Let's Encrypt 证书

---

### 其他部署方式

#### Vercel

1. 将项目推送到 GitHub
2. 在 Vercel 中导入项目
3. 在 Vercel 设置中添加自定义域名

#### Cloudflare Pages（推荐，有国内加速）

1. 连接 GitHub 仓库
2. 自动部署
3. 添加自定义域名（免费 SSL）

## 🎯 功能特性

### 已实现

- [x] 响应式设计（移动端/平板/桌面）
- [x] Matrix 数字流背景动画
- [x] CRT 扫描线效果
- [x] 故障艺术标题动画
- [x] 滚动触发动画
- [x] 悬浮3D卡片效果
- [x] 终端打字效果
- [x] 平滑滚动导航
- [x] 下载统计埋点
- [x] 自定义滚动条

### 可扩展

- [ ] 国际化 (i18n)
- [ ] 深色/浅色主题切换
- [ ] 博客系统
- [ ] 用户反馈表单
- [ ] 分析统计集成

## 📝 自定义配置

### 修改配色

编辑 `<style>` 中的 CSS 变量：

```css
:root {
    --neon-green: #00ff41;      /* 主色 */
    --neon-cyan: #00d4ff;       /* 辅助色 */
    --warning-orange: #ff6b00;  /* 警告色 */
    --alert-red: #ff0040;       /* 错误色 */
}
```

### 更新下载链接

修改 JavaScript 中的 `downloadUrls` 对象：

```javascript
const downloadUrls = {
    windows: '你的下载链接',
    macos: '你的下载链接',
    // ...
};
```

### 修改 GitHub 统计

直接编辑 HTML 中的数字：

```html
<div class="stat-number">12.5K</div>
<div class="stat-label">Stars</div>
```

## 🔧 技术栈

- **纯 HTML5** - 语义化结构
- **CSS3** - 动画、Grid、Flexbox
- **原生 JavaScript** - Canvas 动画、交互
- **无依赖** - 零框架，零构建工具

## 📐 设计规范

### 字体使用

- **标题**：VT323 (像素字体，大号标题)
- **正文**：JetBrains Mono (等宽编程字体)
- **代码**：JetBrains Mono

### 间距系统

- 容器边距：3rem (桌面) / 1.5rem (移动)
- 卡片间距：2rem
- 章节间距：8rem

### 动画时长

- 快速交互：0.3s
- 页面过渡：0.4s
- 循环动画：2-3s

## 🌐 浏览器支持

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ⚠️ IE 不支持

## 📄 许可证

MIT License - 自由使用和修改

---

**Made with** 💚 **by the Open Source Community**
