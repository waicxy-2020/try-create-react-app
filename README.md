教程： https://zh-hans.reactjs.org/tutorial/tutorial.html

### 安装步骤
1. 全局安装 create-react-app
   > create-react-app的相关介绍 https://zh-hans.reactjs.org/docs/create-a-new-react-app.html#create-react-app
2. 新建项目
   npx create-react-app my-app
    ```
    生成的tree
    |-- README.md
    |-- node_modules
    |-- package.json
    |-- public
    |   |-- favicon.ico
    |   |-- index.html
    |   |-- logo192.png
    |   |-- logo512.png
    |   |-- manifest.json
    |   `-- robots.txt
    |-- src
    |   |-- App.css
    |   |-- App.js
    |   |-- App.test.js
    |   |-- index.css
    |   |-- index.js
    |   |-- logo.svg
    |   |-- reportWebVitals.js
    |   `-- setupTests.js
    `-- yarn.lock
    ```

### 开始应用
拷贝棋盘样式代码，布局js代码

### 知识点
1. 函数组件： 组件中只有一个`render`方法，不包含`state`，使用函数组件更简单，不用定义继承于`React.Component`的类，可以定义一个函数，该函数接收`props`作为参数，并返回需要渲染的元素
   ```javascript
   function Square(props) {
      return (
         <button className="square" onClick={props.onClick}>
           {props.value}
         </button>
      )
   }
   ```