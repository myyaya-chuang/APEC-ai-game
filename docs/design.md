# APEC AI 特别行动队 — H5 小游戏设计文档

**日期:** 2026-06-23  
**技术:** 单文件 HTML + CSS + JS  
**风格:** 像素小游戏  

---

## 项目结构

```
APEC-ai-game/
├── index.html              ← 游戏主文件（所有代码）
├── assets/
│   ├── images/             ← 用户替换素材处
│   └── audio/              ← 用户替换音效处
└── docs/
    └── design.md           ← 本文档
```

## 5屏流程

| 屏 | 内容 | 交互 | 素材 |
|----|------|------|------|
| Screen1 | APEC组委会消息 → 接单按钮 | 点击 | bg-screen1.png |
| Screen2 | 4人物卡点击选3人 → 组队确认 | 点击选中/取消 | char-*.png, bg-screen2.png |
| Screen3 | 3个危机事件依次出现，每题3选1 | 点击选项 | bg-screen3.png, emoji |
| Screen4 | 交付动画（装车→地标→会场→机器人） | 自动播放 | bg-screen4.png, char-robot.png, emoji |
| Screen5 | 总分→称号→Canvas海报→重玩/分享 | 点击按钮 | bg-screen5.png |

## 计分

- 每个事件3选项对应属性(AI/产能/国际化/效率)
- 队里有对应属性人物 → 基础分 + 3
- 总分 0-39 → 4档称号

## 防止出错的简化决策

- 只用点击，不用拖拽
- 3个事件固定，顺序随机
- Canvas海报：称号文字 + 小图标，极简
- 所有素材路径集中定义在 JS 顶部常量区
- HTML注释标记每个素材替换点
- 不使用任何外部依赖/框架

## 海报（简单版）

- Canvas 尺寸: 750×1000
- 内容: 底部背景色块 + 称号文字 + 机器人小图标
- 手机端长按/点击保存

## 移动端适配

- viewport: width=device-width
- 游戏容器 max-width: 480px, 居中
- 按钮最小点击区域 44×44px
