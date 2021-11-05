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
   // 函数式写法
   function Square(props) {
      return (
         <button className="square" onClick={props.onClick}>
           {props.value}
         </button>
      )
   }
   // 等效于es6的class
   class Square extends React.Component {
      constructor(props) {
         super(props)
      }
      render() {
         return (
            <button className="square" onClick={this.props.onClick}>
               {this.props.value}
            </button>
         )
      }
   }
   ```

2. 纯函数：不改变入参的函数，且多次调用下相同的入参始终返回相同的结果

3. 构造函数是唯一可以给`this.state`赋值的地方
   ```javascript
   this.state.num = 1; // wrong
   this.setState({num: 1}) // correct
   ```

4. 向事件处理函数传递参数
   ```javascript
   <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
   <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
   ```

### 优势
1. 避免xss攻击
   * React DOM在渲染所有输入内容之前，默认会进行转义。可以确保在你的应用中，永远不会注入那些并非自己明确编写的内容。所有内容在渲染之前都被转义成字符串。
   * React渲染HTML内容和渲染DOM属性时会将`"'&<>`转义
