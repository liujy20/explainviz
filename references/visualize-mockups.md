# 界面原型与设计变体

这是对话中的可操作界面预览，不是项目代码修改。利用已有产品与平台上下文；缺失时合理推断，不为了一个原型扫描整个项目。

- 产品内部使用根节点作用域的产品颜色、字体与布局，不用 .card/.btn 等可视化组件类，也不用 --card/--font-size-base 等宿主 token。
- 产品窗口、弹窗和菜单要有不透明背景；只让外围会话背景透明。未指定主题时用产品自己的 light-dark 配色随宿主切换。
- 桌面完整应用使用 wide；组件、对话框和手机预览用正常宽度。全局导航放应用框架，局部控制放组件，展示真实状态而非填充仪表盘。
- 原型操作本地响应。设计替代方案确有帮助时，使用宿主 Tweak；不要另画一套重复控制面板，也不自动打开批注。

## Tweak 绑定

先渲染初始状态，再判断 `globalThis.Tweak` 是否存在：

```js
const state = { radius: 12, accent: '#4f46e5', dense: false, layout: 'list' };
const root = document.getElementById('product-preview');
function render() {
  root.style.borderRadius = `${state.radius}px`;
  root.style.setProperty('--product-accent', state.accent);
  root.dataset.layout = state.layout;
  root.dataset.dense = String(state.dense);
}
render();
if (globalThis.Tweak) {
  const tweak = new Tweak({ container: root, onChange: render });
  tweak.addSlider(state, 'radius', { label: '圆角', min: 0, max: 32, unit: 'px' });
  tweak.addColorPicker(state, 'accent', { label: '强调色', reference: '--product-accent' });
  tweak.addToggle(state, 'dense', { label: '紧凑模式' });
  tweak.addSelect(state, 'layout', { label: '布局', options: ['list', 'grid'] });
}
```

渲染函数需真正应用所有状态；这里的 dataset 要由产品 CSS 或渲染逻辑消费。每个独立组件一个 Tweak 实例，给组件 aria-label；最多 12 个控制，每个 select 最多 12 项。宿主拥有打开、关闭、重置和提交；onChange 只本地渲染，不发网络写操作。不重建被注册的根元素；组件移除时才 dispose。

导出时 Tweak 可不存在，必须仍显示有效初态和普通产品交互。若用户要求把设计调节功能也导出，按相同 state/render 构造原生输入控件，而非让导出的 Tweak 按钮失效。
