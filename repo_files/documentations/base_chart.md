# BaseChart



### FlBorderData
|PropName		|Description	|default value|
|:---------------|:---------------|:-------|
|show| determines to show or hide the border	|true|
|border| [Border](https://api.flutter.dev/flutter/painting/Border-class.html) details that determines which border should be drawn with which color| Border.all(color: Colors.black, width: 1.0, style: BorderStyle.solid)|



### FlTitlesData
|PropName		|Description	|default value|
|:---------------|:---------------|:-------|
|show| determines to show or hide the titles Around the chart|true|
|leftTitles| a [SideTitles](#SideTitles) that holds data to draw left titles | SideTitles(reservedSize: 40, showTitles: true)|
|topTitles| a [SideTitles](#SideTitles) that holds data to draw top titles |SideTitles(reservedSize: 6)|
|rightTitles| a [SideTitles](#SideTitles) that holds data to draw right titles |SideTitles(reservedSize: 40,)|
|bottomTitles| a [SideTitles](#SideTitles) that holds data to draw bottom titles |SideTitles(reservedSize: 22, showTitles: true)|



### SideTitles
|PropName		|Description	|default value|
|:---------------|:---------------|:-------|
|showTitles| determines whether to show or hide the titles | false|
|getTitles| a function to retrieve the title with given value on the related axis, don't touch it if you want to have a number formatter by showing indicators for large numbers.|defaultGetTitle|
|reservedSize| a reserved space to show titles|22|
|textStyle| [TextStyle](https://api.flutter.dev/flutter/painting/TextStyle-class.html) the style to use for title text |TextStyle(color: Colors.black, fontSize: 11)|
|margin| margin between each title | 6|
|interval| interval to display each title on a side, left it null to be calculate automatically | null |
|rotateAngle| the clockwise angle of rotating title in degrees   | 0.0 |
|textAlign| alignment of the text in each title   | TextAlign.center |
|checkToShowTitle| determines show or not show titles in the provided value | show all|


# AxisChart (Line and Bar Charts)


### FlGridData
|PropName|Description|default value|
|:-------|:----------|:------------|
|show|determines to show or hide the background grid data|true|
|drawHorizontalLine|determines to show or hide the horizontal grid lines|true|
|horizontalInterval|interval space of grid, left it null to be calculate automatically |null|
|getDrawingHorizontalLine|a function to get the line style of each grid line by giving the related axis value|defaultGridLine|
|checkToShowHorizontalLine|a function to check whether to show or hide the horizontal grid by giving the related axis value |showAllGrids|
|drawVerticalLine|determines to show or hide the vertical grid lines|false|
|verticalInterval|interval space of grid, left it null to be calculate automatically |null|
|getDrawingVerticalLine|a function to get the line style of each grid line by giving the related axis value|defaultGridLine|
|checkToShowVerticalLine|a function to determine whether to show or hide the vertical grid by giving the related axis value |showAllGrids|



### FlSpot
|PropName|Description|default value|
|:-------|:----------|:------------|
|x|represents x on the coordinate system (x starts from left)|null|
|y|represents y on the coordinate system (y starts from bottom)|null|



### FlLine
|propName|Description|default value|
|:-------|:----------|:------------|
|color|determines the color of line|Colors.black|
|strokeWidth|determines the stroke width of the line|2|
|dashArray|A circular array of dash offsets and lengths. For example, the array `[5, 10]` would result in dashes 5 pixels long followed by blank spaces 10 pixels long.  The array `[5, 10, 5]` would result in a 5 pixel dash, a 10 pixel gap, a 5 pixel dash, a 5 pixel gap, a 10 pixel dash, etc.|null|


### TouchedSpot
|PropName|Description|default value|
|:-------|:----------|:------------|
|spot|the touched [FlSpot](#FlSpot)|null|
|offset|[Offset](https://api.flutter.dev/flutter/dart-ui/Offset-class.html) of the touched spot|null|



### FlAxisTitleData

Can be used to display a title text for each axis. Titles for the vertical axes (left and right) will be rotated 90 degrees.

|PropName		|Description	|default value|
|:---------------|:---------------|:-------|
|show| determines to show or hide the titles for the axes|true|
|leftTitle| an [AxisTitle](#AxisTitle) that holds data to draw the title of the left axis | `AxisTitle(reservedSize: 16)`|
|topTitle| an [AxisTitle](#AxisTitle) that holds data to draw the title of the top axis | `AxisTitle(reservedSize: 16)`|
|rightTitle| an [AxisTitle](#AxisTitle) that holds data to draw the title of the right axis | `AxisTitle(reservedSize: 16)`|
|bottomTitle| an [AxisTitle](#AxisTitle) that holds data to draw the title of the bottom axis | `AxisTitle(reservedSize: 16)`|



### AxisTitle
|PropName		|Description	|default value|
|:---------------|:---------------|:-------|
|showTitle| determines to show or hide the title | `false`|
|titleText| the text to draw as a description for this axis| `''`|
|reservedSize| a reserved space for the text| `14`|
|margin| margin between the axis text and inner elements ([SideTitles](#SideTitles) or the chart) | `4`|
|textStyle| [TextStyle](https://api.flutter.dev/flutter/painting/TextStyle-class.html) to determine the style of the text | `TextStyle(color: Colors.black, fontSize: 11)`|
|textAlign| [TextAlign](https://api.flutter.dev/flutter/dart-ui/TextAlign-class.html) to determine the alignment of the text | `TextAlign.center`|


### RangeAnnotations
|PropName|Description|default value|
|:-------|:----------|:------------|
|horizontalRangeAnnotations|list of [horizontalRangeAnnotation](#HorizontalRangeAnnotation) to draw on the chart|[]|
|verticalRangeAnnotations|list of [VerticalRangeAnnotation](#VerticalRangeAnnotation) to draw on the chart|[]|


### HorizontalRangeAnnotation
|PropName|Description|default value|
|:-------|:----------|:------------|
|y1|start interval of horizontal rectangle|null|
|y2|end interval of horizontal rectangle|null|
|color|color of the rectangle|Colors.white|


### VerticalRangeAnnotation
|PropName|Description|default value|
|:-------|:----------|:------------|
|x1|start interval of vertical rectangle|null|
|x2|end interval of vertical rectangle|null|
|color|color of the rectangle|Colors.white|

### FlTouchEvent
Base class for all supported touch/pointer events.

|PropName|Description|Inspired from|
|:-------|:----------|:----------|
|FlPanDownEvent|Contains information of happened touch gesture|[GestureDragDownCallback](https://api.flutter.dev/flutter/gestures/GestureDragDownCallback.html)|
|FlPanStartEvent|When a pointer has contacted the screen and has begun to move.|[GestureDragStartCallback](https://api.flutter.dev/flutter/gestures/GestureDragStartCallback.html)|
|FlPanUpdateEvent|When a pointer that is in contact with the screen and moving has moved again.|[GestureDragUpdateCallback](https://api.flutter.dev/flutter/gestures/GestureDragUpdateCallback.html)|
|FlPanCancelEvent|When the pointer that previously triggered a `FlPanStartEvent` did not complete.|[GestureDragCancelCallback](https://api.flutter.dev/flutter/gestures/GestureDragCancelCallback.html)|
|FlPanEndEvent|When a pointer that was previously in contact with the screen and moving is no longer in contact with the screen.|[GestureDragEndCallback](https://api.flutter.dev/flutter/gestures/GestureDragEndCallback.html)|
|FlTapDownEvent|When a pointer that might cause a tap has contacted the screen.|[GestureTapDownCallback](https://api.flutter.dev/flutter/gestures/GestureTapDownCallback.html)|
|FlTapCancelEvent|When the pointer that previously triggered a `FlTapDownEvent` will not end up causing a tap.|[GestureTapCancelCallback](https://api.flutter.dev/flutter/gestures/GestureTapCancelCallback.html)|
|FlTapUpEvent|When a pointer that will trigger a tap has stopped contacting the screen.|[GestureTapUpCallback](https://api.flutter.dev/flutter/gestures/GestureTapUpCallback.html)|
|FlLongPressStart|Called When a pointer has remained in contact with the screen at the same location for a long period of time.|[GestureLongPressStartCallback](https://api.flutter.dev/flutter/gestures/GestureLongPressStartCallback.html)|
|FlLongPressMoveUpdate|When a pointer is moving after being held in contact at the same location for a long period of time. Reports the new position and its offset from the original down position.|[GestureLongPressMoveUpdateCallback](https://api.flutter.dev/flutter/gestures/GestureLongPressMoveUpdateCallback.html)|
|FlLongPressEnd|When a pointer stops contacting the screen after a long press gesture was detected. Also reports the position where the pointer stopped contacting the screen.|[GestureLongPressEndCallback](https://api.flutter.dev/flutter/gestures/GestureLongPressEndCallback.html)|
|FlPointerEnterEvent|The pointer has moved with respect to the device while the pointer is or is not in contact with the device, and it has entered our chart.|[PointerEnterEventListener](https://api.flutter.dev/flutter/services/PointerEnterEventListener.html)|
|FlPointerHoverEvent|The pointer has moved with respect to the device while the pointer is not in contact with the device.|[PointerHoverEventListener](https://api.flutter.dev/flutter/services/PointerHoverEventListener.html)|
|FlPointerExitEvent|The pointer has moved with respect to the device while the pointer is or is not in contact with the device, and exited our chart.|[PointerExitEventListener](https://api.flutter.dev/flutter/services/PointerExitEventListener.html)|
