**组件的声明周期分为三个状态：**

- Mounting：已插入真实DOM
- Updating: 正在被重新渲染
- Unmounting：已移出真实DOM

 **React 为每个状态都提供了两种处理函数，will 函数在进入状态之前调用，did 函数在进入状态之后调用，三种状态共计五种处理函数。**

- componentWillMount()
  - 组件初始化时只调用，以后组件更新不调用，整个生命周期只调用一次，此时可以修改state。
- componentDidMount()
  - 组件渲染之后调用，只调用一次。
- componentWillUpdate(nextProps, nextState)
  - 组件初始化时不调用，只有在组件将要更新时才调用
- componentDidUpdate(nextProps, nextState)
  - 组件初始化时不调用，组件更新完成后调用，此时可以获取dom节点。
- componentWillUnmount()
  -  组件将要卸载时调用，一些事件监听和定时器需要在此时清除。

**此外React还提供两种特殊状态的处理函数**

-  componentWillReceiveProps()
  - 已加载组件收到新的参数(props)时调用
- shouldComponentUpdate(nextProps, nextState) 
  - 组件判断是否重新渲染时调用(接受新的state或者props时调用)