# Pixel Story Switch

把开关的滑轨变成一段可以拖着看的像素故事。滑块是一颗玻璃透镜，经过窗框、书架或人物时，会放大并折射底下的画面。

示例 **《窗里 · 雨夜》** 从晴天的电脑桌开始。往右拖，人物起身走到床边，天色变暗，窗上开始落雨。拨回左边，人物起床走回电脑前。拖到半途也能停住看当前姿势。

[查看示例文件](assets/demo.html) · [阅读 Skill 指南](SKILL.md)

## 在 Codex 中使用

将这个仓库克隆到 Codex 的个人技能目录 `~/.codex/skills/pixel-story-switch`。在 Windows PowerShell 中可以运行以下命令。

```powershell
git clone https://github.com/karenlamb6082-ctrl/pixel-story-switch.git (Join-Path $env:USERPROFILE '.codex/skills/pixel-story-switch')
```

在 Codex 中输入类似这样的请求。

> 用 $pixel-story-switch 做一个小咖啡店的开关。白天店员擦杯子，往右拖时收拾柜台，夜里挂上打烊牌。

克隆后也可以直接在浏览器中打开 `assets/demo.html`。示例是单文件 HTML，支持拖动、点击和方向键，不需要联网或安装运行依赖。

玻璃滑块与微缩房间的组合参考了 [Ian 的开关演示](https://x.com/ianneo_ai/status/2119712336558878871)及其[公开技术提示词](https://x.com/ianneo_ai/status/2119712343022359000)。本仓库的像素画面和交互由代码绘制。
