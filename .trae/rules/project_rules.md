# 项目规则

本规则适用于本仓库（siyabo）中的所有代码，生成或修改任何文件时必须遵守。

## 命名规范

- **JavaScript 变量名**：必须以 `syb_` 开头（如 `syb_name`、`syb_age`、`syb_isConfirm`）
- **CSS 类名**：必须以 `syb_` 开头（如 `syb_header`、`syb_btn-primary`）
- **HTML id 名称**：必须以 `syb_` 开头（如 `syb_main`、`syb_form`）

## HTML 页面注释

- 每个 HTML 页面必须在文件中包含如下格式的注释（日期为创建或修改页面的当天日期）：

```html
<!--
姓名：司雅博
日期：2026.10.22
-->
```

- 注释建议放在 `<!DOCTYPE html>` 之后、`<html>` 标签之前
- 修改已有页面时，更新注释中的日期为修改当天

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
