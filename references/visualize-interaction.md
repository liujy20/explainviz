# 交互状态保存

## 状态契约

读取 `window.openai?.widgetState`，缺失或版本不兼容时回到默认。监听 `openai:set_globals`，读取 `event.detail.globals.widgetState` 并更新画面，不能在加载或接收事件时再次保存。

用户完成有意义的操作后调用：

```js
window.openai?.setWidgetState?.({
  modelContent: { selected: selectedId },
  privateContent: { expanded: expandedId }
})?.catch(() => {});
```

每次替换完整快照，控制在 16 KiB 内，字段为可序列化 JSON 或 null。modelContent 放有助于后续问题的选择，privateContent 放展示细节；不要存图像、秘密或可重新计算的大数据。保存状态不代表开始新对话，模型接收是尽力而为。

[交互示例](../assets/examples/interactive-fragment.html) 展示宿主状态 API。导出为独立 HTML 时，应移除宿主专用 API，改用浏览器原生交互；只有确实需要跨刷新保存时才使用 localStorage，并在存储被禁用时保留页内交互且不声称状态已持久化。

## 界面参数调节

Tweak 仅适用于界面原型，具体绑定和导出行为见 [原型规范](visualize-mockups.md)。
