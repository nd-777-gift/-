# 🎨 3D 图片轮播展示

一个炫酷的 3D 图片切换效果展示项目，部署在 Cloudflare Workers 上。

## ✨ 功能特点

- ✅ **3D 动画效果** - 炫酷的图片切换动画
- ✅ **多图轮播** - 支持无限数量的图片轮播
- ✅ **屏幕自适应** - 完美适配手机、平板、桌面等各种屏幕
- ✅ **响应式设计** - 自动适应横屏/竖屏
- ✅ **交互控制** - 鼠标拖动控制动画，按键暂停
- ✅ **全球 CDN 加速** - Cloudflare 全球节点加速访问

## 📁 项目结构

```
afa/
├── index.html                   # 入口页面
├── _headers                     # Cloudflare 头部配置
├── _redirects                   # 重定向配置
├── pictures/                    # 图片文件夹
│   ├── preview.jpg
│   ├── preview2.jpg
│   ├── preview3.jpg
│   └── preview4.jpg
└── sss.ss/image-3D/
    ├── weixin.html              # 主页面（多图轮播）
    ├── qiehuan3860.js           # 主逻辑
    ├── images-config.js         # 图片配置
    ├── three.min.js             # Three.js 库
    ├── TweenMax.min.js          # 动画库
    ├── bas.js                   # 动画系统
    └── OrbitControls-2.js       # 控制器
```

## 🌐 在线访问

**部署地址**：`https://wangye.361465902.workers.dev/`

## 📸 添加新图片

### 方法：手动编辑配置文件

编辑 `sss.ss/image-3D/images-config.js` 文件：
```javascript
var imagesList = [
    '../../pictures/preview.jpg',
    '../../pictures/preview2.jpg',
    '../../pictures/preview3.jpg',
    '../../pictures/preview4.jpg',
    '../../pictures/your-new-image.jpg',  // 添加新图片
];
```

然后重新上传到 Cloudflare Workers。

## 🎮 操作说明

- **🖱️ 鼠标拖动** - 手动控制动画进度
- **👆 触摸拖动** - 移动端触摸控制
- **⌨️ 按 P 键** - 暂停/继续播放
- **🔄 自动循环** - 播放完所有图片后自动重新开始

## 📱 屏幕适配

项目已针对不同设备进行优化：

| 设备类型 | 屏幕宽度 | 图片缩放 | 相机距离 |
|---------|---------|---------|---------|
| 🖥️ 桌面 | >1024px | 1.5x | 60 |
| 📱 平板 | 768-1024px | 1.2x | 55 |
| 📱 手机 | <768px | 1.0x | 50 |

## 🖼️ 支持的图片格式

- `.jpg` / `.jpeg`
- `.png`
- `.gif`
- `.webp`

## 🔧 自定义配置

### 调整动画速度

编辑 `sss.ss/image-3D/qiehuan3860.js`（第 75-79 行）：
```javascript
tl = new TimelineMax({
    repeat: -1,
    repeatDelay: 1.0,  // 修改这个值（秒）
    onRepeat: onAnimationRepeat
});
```

### 调整图片尺寸

编辑 `sss.ss/image-3D/qiehuan3860.js`（第 26-28 行）：
```javascript
var baseWidth = 40;   // 基础宽度
var baseHeight = 55;  // 基础高度
```

## 🛠️ 技术栈

- **Three.js** - 3D 渲染引擎
- **TweenMax (GSAP)** - 动画库
- **BAS** - 顶点动画系统
- **Cloudflare Workers** - 全球 CDN 部署

## 🚀 部署到 Cloudflare Workers

### 步骤：

1. 访问 [Cloudflare Workers](https://workers.cloudflare.com/)
2. 创建新的 Worker
3. 上传所有项目文件
4. 设置资产目录为 `/`
5. 点击部署

详细说明请查看 `Cloudflare部署指南.md`

## 📝 注意事项

1. **图片优化**：建议单张图片 < 500KB，使用 [TinyPNG](https://tinypng.com/) 压缩
2. **图片比例**：建议使用相同比例的图片，效果更统一
3. **浏览器兼容**：支持 Chrome、Firefox、Safari、Edge 等现代浏览器

## 🎯 性能优化

- ✅ 只加载当前和下一张图片
- ✅ WebGL 硬件加速
- ✅ Cloudflare CDN 全球加速
- ✅ 自动缓存策略（图片 30 天，JS 7 天）

## 📄 许可证

本项目仅供学习和个人使用。

---

**享受你的 3D 图片展示之旅！** 🎉✨

