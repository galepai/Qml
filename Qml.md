## 1.

QML的：（属性绑定）与JavaScript的=（赋值）是不同的。绑定是一个协议，并且存在于整个生命周期。然而JavaScript赋值（=）只会产一次效果。**当一个新的绑定生效或者使用JavaScript赋值给属性时，原绑定的生命周期就会结束。**

## 2.

QML的alias（别名）的功能，它可以将内部嵌套的QML元素的属性导出到外面使用。**只有根级对象的属性才能够被其它文件的组件访问。**

## 3.

一个动画定义了一个属性的在⼀段时间内的变化过程。为了实现这个效果， 我们使用一个动画类型叫做属性行为。这个行为指定了一个动画来定义属性的每一次改变并赋值给属性。**每次属性改变，动画都会运行。**这是QML中声明动画的几种方式中的一种方式。

```
    Image {

        id: root

        Image {

            id: wheel

            Behavior on rotation {

                NumberAnimation {

                    duration: 250
                }

			}

		}

	}
```

现在每当旋转角度发生改变时都会使用NumberAnimation来实现250毫秒的旋转动画效果。每一次90度的转变都需要花费250ms。

## 4.

方法1：（绝对路径）

   

```
 Image{

    source:“file:///C:/images/backa.png”

    anchors.fill: parent

  }
```

方法2：（相对路径）

   

```
 Image{

    source: "file:images/backa.png"

    anchors.fill: parent

  }
```



## 5.

QML的扩展插件(QtQuick 2 QML Extension Plugin)向导，生成的库文件(dll,so)和对应的qmldir文件。 文件要放在QtCreate能识别的路径下。可以放在Qt安装对应版本的qml文件下。