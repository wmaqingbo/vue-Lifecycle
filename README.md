## vue-Lifecycle

vue 生命周期探究

### 生命周期各阶段都做了什么

-   beforeCreate : 实例创建前：这个阶段实例的data、methods是读不到的
-   created : 实例创建后：这个阶段已经完成了数据观测(data observer)，属性和方法的运算， watch/event 事件回调。mount挂载阶段还没开始，$el 属性目前不可见，数据并没有在DOM元素上进行渲染
-   beforeMount : 在挂载开始之前被调用：相关的 render 函数首次被调用。
-   mounted : el选项的DOM节点 被新创建的 vm.$el 替换，并挂载到实例上去之后调用此生命周期函数。此时实例的数据在DOM节点上进行渲染
-   beforeUpdate : 数据更新时调用，但不进行DOM重新渲染，在数据更新时DOM没渲染前可以在这个生命函数里进行状态处理
-   updated : 这个状态下数据更新并且DOM重新渲染，当这个生命周期函数被调用时，组件 DOM 已经更新，所以你现在可以执行依赖于 DOM 的操作。当实例每次进行数据更新时updated都会执行
-   beforeDestory : 实例销毁之前调用。
-   destroyed : Vue 实例销毁后调用。调用后，Vue 实例指示的所有东西都会解绑定，所有的事件监听器会被移除，所有的子实例也会被销毁。

### 生命周期在真实场景下的业务应用

-   created：进行ajax请求异步数据的获取、初始化数据
-   mounted：挂载元素内dom节点的获取
-   nextTick：针对单一事件更新数据后立即操作dom
-   updated：任何数据的更新，如果要做统一的业务逻辑处理
-   watch：监听具体数据变化，并做相应的处理
