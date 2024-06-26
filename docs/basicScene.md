# 基础场景创建
包括场景、相机、渲染器、控制器、事件监听、资源加载器、世界场景构建器、辅助对象、辉光工具类。   
## 场景、渲染器
基础场景与渲染器的创建，采用threejs的场景与渲染器。修改threejs渲染器的源码，删除了原本的透明物体双倍渲染的代码，提高了性能
## 相机
通过扩展创建动态相机，使相机可以在巡游相机与主相机之间进行自由的切换。
## 控制器
采用threejs的轨道控制器，扩展了一个聚焦到当前物体的方法。

## 事件监听
针对场景以及小地图，分别监听了单击，双击，鼠标移动，鼠标按下，鼠标抬起，键盘按下，窗口变化以及当前窗口是否可见。   
`单击，双击`采用了300ms的时间间隔进行了区分。   
`窗口变化`用于动态适配各种分辨率。   
`当前窗口是否可见` 可以在用户切换到其他页面，以及缩小浏览器的时候，对场景不进行渲染，提高性能。
 
 ## 资源加载器
 用于加载多个GLTF模型文件，可以根据需要，进行多个模型的组装和拆分，从而更加灵活的配置当前场景。

## 世界场景构建器
将资源，动画，辅助类在此构建与合并。

## 辅助对象
用于编辑部分材质、物体与灯光的辅助对象的加载，用于配置功能的加载，辅助开发与建模。在实际生产引用中不会加载此类对象。

## 辉光工具类
通过threejs提供的后期渲染功能，对当前场景进行重新渲染，使得某些物体拥有辉光效果。   
`注：辉光会对当前场景进行5次渲染，会使得性能急剧下降。`