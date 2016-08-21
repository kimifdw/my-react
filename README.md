# my-react
React:UP & RUNNING 笔记
## component
1. create component
   > 初始化
   1. React.createElement
   ```react
   React.createElement(Component)
   ```
   2. React.createFactory
   ```react
   React.createFactory(Component)
   ```
   3. 利用React.createElement()直接创建
   ```react
   React.createElement("span",null,"Hello world!")
   ```
2. Properties【类似于类构造函数中的所有对外参数】
   - **this.props** is like all the arguments passed to a class constructor, 
   - **this.state** is a bag of your private properties.
   > 赋值
   1. this.props.name: 读取name属性值
    ```react
    var Component = React.createClass({
            render: function () {
                return React.DOM.span(null, "My name is " + this.props.name + ".I'm so custom");
            }
        });
    ```
    2. 为this.props.name: 赋值
    ```react
    React.createElement(Component,{name: "kimifdw"})
    ```
    > propTypes[添加多属性]
    
    ```react
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
    
    ```react
    getDefaultProps: function() {
        return {
            middleName: 'Bob',
            address: 'n/a'
        }
    }
    ```
    3. 修改组件的值
        - 修改方法
        ```react
        // 修改组件属性
                componentWillReceiveProps: function (newProps) {
                    this.setState({
                        text: newProps.defaultValue
                    })
                }
        ```
        - 设置方法
        ```react
        myTextAreaCounter.componentWillReceiveProps({defaultValue: "hello james"});
        ```
    4. Lifecycle方法
        1. componentWillUpdate()
        - 在render()方法前执行***修改属性或state***
        2. componentDidUpdate()
        - 在render()方法后执行
        3. componentWillMount()
        - 在结点插入DOM前执行
        4. componentWillUnmount()
        - 在组件被移除DOM前执行
        5. shouldComponentUpdate(newProps,newState)
        - 在componentWillUpdate()前调用,可以允许取消更新
        6. 执行顺序
            1. componentWillMount
            2. componentDidMount
            3. componentWillUpdate
            4. componentDidUpdate
        
3. state[为组件提供赋值,类似于类内部的私有属性]
    1. this.setState()【更新值】
    2. this.state 读取值
    3. 利用shouldComponentUpdate()来控制组件的更新
    > 初始化
    
    ```react
    getInitialState: function () {
        return {
             firstName: this.props.firstName
        }
    }
    ```
    > 设置值
    ```react
    this.setState({
         data: this._preSearchData,
         search: false
    });
    ```
4. ReactDom.findDOMNode()
   - 获取组件DOM结点
    