# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 运行方式

- 无需构建，直接用浏览器打开 `index.html` 即可
- 无依赖、纯静态前端，不依赖任何后端或 API

## 架构概览

单文件应用，`index.html` 内嵌 CSS 和 JS，三部分：

1. **CSS** — 星空动画背景、星座网格、详情面板、响应式布局
2. **HTML** — 由 JS 动态渲染（星座网格、运势详情、空状态提示）
3. **JS** — 数据定义 + 运势生成 + DOM 渲染

## 核心数据结构

- `SIGNS[]` — 12 星座元数据（名称、符号、日期范围、元素属性、主题色）
- `ASPECTS[]` — 四大运势维度（爱情/事业/财运/健康），每个维度包含多组描述模板

## 运势生成逻辑

- `seedRandom(seed)` — 基于字符串种子的确定性伪随机数生成器
- `getDaySeed()` — 以当日日期（年月日）作为种子，保证同一天同一星座生成相同结果
- `generateFortune(sign)` — 为指定星座生成完整运势，包含综合评分、四维度评分与描述、幸运元素、每日建议
- 评分范围 55-100，星级按 5 分一档换算

## 可用 Skills

| 命令 | 用途 |
|---|---|
| `/run` | 在浏览器中打开 index.html 预览效果 |
| `/verify` | 验证代码改动是否在浏览器中正确生效 |
| `/code-review` | 审查代码变更，检查潜在问题 |
