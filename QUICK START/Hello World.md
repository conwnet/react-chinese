# Hello World
开始 React 最简单的方法就是[使用 CodePen 上这个 Hello World 的例子](http://codepen.io/gaearon/pen/ZpvBNJ?editors=0010)。你什么都不需要安装，你只需要在浏览器上再打开一个标签页，然后修改里面的代码完成我们的例子。如果你更倾向于使用本地开发环境，请阅读 [Installation](https://github.com/conwnet/react-chinese/blob/master/QUICK%20START/Installation.md)。

最小的 React 例子是这样的：

~~~
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
~~~

它在页面上渲染了一个标题，显示 Hello World。

接下来的几部分将逐步引导你使用 React。我们将研究 React 应用的构建模块：元素和组件。当你学会了这些，你将可以使用很多小的可复用的片段来构建复杂的应用。

## 一个 JavaScript 笔记
React 是一个 JavaScript 库，它假设你对 JavaScript 语言有一个基本的了解。如果你不是很有信心的话，我们推荐你[刷新你的 JavaScript 知识](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)，这样你学起来会更轻松。

我们也会在例子中使用一些 ES6 语法。我们会尽量把握好尺度因为它确实还算有些超前，但是我们鼓励你应该熟悉一下[箭头函数](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)，[类](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)，[模版字符串](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Template_literals)，[`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) 和 [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) 语句，你可以使用 [Babel REPL](http://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact&experimental=false&loose=false&spec=false&code=const%20element%20%3D%20%3Ch1%3EHello%2C%20world!%3C%2Fh1%3E%3B%0Aconst%20container%20%3D%20document.getElementById('root')%3B%0AReactDOM.render(element%2C%20container)%3B%0A) 来检查你的 ES6 代码被编译成什么了。
