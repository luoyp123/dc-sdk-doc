---
sidebar: auto
---

# Material API ✍

## 简介

> 在真实世界里，每个物体会对光产生不同的反应。钢看起来比陶瓷花瓶更闪闪发光，一个木头箱子不会像钢箱子一样对光产生很强的反射。每个物体对镜面高光也有不同的反应。有些物体不会散射(Scatter)很多光却会反射(Reflect)很多光，结果看起来就有一个较小的高光点(Highlight)，有些物体散射了很多，它们就会产生一个半径更大的高光。如果我们想要在 OpenGL 中模拟多种类型的物体，我们必须为每个物体分别定义材质(Material)属性。

## GS.ColorMaterialProperty

> 颜色材质

### example

```js
let material = new GS.ColorMaterialProperty(GS.Color.RED)
```

### creation

- **_constructor(color)_**

  GS.ColorMaterialProperty 构造函数

  - 参数
    - `{GS.Color} color`：颜色
  - 返回值：`material`

## GS.ImageMaterialProperty

> 图片材质

### example

```js
let material = new GS.ImageMaterialProperty({
  image: '**/**.png',
  transparent: true
})
```

### creation

- **_constructor(options)_**

  GS.ImageMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "image": "", // 图片地址
  "repeat": { "x": 1, "y": 1 }, // 图片重复
  "color": GS.Color.WHITE, // 图片颜色
  "transparent": false // 材质是否透明
}
```

### properties

- `{String} image`：图片地址
- `{Object} repeat`：图片重复
- `{GS.Color} color`：图片颜色
- `{Boolean} transparent`：材质是否透明

## GS.PolylineDashMaterialProperty

> 虚线材质

### example

```js
let material = new GS.PolylineDashMaterialProperty({
  color: GS.Color.WHITE
})
```

### creation

- **_constructor(options)_**

  GS.PolylineDashMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": GS.Color.WHITE, // 虚线颜色
  "gapColor": GS.Color.TRANSPARENT, // 间隔颜色
  "dashLength": 16.0 // 虚线片段长度
}
```

### properties

- `{GS.Color} color`：虚线颜色
- `{GS.Color} gapColor`：间隔颜色
- `{Number} dashLength`：虚线片段长度

## GS.PolylineArrowMaterialProperty

> 箭头材质

### example

```js
let material = new GS.PolylineArrowMaterialProperty(GS.Color.WHITE)
```

### creation

- **_constructor(color)_**

  GS.PolylineArrowMaterialProperty 构造函数

  - 参数
    - `{GS.Color} color`：箭头颜色
  - 返回值：`material`

### properties

- `{GS.Color} color`：箭头颜色

## GS.PolylineOutlineMaterialProperty

> 边线材质

### example

```js
let material = new GS.PolylineOutlineMaterialProperty({
  color: GS.Color.WHITE,
  outlineColor: GS.Color.BLACK
})
```

### creation

- **_constructor(options)_**

  GS.PolylineOutlineMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": GS.Color.WHITE, // 颜色
  "outlineColor": GS.Color.BLACK, // 边线颜色
  "outlineWidth": 1 // 边线宽度
}
```

### properties

- `{GS.Color} color`：颜色
- `{GS.Color} outlineColor`：边线颜色
- `{Number} outlineWidth`：边线宽度

## GS.PolylineGlowMaterialProperty

> 光晕材质

### example

```js
let material = new GS.PolylineGlowMaterialProperty({
  color: GS.Color.WHITE,
  glowPower: 0.25
})
```

### creation

- **_constructor(options)_**

  GS.PolylineGlowMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": GS.Color.WHITE, // 颜色
  "glowPower": 0.25, // 发光强度，以总线宽的百分比表示
  "taperPower": 1 // 渐缩效果的强度
}
```

### properties

- `{GS.Color} color`：颜色
- `{Number} glowPower`：发光强度
- `{Number} taperPower`：渐缩效果的强度

## GS.PolylineFlowMaterialProperty

> 流动线材质

### example

```js
let material = new GS.PolylineFlowMaterialProperty({
  color: GS.Color.WHITE,
  duration: 45
})
```

### creation

- **_constructor(options)_**

  GS.PolylineFlowMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": GS.Color.WHITE, // 颜色
  "duration": 45 // 间隔
}
```

### properties

- `{GS.Color} color`：颜色
- `{Number} duration`：间隔

## GS.PolylineTrailMaterialProperty

> 轨迹线材质

### example

```js
let material = new GS.PolylineTrailMaterialProperty({
  color: GS.Color.WHITE,
  duration: 45
})
```

### creation

- **_constructor(options)_**

  GS.PolylineTrailMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": GS.Color.WHITE, // 颜色
  "duration": 45 // 间隔
}
```

### properties

- `{GS.Color} color`：颜色
- `{Number} duration`：间隔

## GS.WaterMaterialProperty

> 流动水材质

### example

```js
let material = new GS.WaterMaterialProperty({
  baseWaterColor: GS.Color.WHITE,
  normalMap: '**/**.png'
})
```

### creation

- **_constructor(options)_**

  GS.WaterMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "baseWaterColor": GS.Color.WHITE, // 颜色
  "blendColor": GS.Color.WHITE, // 混合颜色
  "specularMap": "", // 镜面图片
  "normalMap": "", // 波纹图片
  "frequency": 10, //频率
  "animationSpeed": 0.1 // 动画速度
}
```

### properties

- `{GS.Color} baseWaterColor`：颜色
- `{GS.Color} blendColor`：混合颜色
- `{String} normalMap`：波纹图片
- `{String} specularMap`：镜面图片
