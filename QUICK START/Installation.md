[**返回目录**](https://github.com/conwnet/react-chinese/blob/master/README.md)

# 安装
React 很灵活，他可以用于多种项目中。你可以直接创建一个 React 的应用，也可以在一个已经存在的项目中逐渐引入它，而不需要重写代码。

## 尝试React
如果你只是想随便玩儿一下 React，你可以使用 CodePen。在线体验 [Hello World 的示例代码](http://codepen.io/gaearon/pen/rrpgNB?editors=0010)。你什么都不需要安装，也可以实时修改代码并看到效果。

如果你更喜欢使用自己的编辑器，你也可以[下载这个 HTML 文件](https://facebook.github.io/react/downloads/single-file-example.html)，你可以编辑它，然后用浏览器从本地文件中打开它。这个例子会消耗一个很慢的转换代码时间，所以我们在生产环境中不这样做。

## 创建一个单页应用
[Create React App](http://github.com/facebookincubator/create-react-app) 是创建一个 React 单页应用最好的方式。它会创建一个开发环境，这样你可以使用最新的 JavaScript 特性，来保证更好的开发体验，并且也会优化你的应用。

~~~
npm install -g create-react-app
create-react-app hello-world
cd hello-world
npm start
~~~

Create React App 不处理后端逻辑和数据库，它只是创建一个前端的编译管线(build pipeline)，所以你可以在任何后端环境中使用它。它其实是使用了已经自动配置好了的 [webpack](https://webpack.js.org/)，[Babel](http://babeljs.io/) 和 [ESLint](http://eslint.org/)。

## 在已有应用中添加 React
想要使用 React，你不需要重写你的应用。

我们建议把 React 添加到你应用的一小部分中，比如一个单独的部件，这样如果它工作正常的话你可以很方便的看到它的效果。

当 [React 工作在没有编译管线的环境](https://facebook.github.io/react/docs/react-without-es6.html)中，我们推荐先建立好它以保证更高效。现在的编译管线通常包括：
一个包管理器：比如 [Yarn](https://yarnpkg.com/) 或者 [npm](https://www.npmjs.com/)。它的优点就是它有一个巨大的第三方包库，你可以很方便的安装或者更新它们。
一个打包工具：比如 [webpack](https://webpack.js.org/) 或者 [Browserify](http://browserify.org/)。它可以让你多个模块化的代码打包到一个很小的文件中来优化载入时间。
一个编译器：比如 [Babel](http://babeljs.io/)。它可以让你写新特性的 JavaScript 并且保证它们运行在老版本的浏览器中。

### 安装 React

我们推荐使用 [Yarn](https://yarnpkg.com/) 或者 [npm](https://www.npmjs.com/) 来管理前端依赖。如果你没使用过包管理器，你可以先阅读一下 [Yarn 的文档](https://yarnpkg.com/en/docs/getting-started)。

使用 Yarn 安装 React：
~~~
yarn init
yarn add react react-dom
~~~

使用 npm 安装 React：
~~~
npm init
npm install --save react react-dom
~~~

Yarn 和 npm 都是从 [npm 注册表](http://npmjs.com/) 中下载应用。

### 使用 ES6 和 JSX
我们推荐使用 [Bebel](http://babeljs.io/) 来让你的代码支持 ES6 和 JSX。ES6 包含一些新的 JavaScript 特性，可以让你开发过程更轻松，JSX 是 JavaScript 语言的一个扩展，可以很好的工作在 React 中。

[Babel 安装指南](https://babeljs.io/docs/setup/)介绍了怎么在不同的环境中配置 Babel，确保你已经安装了 [`babel-preset-react`](http://babeljs.io/docs/plugins/preset-react/#basic-setup-with-the-cli-) 和 [`babel-preset-es2015`](http://babeljs.io/docs/plugins/preset-react/#basic-setup-with-the-cli-) 毕竟已经在 `.babelrc` 配置文件中启用了它们，然后就没问题了。

### 使用 ES6 和 JSX 的 Hello World
我们推荐使用一个打包工具比如 [webpack](https://webpack.js.org/) 或者 [Browserify](http://browserify.org/)，这样我们就可以写现代化的代码然后把它们打包成一个小的文件来优化载入时间。

一个最小的 React 例子是这样的：

~~~
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);

~~~

这个代码渲染了一个 id 是 `root` 的 DOM 节点，所以你的 HTML 文件中要有这样一行：`<div id="root"></div>`。

类似的，你可以使用任何其他 JavaScript UI 库在你已经完成的 App 中的任何地方的 DOM 节点渲染一个 React 组件。

### 开发和发行版本
默认地，React 包含很多有用的警告。这些警告在开发中是很有用的，但是他们会让 React 体积更庞大并且运行更慢，所以你应该在部署应用的时候使用发行版本。

#### Brunch
想要使用 Brunch 创建一个优化的发行版，只需要在编译命令中添加 `-p` 参数，查看 [Brunch 文档](http://brunch.io/docs/commands)以了解更多细节。

#### Browserify
运行 Browserify 需要 `NODE_ENV` 这个环境变量来创建发行版并且最后在编译最后一步使用 UglifyJS 来剥离只用作开发版的代码。

#### 创建 React App
如果你使用 [Create React App](https://github.com/facebookincubator/create-react-app)，`npm run build` 命令会在 `build` 目录中编译出一个优化好的的文件。


#### Rollup
使用 [rollup-plugin-replace](https://github.com/rollup/rollup-plugin-replace) 插件和 [rollup-plugin-commonjs](https://github.com/rollup/rollup-plugin-commonjs) (保持这个顺序) 来删除只用作开发版的代码，[查看完整的安装简介](https://gist.github.com/Rich-Harris/cb14f4bc0670c47d00d191565be36bf0)以了解更多。

#### Webpack

使你的发行版本中包括 DefinePlugin 和 UglifyJsPlugin。查看[这个指南](https://webpack.js.org/guides/production-build/)以了解 webpack 的配置。

### 使用 CDN
如果你不想使用 npm 来管理你的本地包，react 和 react-dom npm 包中也提供了单文件的版本，在 dist 目录中，你也可以使用一个 CDN 引用它们。

~~~
<script src="https://unpkg.com/react@15/dist/react.js"></script>
<script src="https://unpkg.com/react-dom@15/dist/react-dom.js"></script>
~~~

这个版本只适用于开发版本，不适用于发行版本。压缩优化发行版本的 React 应使用这个 CDN。
~~~
<script src="https://unpkg.com/react@15/dist/react.min.js"></script>
<script src="https://unpkg.com/react-dom@15/dist/react-dom.min.js"></script>
~~~

要载入一个特定版本的 react 和 react-dom 文件，把 15 替换为相应的版本号即可。

如果你使用 Bower，这个 react 包也是可用的。
