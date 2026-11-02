# FigmaEX 擎天柱皮肤 · v1.4.2

红蓝装甲、青色流光和擎天柱眼睛状态反馈。此仓库只提供当前版本；自动外壳高度尚未完成。

## 下载与使用

- [下载 v1.4.2 压缩包](https://github.com/Torin12323/figmaex-optimus/raw/refs/heads/main/figmaex-optimus-v1.4.2.zip)
- [开发与验收规范](FIGMAEX-SKIN-STANDARD.md)
- [本次修复说明](docs/v1.4.2-native-layout.md)

1. 下载并解压，使用记事本打开 **optimus.css**。
2. 全选复制，进入 FigmaEX 设置 → 皮肤 → 自定义 CSS 皮肤。
3. 备份旧 CSS 后，**全选替换**并保存，不要追加到旧代码后。
4. 静态版改用 optimus-static.css，二选一。

角色图片和装甲素材均内嵌在 CSS 中，无需另行上传。
恢复默认：取消勾选“启用皮肤”，或清空自定义 CSS 后保存。

## 文件区别

| 文件 | 行为 |
| --- | --- |
| optimus.css | 动态版：流光周期 1.6 秒、选中延伸、卡片反馈、眼睛状态 |
| optimus-static.css | 静态版：关闭持续动画、过渡和缩放，保留选中颜色与宽度状态 |
| preview.html | 离线交互示意；布局与事件为模拟，不能代替实际安装验收 |
| FIGMAEX-SKIN-STANDARD.md | 本次错误复盘、开发规范、验收与交付清单 |

## 当前修复

- 撤回强制 Grid 分栏与区域定位覆盖。
- 撤回列表 height:auto!important，恢复原生高度计算。
- 底部拖动条恢复绝对定位。
- 修复同一元素同时带有 area-groups 与 GroupPad 类时目录底色被透明规则覆盖的问题。
- 保留 4px 光轨、2px 主要描边、目录选中延伸和眼睛反馈。

54px 是 FigmaEX 原生收起宽度。关闭设置后，将鼠标移到顶部头像区域检查展开；开启闲时最小化时可能存在约 400ms 延迟。单张收起截图不能证明展开失败。

## 验证与限制

本地 Chromium 已使用官方 Chrome 发布包 v1.5.101 中读取的 CSS 和 DOM 结构，检查 54px 收起、400px 展开、列表滚动、拖动条位置和动画保护。用户截图为 v1.5.100，仍需在实际安装中确认。发布包仅用于读取，未安装或执行其 JavaScript；本地事件由测试脚本模拟。

[验证说明](docs/README-QA.md) · [布局测量](docs/native-layout-check-v1.4.2.json) · [静态检查](docs/qa-results.json)

**外壳随目录／插件数量自动增长的需求暂缓，尚未完成。** 当前优先恢复原生布局；本地测试不能保证所有宿主版本兼容。

右侧持续选中依赖宿主提供 active、selected 或 aria-selected 状态，纯 CSS 不能保存最后点击的插件。系统“减少动态效果”优先关闭持续动画与缩放。

## 素材与参考

用户指定原图保留原始字节和署名，眼睛使用独立透明覆盖层。非官方角色主题，角色及原插画权益归相应权利人；本仓库不对第三方素材授予额外许可。

参考：[Moonvy/Figma-CSS-Skins](https://github.com/Moonvy/Figma-CSS-Skins)、[liteyais/FigmaEX-CSS-Skin](https://github.com/liteyais/FigmaEX-CSS-Skin)。
