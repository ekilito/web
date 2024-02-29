# React 概述

**React 介绍**

![React Logo](./images/react_logo.jpeg)

> react是一个用于构建用户**界面**的 JavaScript 库
>
> react官网(<https://reactjs.org/>)
>
> react中文网(https://zh-hans.reactjs.org/)

+ React 是一个用于构建用户界面（UI，对咱们前端来说，简单理解为：HTML 页面）的 JavaScript 库  
+ 如果从mvc的角度来看，React仅仅是视图层（V）的解决方案。也就是只负责视图的渲染，并非提供了完整了M和C的功能
+ react/react-dom/react-router/redux: 框架
+ React 起源于 Facebook 内部项目（News Feed，2011），后又用来架设 Instagram 的网站（2012），并于 2013 年 5 月开源[react介绍](https://baike.baidu.com/item/react/18077599?fr=aladdin)

+ React 是最流行的前端开发框架之一，其他：Vue、Angular 等等[框架对比](https://www.npmtrends.com/)

**react特点**

**声明式UI**

你只需要描述UI（HTML）看起来是什么样的，就跟写HTML一样

```js
const jsx = <div className="app">
    <h1>Hello React! 动态数据变化:{count}</h1>
</div>
```

声明式对应的是命令式，声明式关注的是what，命令式关注的是how

**组件化**

+ 组件是react中**最重要**的内容
+ 组件用于表示页面中的部分内容
+ 组合、复用多个组件，就可以实现完整的页面功能

![](images/组件-1629115179921.png)

**学习一次，随处使用**

+ 使用react/rect-dom可以开发Web应用
+ 使用react/react-native可以开发移动端原生应用（react-native）  RN   安卓 和 ios应用    flutter
+ 使用react可以开发VR（虚拟现实）应用（react360）

![](images/react-use-1629115179922.png)

**React 脚手架（CLI）**

- React 脚手架的介绍
- 使用 React 脚手架创建项目
- 项目目录结构调整

**React 脚手架的介绍**

- 脚手架：为了保证各施工过程顺利进行而搭设的工作平台
- 对于前端项目开发来说，脚手架是为了保证前端项目开发过程顺利进行而搭设的开发平台
- 脚手架的意义：
  - 现代的前端开发日趋成熟，需要依赖于各种工具，比如，webpack、babel、eslint、sass/less/postcss等
  - 工具配置繁琐、重复，各项目之间的配置大同小异
  - 开发阶段、项目发布，配置不同
    - 项目开始前，帮你搭好架子，省去繁琐的 webpack 配置
    - 项目开发时，热更新、格式化代码、git 提交时自动校验代码格式等
    - 项目发布时，一键自动打包，包括：代码压缩、优化、按需加载等

**使用 React 脚手架创建项目**

- 命令：`npx create-react-app react-basic`
  - npx create-react-app 是固定命令，`create-react-app` 是 React 脚手架的名称
  - react-basic 表示项目名称，可以修改
- 启动项目：`yarn start` or `npm start` 
- `npx` 是 npm v5.2 版本新添加的命令，用来简化 npm 中工具包的使用
  - 原始：1 全局安装`npm i -g create-react-app` 2 在通过脚手架的命令来创建 React 项目
  - 现在：npx 调用最新的 create-react-app 直接创建 React 项目

**项目目录结构说明和调整**

- 说明：
  - `src` 目录是我们写代码进行项目开发的目录
  - 查看 `package.json` 两个核心库：`react`、`react-dom`（脚手架已经帮我们安装好，我们直接用即可）
- 调整：
  1. 删除 src 目录下的所有文件
  2. 创建 index.js 文件作为项目的入口文件，在这个文件中写 React 代码即可

## React 的基本使用

![](images/jsx1.png)

# JSX

## JSX的基本使用

**JSX简介** 

`JSX`是`JavaScript XML`的简写，表示了在Javascript代码中写XML(HTML)格式的代码

优势：声明式语法更加直观，与HTML结构相同，降低学习成本，提高开发效率。

 **JSX是react的核心内容**

注意：*JSX 不是标准的 JS 语法，是 JS 的语法扩展。脚手架中内置的 [@babel/plugin-transform-react-jsx](@babel/plugin-transform-react-jsx) 包，用来解析该语法。*

![JSX 声明式vs命令式](images/JSX 声明式vs命令式-1629116328806.png)



![](images/jsx3.png)





**JSX注意点**

+ 只有在脚手架中才能使用jsx语法
  + 因为JSX需要经过babel的编译处理，才能在浏览器中使用。脚手架中已经默认有了这个配置。
+ JSX必须要有一个根节点， `<></>`  `<React.Fragment></React.Fragment>`
+ 没有子节点的元素可以使用`/>`结束

+ JSX中语法更接近与JavaScript
  + `class` =====> `className`
  + `for`========>  `htmlFor`
+ JSX可以换行，如果JSX有多行，推荐使用`()`包裹JSX，防止自动插入分号的bug

## 使用prettier插件格式化react代码

+ 安装插件

![image-20200907165515629](images/image-20200907165515629-1629115818044.png)

+ 添加prettier的配置

```js
// 保存到额时候用使用prettier进行格式化
"editor.formatOnSave": true,
// 不要有分号
"prettier.semi": false,
// 使用单引号
"prettier.singleQuote": true,
// 默认使用prittier作为格式化工具
"editor.defaultFormatter": "esbenp.prettier-vscode",
```

![](images/jsxcode.png)



## JSX中嵌入JavaScript表达式

> 在jsx中可以在`{}`来使用js表达式

+ 基本使用

```js
const name = 'zs'
const age = 18
const title = (
  <h1>
    姓名：{name}, 年龄：{age}
  </h1>
)
```

+ 可以访问对象的属性

```js
const car = {
    brand: '玛莎拉蒂'
}
const title = (
  <h1>
    汽车：{car.brand}
  </h1>
)
```

+ 可以访问数组的下标

```js
const friends = ['张三', '李四']
const title = (
  <h1>
    汽车：{friends[1]}
  </h1>
)
```

+ 可以使用三元运算符

```js
const gender = 18
const title = (
  <h1>
    性别：{gender >= 18? '是':'否'}
  </h1>
)
```

+ 可以调用方法

```js
function sayHi() {
  return '你好'
}
const title = <h1>姓名：{sayHi()}</h1>
```

+ JSX本身

```js
const span = <span>我是一个span</span>
const title = <h1>盒子{span}</h1>
```

+ JSX中的注释

```js
{/* 这是jsx中的注释 */}   推荐快键键 ctrl + /
```

+ 不要出现语句，比如`if` `for`

## 条件渲染

> 在react中，一切都是javascript，所以条件渲染完全是通过js来控制的

+ 通过判断`if/else`控制 

```js
const isLoding = false
const loadData = () => {
  if (isLoding) {
    return <div>数据加载中.....</div>
  } else {
    return <div>数据加载完成，此处显示加载后的数据</div>
  }
}

const title = <div>条件渲染：{loadData()}</div>
```

+ 通过三元运算符控制

```js
const isLoding = false
const loadData = () => {
  return isLoding ? (
    <div>数据加载中.....</div>
  ) : (
    <div>数据加载完成，此处显示加载后的数据</div>
  )
}
```

+ 逻辑运算符

```js
const isLoding = false
const loadData = () => {
  return isLoding && <div>加载中...</div>
}

const title = <div>条件渲染：{loadData()}</div>
```

## vscode配置自动补全

```jsx
// 当按tab键的时候，会自动提示
"emmet.triggerExpansionOnTab": true,
"emmet.showAbbreviationSuggestions": true,
// jsx的提示
"emmet.includeLanguages": {
  "javascript": "javascriptreact"
}
```



## 列表渲染

> 我们经常需要遍历一个数组来重复渲染一段结构
>
> 在react中，通过map方法进行列表的渲染

+ 列表的渲染 

```js
const songs = ['温柔', '倔强', '私奔到月球']

const list = songs.map(song => <li>{song}</li>)

const dv = (
  <div>
    <ul>{list}</ul>
  </div>
)
```

+ 直接在JSX中渲染

```js
const songs = ['温柔', '倔强', '私奔到月球']

const dv = (
  <div>
    <ul>{songs.map(song => <li>{song}</li>)}</ul>
  </div>
)
```

+ key属性的使用

```js
const dv = (
  <div>
    <ul>
      {songs.map(song => (
        <li key={song}>{song}</li>
      ))}
    </ul>
  </div>
)
```

**注意：列表渲染时应该给重复渲染的元素添加key属性，key属性的值要保证唯一**

**注意：key值避免使用index下标，因为下标会发生改变**

## 样式处理

### 行内样式-style

```js
const dv = (
  <div style={{ color: 'red', backgroundColor: 'pink' }}>style样式</div>
)
```

### 类名-className

```js
// 导入样式
import './base.css'

const dv = <div className="title">style样式</div>
```

base.css样式文件

```css
.title {
  text-align: center;
  color: red;
  background-color: pink;
}
```





# React 事件绑定

![](images/shijianbangding.png)

# React 组件

[React](https://beta.reactjs.org/learn/your-first-component#defining-a-component) 组件是一个 JavaScript 函数，函数中可以添加 JSX 标记

![](images/react组件.png)

# useState

![](images/usestate.png)



# 修改状态规则

![](images/xiugaizhuangtaiguiz.png)

![](images/anli.png)



# className优化类名处理

https://github.com/JedWatson/classnames

![](images/youhualei.png)





# 使用状态操作表单元素的值

![](images/shiyztcz.png)

# useRef 与 DOM 操作



![](images/dom.png)



# 组件props



![](images/props.png)



```jsx
// const Avatar = ( { imgUrl , size = 50 } ) => {   size = 50 是默认值  不传也可以

const Avatar = (props) => {     // 2.通过函数的参数接收 props 注意： props 只读的对象 不可以修改
    return (
       <img  src="{ props.imgUrl }"  alt="" width={ props.size }/>
    )
}

const App = () => {
    return(
       <div>
           // 头像组件  1.给组件传递 props
            <Avatar imgUrl="https://...jpg"  size={100}/>   // 如果是给组件传递非字符串类型的数据，需要使用 {} 来传递
        </div>
    )
}
```





# 父子组件通讯

> 一个组件需要使用另一个组件的数据。

![](images/fuzi.png)

```jsx
import './App.scss'
import className from 'classname'

// 父子组件通讯
// 1. 父传子  
// 2. 子传父
//    2.1 父组件准备修改状态的函数，并传递给子组件
//    2.2 子组件调用函数，并回传数据

// 子组件
const Todo = ({ id,text,done,onToggle }) => {            // 2. 通过结构接收父组件传的数据
    return(
        <div className = { classNames('todo', done && 'todo-done') }>
            <div onClick={()=> onToggle(id)}>{ text }</div>     // 4. 子组件调用函数，并回传数据
            <button>x</button>
        </div>
    )
}

// 任务列表数据
const defaultTodos = [
    { id:1 , text: '学习react' , done: false }
    { id:2 , text: '学习 umi' , done: true }
]

// 父组件
const App = () => {
    
    const {todos , setTodos} = useState(defaultTodos)   // 状态
    
    // 3. 父组件准备修改状态的函数，并传递给子组件
    const onToggle = id = > {
       //console.log(id)
       setTodos(
           todos.map(item => {
            if(item.id === id) {
                return {
                    ...item,
                    done:!item.done
                }
            }
            return item
        })
       )
    }
    
    return (
        <div className = "app">
           <h3>代办任务列表</h3>
            
           { todos.map(item => {
                return <Todo 
                           key={item.id} 
                           //id={item.id} 
                           //done={item.done} 
                           //text={item.text} 
                           // 优化 传递所有属性
                           {...item}
                           onToggle={onToggle}/>       // 1. 父传子
           }) }
      </div>
    )
}
```





# 非父子组件通讯

![](images/xdtx.png)



![](images/houdai.png)



# useEffect

![](images/useeffect.png)



**扩展**

![](images/useeffectkz.png)



![](images/fasong.png)





# React Hooks

![](images/hooks.png)