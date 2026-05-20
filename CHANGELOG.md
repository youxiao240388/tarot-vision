# 更新日志 (Changelog)

所有重要版本的变更记录。

---

## [v5.2] - 2026-05-20

### ✨ 新增功能

#### Bloom 辉光后处理
- 集成 Three.js `EffectComposer` + `RenderPass` + `UnrealBloomPass` 后处理管线
- UnrealBloomPass 参数：threshold 0.15 / strength 0.8 / radius 0.6
- ACES 色调映射 + 1.2x 曝光控制
- 辉光随音乐节奏脉动（±0.3 strength），实现「呼吸感」光效

#### 高级字体系统
- 引入 Google Fonts：**Cinzel**（英文标题/界面）、**Cormorant Garamond**（英文正文）、**Noto Serif SC**（中文衬线）
- 添加 `preconnect` 预连接优化加载
- 启用字体抗锯齿（`-webkit-font-smoothing: antialiased`）
- 字体 fallback 链：Cinzel → Noto Serif SC → Constantia → Palatino → Microsoft YaHei

#### CSS 设计系统
- 新增 16 个 CSS 自定义属性（design tokens）：
  - 颜色层级：`--gold-dim`, `--gold-glow`, `--purple-deep/mid/light`
  - 表面层级：`--surface-1`, `--surface-2`, `--panel-bg-strong`
  - 边框状态：`--border-subtle`, `--border-active`
  - 文字层级：`--text-primary`, `--text-secondary`, `--text-muted`
  - 阴影系统：`--shadow-deep`, `--shadow-glow`
  - 过渡曲线：`--transition-smooth`, `--transition-bounce`

### 🎨 改进

#### 卡片背面 Shader 升级
- 浮雕法线扰动（diamond pattern emboss）— 卡背呈现立体浮雕质感
- 流光扫过效果（time-driven sweep line）— 光线从上到下周期性扫过
- 暗纹呼吸（breathing dark pattern）— 暗部纹理随时间明暗交替
- 紫色边缘辉光（fresnel edge glow）— 卡片边缘呈现紫色光晕

#### 牌面程序化生成增强
- 7-stop 渐变背景 + 中心径向辉光
- 对角线纹理（diagonal texture lines）增加层次感
- 三层边框系统：外层金线 + 中层细线 + 内层虚线
- 顶部/底部菱形装饰标记

#### 粒子系统升级
- 200 颗金色星尘粒子（漫天飘浮 + 音乐响应亮度变化）
- 抽牌能量光束（金色竖向 beam + 扩散消散动画）
- 保留原有灰烬/火焰效果

#### UI 组件全面打磨
- 音乐面板：更强的毛玻璃效果（`backdrop-filter: blur(24px) saturate(1.2)`）+ `inset` 高光
- 滑块控件：增加悬停态和光晕效果
- 下拉选择器：统一样式，增加交互反馈
- 音频频谱条：渐变色背景替代纯色
- 按钮：增加 sweep 光效动画 + bounce 过渡曲线
- 开始屏幕：增加径向暗角遮罩

### 🔧 技术变更
- 背景色从 `#050505` → `#020202` → `#010101`（更深的纯黑）
- 启始画面背景：多层径向渐变替代单层
- 文件体积：778KB → 802KB（+24KB 为 Bloom 模块）
- 新增 Google Fonts CDN 依赖（离线时 fallback 到系统字体）

### 🐛 修复
- 面板悬停边框突变 → 使用 `var(--transition-smooth)` 平滑过渡
- 音量滑块视觉反馈不足 → 增加 hover 态背景变化和拇指光晕
- 频谱条过于生硬 → 改为渐变色 + 更小的圆角

---

## [v5.1] - 2026-05-19

### ✨ 新增
- 程序化牌面生成（替代外部图片，78张牌全部 Canvas 绘制）
- 程序化环境音乐（替代外部音频，Web Audio API 合成）
- 手势状态机（防误触冷却机制）
- Three.js 内联（离线可用，无外部脚本依赖）
- 返回主界面按钮
- 视觉效果优化

---

## [v5.0] - 2026-05-18

### ✨ 新增
- MediaPipe Hands 实时手势追踪
- Three.js 3D 卡牌渲染
- GLSL 全息着色器
- 音频频谱可视化
