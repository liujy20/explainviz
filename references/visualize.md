# 结构、数据与交互可视化

## HTML + Mermaid 节点

静态结构需要可检查的 HTML 预览时，使用 `../assets/examples/router-node.html`。
它保留 Mermaid 源码，并由固定版本的 Mermaid npm 包负责浏览器渲染；需要截图时用浏览器截图能力。

只在图示能帮助用户观察、理解或探索时使用。普通表格直接 Markdown；创建新网站或项目组件回到项目工作流；科学出版图使用标准绘图工具。预览界面、解释产品交互属于此分支。

## 选择表现方式

- 静态节点与边已足够：返回 Mermaid 代码块，不生成 HTML。用户需要在浏览器中预览或截图时，使用 `router-node.html` 的 Mermaid npm 模板。复杂 Mermaid 语法、源码分析或文件操作转 [设计文档分支](design-doc-mermaid.md)。
- 动态过程、参数变化或空间运动：一个主视图配必要控制，采用 [交互示例](../assets/examples/interactive-fragment.html) 的根节点隔离与更新方式。
- 数据图、地图、时间线、分配图或分类网格：读取 [数据图与地图](visualize-data.md)。
- 产品界面预览与设计变体：读取 [界面原型](visualize-mockups.md)。
- 需要状态保存或复杂交互：读取 [宿主交互](visualize-interaction.md)。
- 控件、主题和布局遵循本文件末尾的视觉样式与可访问性规范；不逐次发明外壳。

## HTML 与交付

1. 会话内输出写 UTF-8 HTML fragment，不含 doctype/html/head/body。写真实换行和引号，根节点用唯一 ID；选择器限制在根下，不使用 document.currentScript 推断根节点。文件小于 1 MB，数据多时先聚合。
2. 数据放入 fragment；不使用 fetch、XHR、WebSocket。npm 库通过宿主允许的 CDN 导入：cdnjs.cloudflare.com、esm.sh、cdn.jsdelivr.net、unpkg.com、fonts.googleapis.com、fonts.gstatic.com、fonts.bunny.net；必须固定版本。使用 D3 绘制图表、地图和几何图，使用 Mermaid 渲染结构图。避免用手写 DOM/SVG 实现本已有成熟 npm 包的布局、比例尺或图算法。
3. 选择持久任务目录保存小写连字符命名的 HTML，不写系统临时目录、Library 或 skill 安装目录。会话给出可视化目录时优先使用。
4. 只在宿主明确支持时，在最终回复单独一行显示 `visualize{"path":"<绝对路径>/explainer.html"}`。每次新建或更新都显示；不要用普通下载链接替代。桌面完整应用原型使用 `"mode":"wide"`；其他内容仅在多个并列面板确有需要时用宽模式，单张密集图不自动加宽。
5. 图内部只放图形、必要标签、图例与可访问性描述。说明、结论和边界放在图外，避免复述数据或介绍实现细节。
6. 无宿主展示协议或用户要导出时，保存完整 HTML 并直接在浏览器打开；交互和图表由 npm 包实现，不需要 Python 包装器或构建步骤。保留原 HTML 作为编辑源。
7. 用浏览器检查主交互、320px 窄屏、亮暗主题和控制台错误；通过浏览器截图工具显示渲染结果。无法检查的项目要说明，不能声称已通过。
8. 导出 HTML 时移除宿主专用 API，将宿主动作替换为有意义的本地操作。需要状态持久化时可选用浏览器 localStorage，且明确其限制。交付可在本地浏览器打开的 HTML 文件。

## 视觉样式与可访问性

- 顶层透明、无外框；图、地图和表格不套卡片。只有必要的数值摘要或选中项可用 `.card`，不嵌套卡片。
- 宿主片段使用主题变量；独立 HTML 明确提供等价 CSS 自定义属性：`--background`、`--foreground`、`--card`、`--card-foreground`、`--muted`、`--muted-foreground`、`--primary`、`--primary-foreground`、`--border`。底色与文字成对使用；SVG 可用 `currentColor`。
- 字体正文默认 14px，次要信息 12px，不能小于 11px；触控目标约 44px，输入文字至少 16px。至少支持 320px 宽度。
- 使用原生 button/input/select/textarea，提供标签、键盘焦点和 `aria-live`/`role=alert`；颜色同时配合文字、形状或线型。尊重 `prefers-reduced-motion`。
- 通常按 736px、宽模式按 1024px 设计；响应式 SVG 预留轴和图例空间，删次要标签优于挤压或横向溢出。
- 产品界面预览使用自己的作用域样式和不透明窗口背景；交互原型的 Tweak 规则见 [界面原型](visualize-mockups.md)。
