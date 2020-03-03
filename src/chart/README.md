---
sidebar: auto
---

# Chart API ✍

## 简介

> DC-Chart 是 DC-SDK 与 Echart 融合的产品。主要用于在 3D 场景中添加 echart 的统计图表。将统计图表 Gis 化

## 开始

```html
<script src="***/echarts.min.js"></script>
<script src="libs/dc-sdk/dc.core.min.js"></script>
<script src="***/dc.chart.min.js"></script>
<link href="/libs/dc-sdk/dc.core.min.css" />
```

:::danger
JS 包的导入顺序不能随便， echarts/dc.core > dc.chart
:::

## DC.Chart

> 图表类

### example

```js
let chart = new DC.Chart('test')
viewer.use(chart)
```

### creation

- **_constructor([id],[option])_**

  DC.Chart 构造函数

  - 参数
    - `{String} id`：唯一标识
    - `{Object} option`：echart 配置，详情参考：[echarts](https://www.echartsjs.com/zh/option.html#title)
  - 返回值：`chart`

```json
// 配置参数，其他的参数参考 echarts
{
  "animation": false, // 必须要加
  "GLMap": {}, //地图
  "series": [
    {
      "coordinateSystem": "GLMap" // 坐标系统
    }
  ]
}
```

## 图表示例

| ![图片](https://raw.githubusercontent.com/Digital-Visual/dc-sdk-examples/master/images/datav/e_pm2.5.png) | ![图片](https://raw.githubusercontent.com/Digital-Visual/dc-sdk-examples/master/images/datav/e_pm2.5_2.png) | ![图片](https://raw.githubusercontent.com/Digital-Visual/dc-sdk-examples/master/images/datav/e_plane.gif) | ![图片](https://raw.githubusercontent.com/Digital-Visual/dc-sdk-examples/master/images/datav/e_airline.gif) |
| :-------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------: |
|  ![图片](https://raw.githubusercontent.com/Digital-Visual/dc-sdk-examples/master/images/datav/e_rk.gif)   |   ![图片](https://raw.githubusercontent.com/Digital-Visual/dc-sdk-examples/master/images/datav/e_qx.gif)    |  ![图片](https://raw.githubusercontent.com/Digital-Visual/dc-sdk-examples/master/images/datav/e_wl.gif)   |                                                                                                             |

<style>
 img{
   width:200px;
   height:200px;
 }
</style>
