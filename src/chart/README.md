---
sidebar: auto
---

# Chart API ✍

## 简介

> DC-Chart 是 DC-SDK 与 Echart 融合的产品。主要用于在 3D 场景中添加 echart 的统计图表。将统计图表 Gis 化

## 开始

```html
<script src="**/libs/dc-sdk/dc.core.min.js"></script>
<script src="**/libs/echart/echart.min.js"></script>
<script src="**/libs/dc-chart/dc.chart.min.js"></script>
<link href="**/libs/dc-sdk/dc.core.min.css" />
```

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
  "GLMap": {}, //地图
  "series": [
    {
      "coordinateSystem": "GLMap" // 坐标系统
    }
  ]
}
```

## 图表示例
