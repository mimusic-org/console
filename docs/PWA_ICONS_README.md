# PWA 图标生成指南

MiMusic 的 PWA 功能需要以下图标文件：

## 所需图标

1. **icon-192x192.png** - 192x192 像素的应用图标
2. **icon-512x512.png** - 512x512 像素的应用图标  
3. **apple-touch-icon.png** - 180x180 像素的 iOS 图标

## 生成方法

### 方法一：使用在线工具（推荐）

访问 [RealFaviconGenerator](https://realfavicongenerator.net/)：

1. 上传 `web/src/assets/logo.svg` 文件
2. 选择 PWA 图标选项
3. 下载生成的图标包
4. 将以下文件复制到 `web/public/` 目录：
   - `icon-192x192.png`
   - `icon-512x512.png`
   - `apple-touch-icon.png`

### 方法二：使用 ImageMagick

如果已安装 ImageMagick，可以使用命令行生成：

```bash
# 进入 web 目录
cd web

# 生成 192x192 图标
convert src/assets/logo.svg -resize 192x192 public/icon-192x192.png

# 生成 512x512 图标
convert src/assets/logo.svg -resize 512x512 public/icon-512x512.png

# 生成 180x180 iOS 图标
convert src/assets/logo.svg -resize 180x180 public/apple-touch-icon.png
```

### 方法三：使用 Inkscape

如果已安装 Inkscape：

```bash
# 进入 web 目录
cd web

# 生成 192x192 图标
inkscape src/assets/logo.svg -w 192 -h 192 -o public/icon-192x192.png

# 生成 512x512 图标
inkscape src/assets/logo.svg -w 512 -h 512 -o public/icon-512x512.png

# 生成 180x180 iOS 图标
inkscape src/assets/logo.svg -w 180 -h 180 -o public/apple-touch-icon.png
```

## 验证

生成图标后，可以通过以下方式验证：

1. 启动开发服务器：`bun run dev`
2. 在浏览器中访问应用
3. 打开浏览器开发者工具 > Application > Manifest
4. 检查图标是否正确加载

## 注意事项

- 图标应使用 PNG 格式
- 建议使用透明背景或纯色背景
- 确保图标在不同尺寸下都清晰可见
- iOS 图标会自动添加圆角，无需手动处理
