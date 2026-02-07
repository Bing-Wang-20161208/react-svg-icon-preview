# React SVG Preview

一款 VS Code / Cursor 扩展，为 React SVG 图标组件提供**行内预览**和**悬停预览**功能。

## 功能特性

- **行内图标预览**：在编辑器侧边栏（gutter）中，直接显示 SVG 图标缩略图
- **悬停预览**：鼠标悬停在 SVG 组件上时，显示更大尺寸的预览图
- **多种格式支持**：兼容常见的 React 组件写法：
  - 标准函数组件
  - 箭头函数组件
  - forwardRef 包裹的组件
  - memo 包裹的组件

## 支持的组件模式

```tsx
// 模式 1：标准函数组件
export function IconName() {
  return <svg>...</svg>
}

// 模式 2：箭头函数组件
export const IconName = () => <svg>...</svg>

// 模式 3：forwardRef（常见于设计系统）
export const IconName = forwardRef<'svg', IconProps>((props, ref) => {
  return <Icon viewBox="0 0 16 16">...</Icon>
})

// 模式 4：memo
export const IconName = memo(() => <svg>...</svg>)
```

## 配置项

| 配置项 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `reactSvgPreview.enabled` | boolean | `true` | 启用 / 禁用扩展 |
| `reactSvgPreview.iconSize` | number | `16` | 行内图标预览尺寸（px） |
| `reactSvgPreview.showInlineIcon` | boolean | `true` | 是否显示侧边栏行内图标 |
| `reactSvgPreview.showHoverPreview` | boolean | `true` | 是否显示悬停预览 |
| `reactSvgPreview.hoverPreviewSize` | number | `64` | 悬停预览尺寸（px） |
| `reactSvgPreview.defaultFillColor` | string | `#888888` | `currentColor` 的默认填充颜色 |

## 命令

- **Toggle React SVG Preview**：启用 / 禁用预览
- **Refresh React SVG Preview**：刷新并重新扫描当前文件

## 安装方式

### 通过 VSIX 安装

1. 从 Releases 页面下载 `.vsix` 文件
2. 在 VS Code / Cursor 中：扩展 → 点击右上角 `...` → 选择「从 VSIX 安装...」

### 从源码构建

```bash
# 安装依赖
npm install

# 编译
npm run compile

# 打包
npm run package

# 安装生成的 .vsix 文件
code --install-extension react-svg-preview-0.1.0.vsix
# 如果使用 Cursor
cursor --install-extension react-svg-preview-0.1.0.vsix
```

## 开发调试

```bash
# 启动监听模式
npm run watch

# 在 VS Code 中按 F5 启动扩展开发宿主窗口
```

## 许可证

MIT
