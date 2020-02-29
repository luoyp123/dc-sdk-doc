---
sidebar: auto
---

# Material API ✍

## 简介

> 在真实世界里，每个物体会对光产生不同的反应。钢看起来比陶瓷花瓶更闪闪发光，一个木头箱子不会像钢箱子一样对光产生很强的反射。每个物体对镜面高光也有不同的反应。有些物体不会散射(Scatter)很多光却会反射(Reflect)很多光，结果看起来就有一个较小的高光点(Highlight)，有些物体散射了很多，它们就会产生一个半径更大的高光。如果我们想要在 OpenGL 中模拟多种类型的物体，我们必须为每个物体分别定义材质(Material)属性。

## DC.ColorMaterialProperty

> 颜色材质

### example

```js
let material = new DC.ColorMaterialProperty(DC.Color.RED)
```

### creation

- **_constructor(color)_**

  DC.ColorMaterialProperty 构造函数

  - 参数
    - `{DC.Color} color`：颜色
  - 返回值：`material`

## DC.ImageMaterialProperty

> 图片材质

### example

```js
let material = new DC.ImageMaterialProperty({
  image: '**/**.png',
  transparent: true
})
```

### creation

- **_constructor(options)_**

  DC.ImageMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "image": "", // 图片地址
  "repeat": { "x": 1, "y": 1 }, // 图片重复
  "color": DC.Color.WHITE, // 图片颜色
  "transparent": false // 材质是否透明
}
```

### properties

- `{String} image`：图片地址
- `{Object} repeat`：图片重复
- `{DC.Color} color`：图片颜色
- `{Boolean} transparent`：材质是否透明

## DC.PolylineDashMaterialProperty

> 虚线材质

### example

```js
let material = new DC.PolylineDashMaterialProperty({
  color: DC.Color.WHITE
})
```

### creation

- **_constructor(options)_**

  DC.PolylineDashMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": DC.Color.WHITE, // 虚线颜色
  "gapColor": DC.Color.TRANSPARENT, // 间隔颜色
  "dashLength": 16.0 // 虚线片段长度
}
```

### properties

- `{DC.Color} color`：虚线颜色
- `{DC.Color} gapColor`：间隔颜色
- `{Number} dashLength`：虚线片段长度

## DC.PolylineArrowMaterialProperty

> 箭头材质

### example

```js
let material = new DC.PolylineArrowMaterialProperty(DC.Color.WHITE)
```

### creation

- **_constructor(color)_**

  DC.PolylineArrowMaterialProperty 构造函数

  - 参数
    - `{DC.Color} color`：箭头颜色
  - 返回值：`material`

### properties

- `{DC.Color} color`：箭头颜色

## DC.PolylineOutlineMaterialProperty

> 边线材质

### example

```js
let material = new DC.PolylineOutlineMaterialProperty({
  color: DC.Color.WHITE,
  outlineColor: DC.Color.BLACK
})
```

### creation

- **_constructor(options)_**

  DC.PolylineOutlineMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": DC.Color.WHITE, // 颜色
  "outlineColor": DC.Color.BLACK, // 边线颜色
  "outlineWidth": 1 // 边线宽度
}
```

### properties

- `{DC.Color} color`：颜色
- `{DC.Color} outlineColor`：边线颜色
- `{Number} outlineWidth`：边线宽度

## DC.PolylineGlowMaterialProperty

> 光晕材质

### example

```js
let material = new DC.PolylineGlowMaterialProperty({
  color: DC.Color.WHITE,
  glowPower: 0.25
})
```

### creation

- **_constructor(options)_**

  DC.PolylineGlowMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": DC.Color.WHITE, // 颜色
  "glowPower": 0.25, // 发光强度，以总线宽的百分比表示
  "taperPower": 1 // 渐缩效果的强度
}
```

### properties

- `{DC.Color} color`：颜色
- `{Number} glowPower`：发光强度
- `{Number} taperPower`：渐缩效果的强度

## DC.PolylineFlowMaterialProperty

> 流动线材质

### example

```js
let material = new DC.PolylineFlowMaterialProperty({
  color: DC.Color.WHITE,
  duration: 45
})
```

### creation

- **_constructor(options)_**

  DC.PolylineFlowMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": DC.Color.WHITE, // 颜色
  "duration": 45 // 间隔
}
```

### properties

- `{DC.Color} color`：颜色
- `{Number} duration`：间隔

## DC.PolylineTrailMaterialProperty

> 轨迹线材质

### example

```js
let material = new DC.PolylineTrailMaterialProperty({
  color: DC.Color.WHITE,
  duration: 45
})
```

### creation

- **_constructor(options)_**

  DC.PolylineTrailMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "color": DC.Color.WHITE, // 颜色
  "duration": 45 // 间隔
}
```

### properties

- `{DC.Color} color`：颜色
- `{Number} duration`：间隔

## DC.WaterMaterialProperty

> 流动水材质

### example

```js
let material = new DC.WaterMaterialProperty({
  baseWaterColor: DC.Color.WHITE,
  normalMap: '**/**.png'
})
```

### creation

- **_constructor(options)_**

  DC.WaterMaterialProperty 构造函数

  - 参数
    - `{Object} options`：属性
  - 返回值：`material`

```json
// 属性参数（可选）
{
  "baseWaterColor": DC.Color.WHITE, // 颜色
  "blendColor": DC.Color.WHITE, // 混合颜色
  "specularMap": "", // 镜面图片
  "normalMap": "", // 波纹图片
  "frequency": 10, //频率
  "animationSpeed": 0.1 // 动画速度
}
```

### properties

- `{DC.Color} baseWaterColor`：颜色
- `{DC.Color} blendColor`：混合颜色
- `{String} normalMap`：波纹图片
- `{String} specularMap`：镜面图片
