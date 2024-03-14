# MVC模式

1. ## 简介

- MVC模式代表Model——View——Controller（模型——视图——控制器）模式。这种模式用于应用程序的分层开发。
  - Model（模型）-模型代表一个存取数据的对象或JAVA POJO。它也可以带有逻辑，在数据变化时更新控制器。
  - View（视图）-视图代表模型包含的数据的可视化。
  - Controller（控制器）-控制器作用月模型和视图上。它控制数据流向模型对象，并在数据变化时更新视图。它使视图与模型分离开。

<img src="D:\Study\Self\Typora\images\ModelViewController.png" style="zoom:25%;" />

