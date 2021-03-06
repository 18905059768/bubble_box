[![pub package](https://img.shields.io/badge/pub-v0.3.0-blue.svg)](https://pub.dev/packages/bubble_box)

[English](https://pub.dev/packages/bubble_box) [中文](https://github.com/18905059768/bubble_box/blob/master/README_zh.md)
# bubble_box

一个强大的气泡盒子，实现了基础的气泡、边框、虚线、渐变色、角度，自适应宽，方向、偏移等等功能

该项目是用纯flutter代码编写的，这意味着它同时支持iOS和Android。

注意：在 Flutter SDK 版本 1.24 发布之前，或者除非您位于主通道上，否则应使用版本 0.2.0

## Screenshot
<img src="https://raw.githubusercontent.com/18905059768/bubble_box/master/01.png">

# 基础的组件
```dart
BubbleBox(
    maxWidth: MediaQuery.of(context).size.width * 0.8,
    child: Text('我是一个基础的组件应用示例'),
)
```

# 自定义边框颜色、宽度，组件的背景色
```dart
BubbleBox(
    maxWidth: MediaQuery.of(context).size.width * 0.8,
    border: BubbleBoxBorder(color: Colors.blue, width: 3),
    position: BubblePosition(center: 0),
    direction: BubbleDirection.right,
    backgroundColor: Colors.green.withOpacity(0.8),
    child: Text('我可以自定义边框颜色、宽度，组件的背景色，气泡的尖角位置及尖角的偏移'),
  )
```

# 定义边框为虚线、边框颜色渐变
```dart
BubbleBox(
    maxWidth: MediaQuery.of(context).size.width * 0.8,
    gradient: LinearGradient(
      colors: [
        Colors.pink,
        Colors.orange[700],
      ],
    ),
    blendMode: BlendMode.srcATop,
    direction: BubbleDirection.left,
    border: BubbleBoxBorder(
      gradient: LinearGradient(
        colors: [
          Colors.pink,
          Colors.orange[700],
        ],
      ),
      width: 3,
      style: BubbleBoxBorderStyle.dashed,
    ),
    margin: EdgeInsets.all(4),
    position: BubblePosition(top: 9),
    elevation: 5,
    shadowColor: Colors.redAccent,
    child: Text(
        '然而我不仅仅可以自定气泡的边框和尖角。我还可以定义边框为虚线、边框颜色渐变。\n我对内容是自适应的，不需要设置宽高，当然，你可以限制组件的最大宽高。\n我的内容也可以渐变色。\n此外，你可能需要一些阴影,阴影可能也需要一些自己的颜色。'),
  )
```

#  背景色渐变
```dart
BubbleBox(
    maxWidth: MediaQuery.of(context).size.width * 0.85,
    elevation: 5,
    gradient: LinearGradient(colors: [
      Colors.red,
      Colors.orange[700],
      Colors.orange[500],
    ]),
    border: BubbleBoxBorder(
      color: Colors.blue,
      width: 3,
      style: BubbleBoxBorderStyle.dashed,
    ),
    direction: BubbleDirection.none,
    position: BubblePosition(top: 9),
    margin: EdgeInsets.all(4),
    child: Text(
      '我的背景其实也能够渐变',
    ),
  )
```

# 钝角
```dart
BubbleBox(
    maxWidth: MediaQuery.of(context).size.width * 0.85,
    direction: BubbleDirection.left,
    position: BubblePosition(top: 9),
    backgroundColor: Color(0xff98E165),
    margin: EdgeInsets.all(4),
    arrowQuadraticBezierLength: 2,
    child: Text(
      '我们添加了新的钝角，使三角形不再那么的尖锐',
    ),
  )
```

# 加强的radius
```dart
BubbleBox(
    maxWidth: MediaQuery.of(context).size.width * 0.85,
    backgroundColor: Color(0xff98E165),
    margin: EdgeInsets.all(4),
    borderRadius: BorderRadius.only(
        topRight: Radius.elliptical(30, 15),
        bottomLeft: Radius.elliptical(30, 15)),
    child: Text(
      '我们对边框radius进行了一些改造,让它更加自由',
    ),
  )
```