# 项目规则

> 本规则的完整源文件是项目根目录的 `agent.md`，以 agent.md 为准。

## 命名规范

- **JavaScript 变量名**（含函数名）：必须以 `syb_` 开头（如 `syb_name`、`syb_isPass`）
- **CSS 类名**：必须以 `syb_` 开头（如 `syb_header`、`syb_btn-primary`）
- **HTML id 名称**：必须以 `syb_` 开头（如 `syb_main`、`syb_form`）

## 新建 HTML 文件的注释规则

每新建一个 HTML 文件，必须在 `<!DOCTYPE html>` 之后、`<html>` 标签之前加入如下格式的注释：

```html
<!--
姓名：司雅博（syb）
建立时间：2026.10.26
使用的大模型：GLM
功能名称：<本页面的功能描述>
-->
```

- **姓名**：固定为 司雅博（syb）
- **建立时间**：文件创建当天的日期，格式 YYYY.MM.DD
- **使用的大模型**：创建该文件时所用的 AI 大模型名称
- **功能名称**：一句话描述页面功能（如"数7游戏"、"六种数据类型演示"）

## 技术栈限制

- 只使用**原生** HTML、CSS 和 JavaScript 实现，禁止引入任何第三方库和 CDN 资源（如 jQuery、Bootstrap、FontAwesome 在线版、lodash 等）
- 仓库中已存在的 `cdn/` 目录（FontAwesome、lucide）不再在新页面中使用
- 需要图标时，使用 `font/download/font_5244786_2soxe0r4aqo/` 目录下的本地 iconfont 图标：

```html
<!-- 引入样式 -->
<link rel="stylesheet" href="font/download/font_5244786_2soxe0r4aqo/iconfont.css">

<!-- 使用图标：class 为 iconfont icon-图标名 -->
<span class="iconfont icon-yingyong"></span>
```

- 可用图标（共 4 个）：`icon-yingyong`（应用）、`icon-wangluo`（网络）、`icon-jinbi_o`（金币）、`icon-xiaochengxu`（小程序）
- 例外：iconfont 自带的 `iconfont`、`icon-*` 类名是本地字体库的固定类名，不受 `syb_` 前缀规则约束
