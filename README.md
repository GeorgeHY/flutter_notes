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
