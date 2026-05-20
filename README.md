# 🃏 塔罗·灵境 | Tarot Vision V5.2

一个沉浸式塔罗牌占卜 Web 应用，支持手势交互和鼠标交互，程序化生成全部视觉与音频内容。

## ✨ 功能特性

- **🃏 78张完整塔罗牌** — 22张大阿卡纳 + 56张小阿卡纳，Canvas 程序化生成，每张牌有独特符号
- **🌟 Bloom 辉光效果** — Three.js UnrealBloomPass 后处理管线，全局辉光随音乐脉动
- **🖐️ 手势交互** — MediaPipe Hands 实时手势追踪（捏合翻牌、握拳归位、挥手切换视图）
- **🖱️ 鼠标交互** — 点击翻牌、双击归位、拖拽跟随
- **🎵 程序化音乐** — Web Audio API 生成神秘氛围环境音乐（Am和弦drone + shimmer + 心跳脉冲）
- **✨ 3D渲染** — Three.js 驱动的卡牌3D渲染、全息着色器、粒子特效
- **🔮 占卜牌阵** — 三张牌阵（现在/过去/远古），含燃烧归位动画
- **📖 全牌画廊** — 78张牌的完整浏览画廊
- **🌐 离线可用** — 单HTML文件，除MediaPipe模型外零外部依赖

## 🛠️ 技术栈

| 技术 | 用途 | 体积 |
|------|------|------|
| Three.js r160 | 3D场景渲染、GLSL着色器、粒子系统 | 654KB (内联) |
| Three.js Postprocessing | EffectComposer + UnrealBloomPass 辉光后处理 | ~40KB (内联) |
| MediaPipe Hands | 实时手势识别（WASM + 神经网络模型） | ~3MB (CDN) |
| Web Audio API | 程序化环境音乐生成、交互音效合成 | 11KB (内联) |
| Canvas 2D | 78张塔罗牌牌面程序化绘制 | 32KB (内联) |
| Google Fonts | Cinzel + Cormorant Garamond + Noto Serif SC | CDN |
| HTML5/CSS3 | 界面布局、动画、响应式设计 | - |
| 原生 JavaScript | 零框架依赖 | - |

## 📁 项目结构

```
tarot-vision/
├── README.md          # 项目说明
├── index.html         # 单文件应用（802KB，含所有内联依赖）
├── CHANGELOG.md       # 更新日志
└── LICENSE            # MIT 许可证
```

## 🚀 使用方式

1. 下载 `index.html`
2. 用现代浏览器打开（推荐 Chrome/Edge）
3. 允许摄像头权限（手势模式需要）
4. 点击「开启灵视」开始

### 操作方式

**手势模式：**
- 🖐️ 移动 — 牌跟随悬浮
- 👌 捏合 — 抽取/翻牌
- ✊ 握拳 — 归位/下一张
- 👋 挥手 — 切换聚焦视图

**鼠标模式：**
- 🖱️ 移动 — 牌跟随
- 🖱️ 左键点击 — 翻牌
- 🖱️ 双击 — 归位
- 🔲 右键 — 显隐摄像头

## 🎨 设计亮点

- **全局辉光** — UnrealBloomPass 后处理 + ACES 色调映射，辉光随音乐节奏脉动
- **高级字体** — Cinzel（标题/界面）+ Cormorant Garamond（正文）+ Noto Serif SC（中文）
- **设计系统** — 完整 CSS 自定义属性体系（颜色层级、阴影、过渡曲线）
- **卡片背面 Shader** — 浮雕法线扰动 + 流光扫过 + 暗纹呼吸 + 紫色边缘辉光
- **牌面生成升级** — 7-stop渐变背景 + 中心径向辉光 + 对角线纹理 + 三层边框 + 菱形装饰
- **粒子系统** — 200颗金色星尘 + 抽牌能量光束 + 灰烬/火焰效果
- **神秘紫色主题** — 深空星云背景 + 神圣几何光环
- **程序化音效** — 风铃(chime)、翻牌(flip)、燃烧(burn) 全部合成
- **状态机交互** — 防误触冷却机制，流畅的状态转换动画

## 📝 版本历史

### v5.2 (2026-05-20) — Visual Refinement
- 🌟 Three.js Bloom 辉光后处理（UnrealBloomPass + ACES色调映射）
- ✨ 卡片背面 Shader 升级（浮雕/流光/暗纹/边缘辉光）
- 🎨 牌面程序化生成增强（渐变/纹理/三层边框/菱形装饰）
- 💫 粒子系统升级（200颗星尘 + 能量光束）
- 🖋️ 高级字体系统（Cinzel + Cormorant Garamond + Noto Serif SC）
- 📐 完整 CSS 设计系统（design tokens + 自定义属性体系）
- 🔧 UI 组件全面打磨（面板/滑块/按钮/下拉框）

### v5.1 (2026-05-19)
- 程序化牌面生成（替代外部图片）
- 程序化环境音乐（替代外部音频）
- 手势状态机（防误触）
- Three.js 内联（离线可用）
- 返回主界面按钮
- 视觉效果优化

### v5.0
- MediaPipe Hands 手势追踪
- Three.js 3D 卡牌渲染
- GLSL 全息着色器
- 音频频谱可视化

## 📄 许可证

MIT License
