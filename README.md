# 透明物理幕布 · 手势交互

基于 p5.js 和 MediaPipe Hands 的透明物理幕布手势交互网页应用。

## 核心概念

屏幕里挂一块隐形的布，表面是摄像头实时画面（布完全看不见），背后藏着上传的图或视频。手在空中 pinch（拇指食指捏合）抓住布，甩起或放下——掀开的瞬间，背后画面被揭示。

## 技术特性

### 光学伪装
三层渲染架构：
- **底层**: 全屏摄像头画面
- **中层**: 上传的媒体（图片/视频）
- **顶层**: 布料剪切层，使用 `ctx.clip()` 实现透明效果

### Verlet 布料物理
- 网格: 38×35
- 顶端 pin 住
- 摩擦力: 0.94
- 重力: 0.08
- 约束迭代: 12 次
- 刚度: 0.4

### 手势识别
- MediaPipe Hands 双手同时操作
- pinch 距离计算带防抖
- 抓取半径: 150px

## 快速开始

### 在线体验
访问 [GitHub Pages](https://[你的用户名].github.io/[仓库名]/) 直接体验

### 本地运行

```bash
# 克隆仓库
git clone https://github.com/[你的用户名]/[仓库名].git
cd [仓库名]

# 启动 HTTP 服务器
python -m http.server 8000
```

然后在浏览器中访问 `http://localhost:8000`

## 使用方法

1. **启动应用**: 点击 Start 按钮，允许摄像头权限
2. **手势交互**: 
   - 使用拇指和食指捏合（pinch）抓住布料
   - 移动手来拖动布料
   - 松手后布料自然下垂

## 技术栈

- **p5.js**: 1.10.0
- **MediaPipe Tasks Vision**: 0.10.0
- **Canvas 2D API**

## 浏览器兼容性

| 浏览器 | 支持 | 备注 |
|--------|------|------|
| Chrome | ✅ | 推荐 |
| Firefox | ✅ | 需要 HTTPS |
| Safari | ✅ | 需要 HTTPS |
| Edge | ✅ | 推荐 |

## 注意事项

1. 需要浏览器摄像头权限
2. HTTPS 环境下功能更完整
3. 移动端需要禁止滚动（已设置 `touch-action: none`）

## 许可证

MIT License

## 作者

Created with ❤️ using p5.js and MediaPipe