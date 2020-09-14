# flutter_notes

1. 可以通过onGenerateRoute做一些全局的路由跳转前置处理逻辑(使用命名路由方式)
2. 路由使用命名路由方式
3. pubspec.yaml 管理依赖库
4. initState:当Widget第一次插入到Widget树时会被调用，对于每一个State对象，Flutter framework只会调用一次该回调，所以，通常在该回调中做一些一次性的操作，如状态初始化、订阅子树的事件通知等。
   在build（）方法或didChangeDependencies()中调用BuildContext.dependOnInheritedWidgetOfExactType
5. 当系统语言Locale或应用主题改变时，Flutter framework会通知widget调用didChangeDependencies()
6. 在继承StatefulWidget重写其方法时，对于包含@mustCallSuper标注的父类方法，都要在子类方法中先调用父类方法。
7. 直接通过of静态方法来获取ScaffoldState
8. 使用GlobalKey开销较大，如果有其他可选方案，应尽量避免使用它。另外同一个GlobalKey在整个widget树中必须是唯一的，不能重复。
9. 如果状态是用户数据，如复选框的选中状态、滑块的位置，则该状态最好由父Widget管理。如果状态是有关界面外观效果的，例如颜色、动画，那么状态最好由Widget本身来管理。如果某一个状态是不同Widget共享的则最好由它们共同的父Widget管理。
10.实现一个全局的事件总线，将语言状态改变对应为一个事件，然后在APP中依赖应用语言的组件的initState 方法中订阅语言改变的事件。当用户在设置页切换语言后，我们发布语言改变事件，而订阅了此事件的组件就会收到通知，收到通知后调用setState(...)方法重新build一下自身即可。或者第三方库
