# GitHub Pages 部署指南

## 步骤 1: 创建 GitHub 仓库

### 仓库信息建议

**仓库名称建议：**
- `transparent-cloth` - 简洁明了
- `gesture-cloth` - 强调手势交互
- `physics-cloth` - 强调物理模拟

**仓库描述建议：**
```
基于 p5.js 和 MediaPipe 的透明物理幕布手势交互网页应用。
使用 pinch 手势控制隐形布料，揭示背后隐藏的媒体内容。
```

**仓库设置：**
- Public（公开）- 这样才能使用 GitHub Pages
- 不要初始化 README、.gitignore 或 license（我们已经有了）

## 步骤 2: 在 GitHub 上创建仓库

1. 访问 https://github.com/new
2. 填写仓库名称和描述
3. 选择 Public
4. 点击 "Create repository"

## 步骤 3: 连接本地仓库到 GitHub

```bash
# 替换为你的用户名和仓库名
git remote add origin https://github.com/[你的用户名]/[仓库名].git

# 推送到 GitHub
git branch -M main
git push -u origin main
```

## 步骤 4: 启用 GitHub Pages

1. 进入你的 GitHub 仓库
2. 点击 "Settings" 标签
3. 在左侧菜单中找到 "Pages"
4. 在 "Build and deployment" 下：
   - Source: 选择 "Deploy from a branch"
   - Branch: 选择 "main" 和 "/ (root)"
5. 点击 "Save"

## 步骤 5: 等待部署完成

- 几分钟后，GitHub 会自动部署你的网站
- 访问地址：`https://[你的用户名].github.io/[仓库名]/`

## 步骤 6: 验证部署

1. 访问你的 GitHub Pages URL
2. 点击 Start 按钮
3. 允许摄像头权限
4. 测试手势交互功能

## 常见问题

### Q: 为什么页面显示空白？
A: 确保你使用 HTTPS 访问，摄像头权限需要安全环境。

### Q: 手势识别不工作？
A: 检查浏览器控制台是否有错误，确保网络连接正常（需要加载 MediaPipe 模型）。

### Q: 如何更新网站？
A: 修改代码后：
```bash
git add .
git commit -m "更新描述"
git push
```
GitHub 会自动重新部署。

## 示例命令

```bash
# 假设你的用户名是 username，仓库名是 transparent-cloth
git remote add origin https://github.com/username/transparent-cloth.git
git branch -M main
git push -u origin main
```

部署后访问：`https://username.github.io/transparent-cloth/`

## 下一步

部署完成后，你可以：
1. 分享链接给朋友
2. 添加自定义域名
3. 添加更多功能（如媒体上传、UI改进等）
4. 提交到开源社区

需要帮助吗？告诉我你的 GitHub 用户名和仓库名，我可以帮你生成具体的命令！