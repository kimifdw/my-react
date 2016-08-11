# my-react
## component
1. create component
   > 初始化
   1. React.createElement
   ```javascript
   React.createElement(Component)
   ```
   2. React.createFactory
   ```javascript
   React.createFactory(Component)
   ```
   3. 利用React.createElement()直接创建
   ```javascript
   React.createElement("span",null,"Hello world!")
   ```
2. Properties【类似于类构造函数中的所有对外参数】
   - **this.props** is like all the arguments passed to a class constructor, 
   - **this.state** is a bag of your private properties.
   > 赋值
   1. this.props.name: 读取name属性值
    ```javascript
    var Component = React.createClass({
            render: function () {
                return React.DOM.span(null, "My name is " + this.props.name + ".I'm so custom");
            }
        });
    ```
    2. 为this.props.name: 赋值
    ```javascript
    React.createElement(Component,{name: "kimifdw"})
    ```
    > propTypes[添加多属性]
    ```javascript
    var Component = React.createClass({
            // 声明多个属性
            propTypes: {
                name: React.PropTypes.string.isRequired
            },
            render: function () {
                return React.DOM.span(null, "My name is " + this.props.name + ".I'm so custom");
            }
        });
    ```
    > Default Property Values[默认值]
    ```javascript
    getDefaultProps: function () {
        return {
            middleName: 'Bob',
            address: 'n/a'
        }
    }
    ```
3. state[为组件提供赋值,类似于类内部的私有属性]
    1. this.setState()【更新值】
    2. this.state 读取值
    3. 利用shouldComponentUpdate()来控制组件的更新
    > 初始化
    ```javascript
    getInitialState: function () {
        return {
             firstName: this.props.firstName
        }
    }
    ```
    待续。。。
    