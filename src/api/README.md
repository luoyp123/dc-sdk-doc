---
sidebar: auto
---

# API ✍

## 基础

### Coordinates System

**`世界坐标`**

笛卡尔坐标，以椭球中心为原点的空间直角坐标系中的一个点的坐标。

**`地理坐标`**

地理坐标系，坐标原点在椭球的质心。

经度：参考椭球面上某点的大地子午面与本初子午面间的两面角。东正西负。

纬度 ：参考椭球面上某点的法线与赤道平面的夹角。北正南负。

**`屏幕坐标`**

浏览器窗口坐标

### Webgl

WebGL 是一种 JavaScript API，用于在不使用插件的情况下在任何兼容的网页浏览器中呈现交互式 2D 和 3D 图形。WebGL 完全集成到浏览器的所有网页标准中，可将影像处理和效果的 GPU 加速使用方式当做网页 Canvas 的一部分。WebGL 元素可以加入其他 HTML 元素之中并与网页或网页背景的其他部分混合。WebGL 程序由 JavaScript 编写的句柄和 OpenGL Shading Language（ **`GLSL`** ）编写的着色器代码组成。

### 3D 数据

**`glb/gltf`**

GLTF 代表 Graphics Language Transmission Format（图形语言传输格式）。这种跨平台格式已成为 Web 上的 3D 对象标准。它由 OpenGL 和 Vulkan 背后的 3D 图形标准组织 Khronos 所定义，这使得 GLTF 基本上成为 3D 模型的 JPG 格式：Web 导出的通用标准。

**`3dtiles`**

3D Tiles 是用于流式传输大规模异构 3D 地理空间数据集的开放规范。3D Tiles 数据可以通过 shp、osgb(倾斜摄影)、3dmax 等数据生成。

**`geojson`**

GeoJSON 是一种对各种地理数据结构进行编码的格式，基于 Javascript 对象表示法的地理空间信息数据交换格式。GeoJSON 对象可以表示几何、特征或者特征集合。GeoJSON 支持下面几何类型：点、线、面、多点、多线、多面和几何集合。GeoJSON 里的特征包含一个几何对象和其他属性，特征集合表示一系列特征。

**`kml/czml`**

KML/CZML 是一个 JSON 格式的数据,描述 time-dynamic（时间、动态）图形场景,它描述了线、点、广告牌(标记)、模型、和其他图形原语,并指定他们如何随时间变化。

<img src="https://raw.githubusercontent.com/Digital-Visual/dc-sdk/master/data_transform.png" style="width:100%;height:400px">

### Namespace

**`DC`**

框架使用 DC 为命名空间，开发时尽量不要使用 GS 为变量名或者命名空间，避免框架无法正常使用。

**`Cesium`**

[Cesium](https://cesium.com/cesiumjs/) 是一款面向三维 GIS 的世界级的 ES6 的开源产品。该产品方便个人或者团队快速搭建一款无插件的三维 GIS 的 Web 应用， 在性能、精度、渲染质量、跨平台上都有很好的保证。开发时如果需要 Cesium 的内部接口可以通过 DC.getNamesapce().Cesium 获取 Cesium 命名空间。

[Cesium Api](https://cesium.com/docs/cesiumjs-ref-doc/)

## 类图

> SDK 中类，使用时需要添加命名空间

<img src="https://raw.githubusercontent.com/Digital-Visual/dc-sdk/master/SDK.png" style="width:100%;height:800px">
## 开始

```html
<script src="libs/dc-sdk/dc.core.min.js"></script>
<script src="libs/dc-sdk/plugins/dc.plugins.min.js"></script>
<link href="libs/dc-sdk/dc.core.min.css" />
```

```js
DC.ready(() => {
  let viewer = new DC.Viewer(divId)
})
```

:::danger
请将 JS 包放置项目根目录的 libs 下，如果放置到其他文件夹下，框架将无法正常运行
:::

## 常量

> 框架内部默认常量

::: danger
开发时请使用默认常量进行开发，使用其他可能无法正常运行。
:::

### MouseEventType

**_`DC.MouseEventType.CLICK`_**: 鼠标点击事件

**_`DC.MouseEventType.RIGHT_CLICK`_**: 鼠标右击事件

**_`DC.MouseEventType.DB_CLICK`_**: 鼠标双击事件

**_`DC.MouseEventType.MOUSE_MOVE`_**: 鼠标移动事件

**_`DC.MouseEventType.WHEEL`_**: 鼠标滚轮事件

**_`DC.MouseEventType.MOUSE_OVER`_**: 鼠标移入事件

**_`DC.MouseEventType.MOUSE_OUT`_**: 鼠标移出事件

### SceneEventType

**_`DC.SceneEventType.CAMERA_MOVE_END`_**: 相机移动完成

**_`DC.SceneEventType.CAMERA_CHANGED`_**: 相机位置完成

**_`DC.SceneEventType.PRE_RENDER`_**: 场景渲染前

**_`DC.SceneEventType.POST_RENDER`_**: 场景渲染后

**_`DC.SceneEventType.MORPH_COMPLETE`_**: 场景模式变换完成

**_`DC.SceneEventType.CLOCK_TICK`_**: 时钟跳动

### LayerType

**_`DC.LayerType.VECTOR`_**: 矢量图层

**_`DC.LayerType.TILESET`_**: 3dtiles 图层

**_`DC.LayerType.CLUSTER`_**: 聚合图层

**_`DC.LayerType.GEOJSON`_**: GeoJson 图层

**_`DC.LayerType.KML`_**: kml 图层

**_`DC.LayerType.CZML`_**: czml 图层

**_`DC.LayerType.HTML`_**: html 图层

**_`DC.LayerType.HEAT`_**: 热区图层

**_`DC.LayerType.MAPV`_**: Mapv 图层

### OverlayType

**_`DC.OverlayType.POINT`_**: 点

**_`DC.OverlayType.POLYLINE`_**: 线

**_`DC.OverlayType.POLYGON`_**: 面

**_`DC.OverlayType.MODEL`_**: 模型

**_`DC.OverlayType.BILLBOARD`_**: 图标点

**_`DC.OverlayType.CIRCLE`_**: 圆

**_`DC.OverlayType.RECT`_**: 矩形

**_`DC.OverlayType.LABEL`_**: 标签

**_`DC.OverlayType.PLANE`_**: 面板

**_`DC.OverlayType.WALL`_**: 墙体

### EffectType

**_`DC.EffectType.RAIN`_**: 雨

**_`DC.EffectType.SNOW`_**: 雪

**_`DC.EffectType.FOG`_**: 雾

**_`DC.EffectType.BLOOM`_**: 泛光

**_`DC.EffectType.CIRCLE_SCAN`_**: 扫描圈

**_`DC.EffectType.RADAR_SCAN`_**: 雷达扫描

## DC.World

> 等同 DC.Viewer，后期不要用，会舍弃

## DC.Viewer

> 3D 场景

### example

```html
<div id="map-contaienr"></div>
```

```js
let viewer = DC.Viewer('map-contaienr')
global.viewer = viewer // 添加到全局变量
```

:::warning
如果开发使用的是 Vue 这样的 MVVM 框架，不要将 viewer、layer、overlay 添加到数据模型中。由于 3D 场景中会不停的刷新每一帧，如果将数据添加到数据模型中，长时间的话会导致浏览器的压力增大而奔溃。
:::

### creation

- **_constructor(id,options)_**

  DC.Viewer 构造函数

  - 参数
    - `{Stiring} id`：容器 ID
    - `{Object} options`：属性
  - 返回值：`viewer`

  ```json
  //属性参数（可选）
  {
    "contextOptions": {
      "webgl": {
        "alpha": false, //背景
        "depth": true,
        "stencil": false,
        "antialias": true,
        "powerPreference": "high-performance",
        "premultipliedAlpha": true,
        "preserveDrawingBuffer": false,
        "failIfMajorPerformanceCaveat": false
      },
      "allowTextureFilterAnisotropic": true
    },
    "sceneMode": 3 //1: 2.5D，2: 2D，3: 3D
  }
  ```

### properties

- `{Element} dcContainer`：框架自定义容器 **_`readonly`_**
- `{Object} scene`：场景 **_`readonly`_**，详情参考：[Scene](https://cesium.com/docs/cesiumjs-ref-doc/Scene.html)
- `{Object} camera`：相机 **_`readonly`_**，详情参考：[Camera](https://cesium.com/docs/cesiumjs-ref-doc/Scene.html)
- `{Element} canvas`：canvas 节点 **_`readonly`_**
- `{Object} clock`：时钟，详情参考：[Clock](https://cesium.com/docs/cesiumjs-ref-doc/Clock.html)
- [`{Popup} popup`](#popup)：气泡窗口 **_`readonly`_**
- [`{ContextMenu} contextMenu`](#contextmenu)：右击弹框 **_`readonly`_**
- [`{Tooltip} tooltip`](#tooltip)：提示框 **_`readonly`_**
- [`{MapSplit} mapSplit`](#mapsplit)：地图分割 **_`readonly`_**
- `{DC.Position} cameraPosition`：相机位置 **_`readonly`_**

### methods

- **_setOptions(options)_**

  设置属性

  - 参数
    - `{Object} options`：属性对象
  - 返回值：`this`

  ```json
  // 属性参数(可选)
  {
    "showGlobe": true, //是否显示地球
    "enableLighting": true, //是否开启灯光，开启后地球会根据当前时间启用灯光
    "showAtmosphere": true, //是否显示大气层
    "showSun": true, //是否显示太阳
    "showMoon": true, //是否显示月亮
    "showSkyBox": true, //是否显示天空盒
    "enableFxaa": true, //是否开启抗锯齿
    "underground": true, //是否开启地下模式
    "shouldAnimate": true //是否允许动画
  }
  ```

- **_setPitchRange(min,max)_**

  设置翻转角度

  - 参数
    - `{Number} min`：最小角度
    - `{Number} max`：最大角度
  - 返回值：`this`

- **_limitCameraToGround()_**

  设置限制相机到地下

  - 返回值：`this`

- **_changeMode(sceneMode, duration)_**

  改变场景模式

  - 参数
    - `{Number} sceneMode`：场景模式 ，2：2D，3：3D
    - `{Number} duration`：间隔时间
  - 返回值：`this`

- **_addBaseLayer(baseLayers,options)_**

  添加地图图层

  - 参数
    - `{baselayer|Array<baselayer>} baseLayers`：地图图层
    - `{Object} options`：属性
  - 返回值：`this`

  ```json
  //属性参数
  {
    "name": "电子地图", //名称
    "iconUrl": "../preview.png" //缩略图
  }
  ```

- **_changeBaseLayer(index)_**

  更改地图

  - 参数
    - `{Number} index`：地图索引
  - 返回值：`this`

- **_addTerrain(terrain)_**

  添加地形

  - 参数
    - `{Terrain} terrain`：地形
  - 返回值：`this`

- **_changeTerrain(index)_**

  变换地形

  - 参数
    - `{Number} index`：地形索引
  - 返回值：`this`

- **_addLayer(layer)_**

  添加图层

  - 参数
    - `{Layer} layer`：图层
  - 返回值：`this`

- **_removeLayer(layer)_**

  删除图层

  - 参数
    - `{Layer} layer`：图层
  - 返回值：`this`

- **_getLayer(id)_**

  获取图层

  - 参数
    - `{String} id`：图层 ID
  - 返回值：`layer`

- **_getLayers()_**

  获取所有图层，不包括地图

  - 返回值：`layer`

- **_eachLayer(method, context)_**

  遍历所有图层

  - 参数
    - `{Function} method`：回调函数
    - `{Object} context`：上下文，默认为 this
  - 返回值：`this`

  ```js
  viewer.eachLayer(layer => {})
  ```

- **_addEffect(effect)_**

  添加效果

  - 参数
    - [`{Effect} effect`](#effect)：效果
  - 返回值：`this`

- **_removeEffect(effect)_**

  删除效果

  - 参数
    - `{Effect} effect`：效果
  - 返回值：`this`

- **_flyTo(target)_**

  飞向目标

  - 参数
    - `{DC.Vectolayer|Overlay} target` ：目标
  - 返回值：`this`

- **_zoomTo(target)_**

  缩放到目标

  - 参数
    - `{DC.Vectolayer|Overlay} target` ：目标
  - 返回值：`this`

- **_flyToPosition(position, completeCallback, duration)_**

  飞到具体位置

  - 参数
    - `{DC.Position} position`：位置
    - `{Function} completeCallback`：飞完之后触发的回调
    - `{Number} duration`：飞到位置时间，单位：秒
  - 返回值：`this`

- **_on(type, callback, context)_**

  事件订阅

  - 参数
    - `{Object} type` ：订阅类型
    - `{Function} callback` ：订阅回调
    - `{Object} context` ：上下文
  - 返回值：`this`

- **_off(type, callback, context)_**

  取消事件订阅

  - 参数
    - `{Object} type` ：订阅类型
    - `{Function} callback` ：订阅回调
    - `{Object} context` ：上下文
  - 返回值：`this`

- **_use(plugin)_**

  使用插件(慎用)

  - 参数
    - `{Object} plugin` ：插件
  - 返回值：`this`

  ```js
  let pulgin = {
    install: viewer => {}
  }
  viewer.use(pulgin)
  ```

## Popup

> 气泡窗口

### example

```js
let popup = viewer.popup
popup.setContent('<div></div>')
```

### properties

- `{Boolean} enable`：是否启用
- `{String} state`：状态 **_`readonly`_**
- `{Object} config`：配置 **_`writeonly`_**

```json
// 配置参数（可选）
// 配置后会影响全局的popup的显示样式，请慎重。
{
  "position": "center", // popup的位于鼠标的点击位置的方向,有：center，left ，right
  "customClass": "custom" // 添加自定义的Css 类名到popup中，多个用空格隔开
}
```

### methods

- **_setPosition(position)_**

  设置位置

  - 参数
    - `{Cartesian3} position`：世界坐标
  - 返回值：`this`

- **_setContent(content)_**

  设置位置

  - 参数
    - `{String|Element} content`：内容
  - 返回值：`this`

## ContextMenu

> 右击菜单

### example

```js
let contextMenu = viewer.contextMenu
contextMenu.enable = true
tooltip.addMenuItem('测试', () => {}, this)
```

### properties

- `{Boolean} enable`：是否启用
- `{String} state`：状态 **_`readonly`_**

### methods

- **_addMenuItem(label, callback, context)_**

  设置位置

  - 参数
    - `{String} label`：文本
    - `{Function} callback`：回调函数
    - `{Object} context`：回调上下文
  - 返回值：`this`

## Tooltip

> 提示框

### example

```js
let tooltip = viewer.tooltip
tooltip.enable = true
tooltip.setContent('测试')
```

### properties

- `{Boolean} enable`：是否启用
- `{String} state`：状态 **_`readonly`_**

### methods

- **_setPosition(position)_**

  设置位置

  - 参数
    - `{Cartesian3} position`：世界坐标
  - 返回值：`this`

- **_setContent(content)_**

  设置位置

  - 参数
    - `{String|Element} content`：内容
  - 返回值：`this`

## MapSplit

> 地图分割

### examples

```js
let baselayer_elc = DC.ImageryLayerFactorycreateGoogleImageryLayer()
viewer._mapSplit.enable = true
viewer._mapSplit.addBaseLayer(baselayer_elc, -1)
```

## DC.ImageryLayerFactory

> 地图工厂

### example

```js
let baseLayer = DC.ImageryLayerFactory.createAmapImageryLayer({
  style: 'img'
})
viewer.addBaseLayer(baseLayer, {
  name: '地图',
  iconUrl: '../preview.png'
})
```

### static methods

- **_createAmapImageryLayer(options)_**

  创建高德地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createBaiduImageryLayer(options)_**

  创建百度地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createGoogleImageryLayer(options)_**

  创建谷歌地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createTdtImageryLayer(options)_**

  创建天地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createTencentImageryLayer(options)_**

  创建腾讯地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createArcGisImageryLayer(options)_**

  创建 Arcgis 地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createSingleTileImageryLayer(options)_**

  创建单图片地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createWMTSImageryLayer(options)_**

  创建 WMTS 地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createXYZImageryLayer(options)_**

  创建 X/Y/Z 地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createCoordImageryLayer(options)_**

  创建坐标系地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

- **_createCaeaImageryLayer(options)_**

  创建数图地图

  - 参数
    - `{Object} options`：属性
  - 返回值：`baseLayer`

  ```json
  //属性参数(可选)
  {
    "url": "", //地址：arcgis/wmts/xyx/single 有效
    "style": "img", //样式：img、elec、ter。百度：normal、middelnight
    "key": "", //天地图有效
    "subdomains": []
  }
  ```

## DC.TerrainFactory

> 地形工厂

### example

```js
let terrain = DC.ImageryLayerFactory.createUrlTerrain({
  url: '****/***'
})
viewer.addTerrain(terrain)
```

### static methods

- **_createEllipsoidTerrain()_**

  创建默认地形

  - 返回值：`terrain`

- **_createUrlTerrain(options)_**

  根据 url 创建地形

  - 参数
    - `{Object} options`：属性
  - 返回值：`terrain`

- **_createGoogleTerrain(options)_**

  创建谷歌地形

  - 参数
    - `{Object} options`：属性
  - 返回值：`terrain`

- **_createArcgisTerrain(options)_**

  创建 Arcgis 地形

  - 参数
    - `{Object} options`：属性
  - 返回值：`terrain`

- **_createVRTerrain(options)_**

  创建 VR 地形

  - 参数
    - `{Object} options`：属性
  - 返回值：`terrain`

```json
//属性参数（可选）
{
  "url": "" // 服务地址
}
```

## Layer

> 图层的基类

:::warning
该基本类无法实例化
:::

### properties

- `{Sting} id`：唯一标识 **_`readonly`_**
- `{Boolean} show`：是否显示
- `{Object} attr`：业务属性
- `{Sting} state`：图层状态 **_`readonly`_**
- `{Sting} type`：图层类型 **_`readonly`_**

### methods

- **_addOverlay(overlay)_**

  添加覆盖物

  - 参数
    - `{Overlay} overlay`：覆盖物
  - 返回值：`this`

- **_removeOverlay(overlay)_**

  删除覆盖物

  - 参数
    - `{Overlay} overlay`：覆盖物
  - 返回值：`this`

- **_getOverlay(id)_**

  根据 Id 获取覆盖物(不推荐用)

  - 参数
    - `{String} id`：覆盖物唯一标识
  - 返回值：`overlay`

- **_getOverlayByAttr(atrrName, attrVal)_**

  根据覆盖物属性获取覆盖物

  - 参数
    - `{String} atrrName`：属性名称
    - `{Object} attrVal`：属性值
  - 返回值：`overlay`

  ```js
  overlay.attr.name = 'test' //设置覆盖物的属性
  layer.getOverlayByAttr('name', 'test') //根据属性获取覆盖物
  ```

- **_clear()_**

  清空图层

  - 返回值：`this`

- **_remove()_**

  删除图层

  - 返回值：`this`

- **_addToViewer(viewer)_**

  添加图层到场景

  - 参数
    - `{DC.Viewer} viewer`：场景
  - 返回值：`this`

## DC.VectorLayer

> 矢量图层，继承于[Layer](#layer)

### example

```js
let layer = new DC.VectorLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  DC.VectorLayer 构造函数

  - 参数
    - `{Stiring} id`：图层唯一标识
  - 返回值：`vectorLayer`

## DC.TilesetLayer

> 3dTiles 图层，继承于[Layer](#layer)

### example

```js
let layer = new DC.TilesetLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  DC.TilesetLayer 构造函数

  - 参数
    - `{Stiring} id`：图层唯一标识
  - 返回值：`tilesetLayer`

## DC.ClusterLayer

> 聚合图层，继承于[Layer](#layer)

### example

```js
let layer = new DC.ClusterLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id,[options])_**

  DC.ClusterLayer 构造函数

  - 参数
    - `{Stiring} id`：图层唯一标识
    - `{Object} options`：属性配置
  - 返回值：`clusterLayer`

```json
// 属性参数(可选)
{
  "size": 48, //聚合的尺寸
  "pixelRange": 40, //像素范围
  "gradient": {
    0.0001: Cesium.Color.BLUE,
    0.001: Cesium.Color.GREEN,
    0.01: Cesium.Color.ORANGE,
    0.1: Cesium.Color.RED
  }, // 幅度颜色设置
  "fontSize": 14, // 字体大小
  "fontColor": Cesium.Color.BLACK // 字体颜色
}
```

### methods

- **_addOverlays(overlays)_**

  添加覆盖物数组

  - 参数
    - `{Array<Overlay>} overlays`：覆盖物数组
  - 返回值：`this`

## DC.HeatmapLayer

> 热区图层，继承于[Layer](#layer)

### example

```js
let bounds = [new DC.Position(100, 20), new DC.Position(150, 26)]
let layer = new DC.HeatmapLayer('id', bound)
viewer.addLayer(layer)
```

### creation

- **_constructor(id,bounds,[options])_**

  DC.HeatmapLayer 构造函数

  - 参数
    - `{Stiring} id`：图层唯一标识
    - `{Array<DC.Position>} bounds`：热区范围，有长度为 2 的数组组成，第一个为西南坐标，第二个为东北坐标
    - `{Object} options`：属性配置
  - 返回值：`heatmapLayer`

```json
//属性参数(可选)
{
  "maxOpacity": 0.8, // 最大透明度
  "minOpacity": 0.1, // 最小透明度
  "blur": 0.85, // 模糊度
  "gradient": {
    "0.5": "blue",
    "0.8": "red",
    "0.95": "white",
    "0.6": "yellow",
    "0.5": "green"
  }, //颜色设置
  "distanceDisplayCondition": {
    "near": 0, //最近距离
    "far": Number.MAX_VALUE //最远距离
  } //根据距离设置可见
}
```

### methods

- **_setPositions(positions)_**

  设置点位

  - 参数
    - `{Array<Object>} positions`：点位信息
  - 返回值：`heatmapLayer`

  ```json
  //点位信息参数
  {
    "lng": "", //经度
    "lat": "", //纬度
    "value": "" //值
  }
  ```

  ·

## DC.GeoJsonLayer

> GeoJson 图层，继承于[Layer](#layer)，主要要来加载 Geojson 数据

### example

```js
let layer = new DC.GeoJsonLayer('id', '**/**.geojson')
layer.eachOverlay(item => {
  if (item.polygline) {
    //todo
  }
  if (item.polygon) {
    //todo
  }
  if (item.billboard) {
    //todo
  }
})
```

### creation

- **_constructor(id,url,[options])_**

  DC.GeoJsonLayer 构造函数

  - 参数
    - `{Stiring} id`：图层唯一标识
    - `{Stiring} url`：数据地址
    - `{Object} options`：属性配置，详情参考：[GeoJsonDataSource](https://cesium.com/docs/cesiumjs-ref-doc/GeoJsonDataSource.html)
  - 返回值：`geoJsonLayer`

### methods

- **_toVectorLayer()_**

  转换为矢量图层

  - 返回值：`vectorLayer`

## DC.CzmlLayer

> Czml 图层，继承于[Layer](#layer)，主要要来加载 Czml 数据

### example

```js
let layer = new DC.CzmlLayer('id', '**/**.czml')
layer.eachOverlay(item => {
  if (item.polygline) {
    //todo
  }
  if (item.polygon) {
    //todo
  }
  if (item.billboard) {
    //todo
  }
})
```

### creation

- **_constructor(id,url,[options])_**

  DC.CzmlLayer 构造函数

  - 参数
    - `{Stiring} id`：图层唯一标识
    - `{Stiring} url`：数据地址
    - `{Object} options`：属性配置，详情参考：[CzmlDataSource](https://cesium.com/docs/cesiumjs-ref-doc/CzmlDataSource.html)
  - 返回值：`czmlLayer`

## DC.KmlLayer

> Kml 图层，继承于[Layer](#layer)，主要要来加载 Kml 数据

### example

```js
let layer = new DC.KmlLayer('id', '**/**.kml')
layer.eachOverlay(item => {
  if (item.polygline) {
    //todo
  }
  if (item.polygon) {
    //todo
  }
  if (item.billboard) {
    //todo
  }
})
```

### creation

- **_constructor(id,url,[options])_**

  DC.KmlLayer 构造函数

  - 参数
    - `{Stiring} id`：图层唯一标识
    - `{Stiring} url`：数据地址
    - `{Object} options`：属性配置，详情参考：[KmlDataSource](https://cesium.com/docs/cesiumjs-ref-doc/KmlDataSource.html)
  - 返回值：`kmlLayer`

## DC.HtmlLayer

> Html 图层，继承于[Layer](#layer)，主要要来加载 DivIcon 节点

### example

```js
let layer = new DC.HtmlLayer('dom')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  DC.HtmlLayer 构造函数

  - 参数
    - `{Stiring} id`：图层唯一标识
  - 返回值：`htmlLayer`

## DC.Position

> 坐标类，在 3D 中坐标采用右手标准

### example

```js
let position = new DC.Potision(120, 22, 102)

let position1 = DC.Potision.fromCoordString('120,22,102')

let position2 = DC.Potision.fromCoordArray([120, 22, 102])
```

### creation

- **_constructor(lng,lat,alt,heaing,pitch,roll)_**

  DC.Position 构造函数

  - 参数
    - `{Number} lng`：经度
    - `{Number} lat`：纬度
    - `{Number} alt`：高度，单位：米，默认：0
    - `{Number} heaing`：偏航角度，可能其他框架作 yaw，表示绕 Z 轴旋转。默认：0
    - `{Number} pitch`：俯仰角度，表示绕 Y 轴旋转。默认：0
    - `{Number} roll`：翻转角度，表示绕 Z 轴旋转。默认：0
  - 返回值：`position`

### porperties

- `{Number} lng`：经度
- `{Number} lat`：纬度
- `{Number} alt`：高度，单位：米，默认：0
- `{Number} heaing`：偏航角度，可能其他框架作 yaw，表示绕 Z 轴旋转。默认：0
- `{Number} pitch`：俯仰角度，表示绕 Y 轴旋转。默认：0
- `{Number} roll`：翻转角度，表示绕 Z 轴旋转。默认：0

### methods

- **_serialize()_**

  序列化

  - 返回值：`string`

### static methods

- **_fromCoordString(str)_**

  字符坐标串转换为坐标对象

  - 参数
    - `{String} str`：字符坐标串
  - 返回值：`position`

- **_fromCoordArray(array)_**

  坐标数组转换为坐标对象

  - 参数
    - `{Array<Sting|Number>} array`：坐标数组
  - 返回值：`position`

## DC.Color

> 颜色类

### example

```js
let red = DC.Color.RED
```

### properties

- `{Color} RED`：红色
- `{Color} YELLOW`：黄色
- `{Color} WHITE`：白色
- `{Color} GREEN`：绿色

  [其他颜色](https://cesium.com/docs/cesiumjs-ref-doc/Color.html)

### static methods

- **_fromBytes(red, green, blue, alpha)_**

  通过字节获取颜色

  - 参数
    - `{Number} red`：红色值，0~255
    - `{Number} green`：绿色值，0~255
    - `{Number} blue`：蓝色值，0~255
    - `{Number} alpha`：透明值，0~255
  - 返回值：`color`

- **_fromCssColorString(color)_**

  通过 Css 获取颜色

  - 参数
    - `{String} color`：Css 颜色值，如：#rgb, #rrggbb, rgb(), rgba(), hsl(), or hsla()
  - 返回值：`color`

## DC.JulianDate

> 朱莉安日历

```js
let date = DC.JulianDate.now()
```

### static methods

- **_now()_**

  当前朱莉安时间

  - 返回值：`date`

- **_fromDate(date)_**

  通过 Js 时间创建朱莉安时间

  - 参数
    - `{Date} date`：Js 时间
  - 返回值 `date`

## DC.CallbackProperty

> 回调属性，用户通过自定义，回调函数，来返回需要的值。回调函数中，用户可以使用 time 来给定 value，也可以以自己的方式给给定。

```js
let position = new DC.Position(120, 20)
let point = new DC.Point(position)
let size = 0
point.setStyle({
  pixelSize: new DC.CallbackProperty(time => {
    size += 1
    if (size == 10) {
      size = 0
    }
    return size
  })
})
```

## Overlay

> 覆盖物基类

:::warning
该类无法实例化
:::

### properties

- `{Sting} id`：唯一标识 **_`readonly`_**
- `{Boolean} show`：是否显示
- `{Object} attr`：业务属性
- `{Sting} state`：覆盖物状态 **_`readonly`_**
- `{Sting} type`：覆盖物类型 **_`readonly`_**

### methods

- **_addToLayer(layer)_**

  添加到图层

  - 参数
    - `{Layer} layer` ：图层
  - 返回值：`this`

- **_remove()_**

  删除

  - 返回值：`this`

- **_on(type, callback, context)_**

  事件订阅

  - 参数
    - `{Object} type` ：订阅类型
    - `{Function} callback` ：订阅回调
    - `{Object} context` ：上下文
  - 返回值：`this`

- **_off(type, callback, context)_**

  取消事件订阅

  - 参数
    - `{Object} type` ：订阅类型
    - `{Function} callback` ：订阅回调
    - `{Object} context` ：上下文
  - 返回值：`this`

- **_fire(type,params)_**

  触发事件

  - 参数
    - `{Object} type` ：订阅类型
    - `{Object} params` ：参数
  - 返回值：`this`

## DC.Point

> 点位要素，继承于[Overlay](#overlay)

### exmaple

```js
let position = new DC.Position(120, 20)
let point = new DC.Point(position)
point.setStyle({
  pixelSize: 10
})
```

### creation

- **_constructor(position)_**

  DC.Point 构造函数

  - 参数
    - [`{DC.Position} position`](#dc-position)：坐标
  - 返回值：`point`

### properties

- [`{DC.Position} position`](#dc-position)：坐标

### methods

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式，详情参考：[PointGraphics](https://cesium.com/docs/cesiumjs-ref-doc/PointGraphics.html)
  - 返回值：`this`

  ```json
  // 样式参数(可选)
  {
    "pixelSize": "1", //像素大小
    "color": DC.Color.WHITE, //颜色
    "outlineColor": DC.Color.WHITE, //边框颜色
    "outlineWidth": 0, //边框大小，
    "scaleByDistance": {
      "near": 0, //最近距离
      "nearValue": 0, //最近距离值
      "far": 1, //最远距离值
      "farValue": 0 //最远距离值
    }, //根据距离设置比例
    "translucencyByDistance": {
      "near": 0, //最近距离
      "nearValue": 0, //最近距离值
      "far": 1, //最远距离值
      "farValue": 0 //最远距离值
    }, //根据距离设置透明度
    "distanceDisplayCondition": {
      "near": 0, //最近距离
      "far": Number.MAX_VALUE //最远距离
    }, //根据距离设置可见
    "disableDepthTestDistance": 0 // 深度检测距离，用于防止剪切地形，设置为零时，将始终应用深度测试。设置为Number.POSITIVE_INFINITY时，永远不会应用深度测试。
  }
  ```

## DC.Polyline

> 线要素，继承于[Overlay](#overlay)

### exmaple

```js
let polyline = new DC.Polyline('120,20;120,30')
polyline.setStyle({
  width: 10
})
```

### creation

- **_constructor(positions)_**

  DC.Polyline 构造函数

  - 参数
    - `{String|Array<DC.Position|Number|String>} positions`：坐标串
  - 返回值：`polyline`

### properties

- `{String|Array<DC.Position|Number|String>} positions`：坐标串
- `{DC.Position} center`：中心点 **_`readonly`_**
- `{Number} distance`：距离,单位：米 **_`readonly`_**

### methods

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式，详情参考：[PolylineGraphics](https://cesium.com/docs/cesiumjs-ref-doc/PolylineGraphics.html)
  - 返回值：`this`

  ```json
  // 样式参数(可选)
  {
    "width": 1, //线宽
    "material": DC.Color.WHITE, //材质
    "clampToGround": false, //是否贴地
    "shadows": 0, //阴影类型，0：禁用、1：启用 、2：投射、3：接受
    "distanceDisplayCondition": {
      "near": 0, //最近距离
      "far": Number.MAX_VALUE //最远距离
    }, //根据距离设置可见
    "classificationType": 2, //分类 是否影响地形，3D切片或同时影响这两者。0:地形、1:3D切片、2：两者
    "zIndex": 0 //层级
  }
  ```

## DC.Polygon

> 面要素，继承于[Overlay](#overlay)

### exmaple

```js
let polygon = new DC.Polygon('120,20;120,30;122,30')
polygon.setStyle({
  height: 10
})
```

### creation

- **_constructor(positions)_**

  DC.Polygon 构造函数

  - 参数
    - `{String|Array<DC.Position|Number|String>} positions`：坐标串
  - 返回值：`polygon`

### properties

- `{String|Array<DC.Position|Number|String>} positions`：坐标串
- `{String|Array<DC.Position|Number|String>} holes`：洞坐标串
- `{DC.Position} center`：中心点 **_`readonly`_**
- `{Number} area`：距离，单位：平方米 **_`readonly`_**

### methods

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式，详情参考：[PolygonGraphics](https://cesium.com/docs/cesiumjs-ref-doc/PolygonGraphics.html)
  - 返回值：`this`

  ```json
  // 样式参数(可选)
  {
    "height": 1, //高度
    "extrudedHeight": 0, //拉升高度
    "stRotation": 0, //旋转角度
    "material": DC.Color.WHITE, //材质
    "outline": false, //是否显示边框
    "outlineColor": DC.Color.BLACK, //边框颜色
    "outlineWidth": 0, //边框宽度
    "closeTop": true, //顶面是否闭合
    "closeBottom": true, //底面是否闭合
    "shadows": 0, //阴影类型，0：禁用、1：启用 、2：投射、3：接受
    "distanceDisplayCondition": {
      "near": 0, //最近距离
      "far": Number.MAX_VALUE //最远距离
    }, //根据距离设置可见
    "classificationType": 2, //分类 是否影响地形，3D切片或同时影响这两者。0:地形、1:3D切片、2：两者
    "zIndex": 0 //层级
  }
  ```

## DC.Billboard

> 图标要素，继承于[Overlay](#overlay)

### exmaple

```js
let position = new DC.Position(120, 20)
let billboard = new DC.Billboard(position, '***/**.png')
billboard.size = [20, 20]
```

### creation

- **_constructor(position,icon)_**

  DC.Billboard 构造函数

  - 参数
    - `{DC.Position} position`：坐标
    - `{String} icon`：图标地址
  - 返回值：`billboard`

### properties

- `{DC.Position} position`：坐标
- `{String} icon`：图标地址
- `{Arrray<Number>} size`：图标大小

### methods

- **_setLabel(text, textStyle)_**

  设置标签

  - 参数
    - `{String} text`：文本
    - `{String} textStyle`：文本样式，详情参考：[DC.Label](#dc-label)
  - 返回值：`this`

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式，详情参考：[BillboardGraphics](https://cesium.com/docs/cesiumjs-ref-doc/BillboardGraphics.html)
  - 返回值：`this`

  ```json
  // 样式参数(可选)
  {
    "scale": 1, //比例
    "pixelOffset": { "x": 0, "y": 0 }, //偏移像素
    "stRotation": 0, //旋转角度
    "translucencyByDistance": {
      "near": 0, //最近距离
      "nearValue": 0, //最近距离值
      "far": 1, //最远距离值
      "farValue": 0 //最远距离值
    }, //根据距离设置透明度
    "distanceDisplayCondition": {
      "near": 0, //最近距离
      "far": Number.MAX_VALUE //最远距离
    }, //根据距离设置可见
    "disableDepthTestDistance": 0 // 深度检测距离，用于防止剪切地形，设置为零时，将始终应用深度测试。设置为Number.POSITIVE_INFINITY时，永远不会应用深度测试。
  }
  ```

## DC.Label

> 标签要素，继承于[Overlay](#overlay)

### exmaple

```js
let position = new DC.Position(120, 20)
let Label = new DC.Label(position, 'test')
```

### creation

- **_constructor(position,text)_**

  DC.Label 构造函数

  - 参数
    - `{DC.Position} position`：坐标
    - `{String} text`：文本
  - 返回值：`label`

### properties

- `{DC.Position} position`：坐标
- `{String} text`：文本

### methods

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式，详情参考：[LabelGraphics](https://cesium.com/docs/cesiumjs-ref-doc/LabelGraphics.html)
  - 返回值：`this`

  ```json
  // 样式参数(可选)
  {
    "font": "30px sans-serif", // CSS 字体设置
    "scale": 1, //比例
    "pixelOffset": { "x": 0, "y": 0 }, //偏移像素
    "showBackground": false, //是否显示背景
    "backgroundColor": DC.Color.BLACK, //背景颜色
    "backgroundPadding": { "x": 0, "y": 0 }, //背景间隙
    "fillColor": DC.Color.BLACK, //文字颜色
    "outlineColor": DC.Color.WHITE, //边框颜色
    "outlineWidth": 0, //边框大小，
    "scaleByDistance": {
      "near": 0, //最近距离
      "nearValue": 0, //最近距离值
      "far": 1, //最远距离值
      "farValue": 0 //最远距离值
    }, //根据距离设置比例
    "translucencyByDistance": {
      "near": 0, //最近距离
      "nearValue": 0, //最近距离值
      "far": 1, //最远距离值
      "farValue": 0 //最远距离值
    }, //根据距离设置透明度
    "distanceDisplayCondition": {
      "near": 0, //最近距离
      "far": Number.MAX_VALUE //最远距离
    }, //根据距离设置可见
    "disableDepthTestDistance": 0 // 深度检测距离，用于防止剪切地形，设置为零时，将始终应用深度测试。设置为Number.POSITIVE_INFINITY时，永远不会应用深度测试。
  }
  ```

## DC.Circle

> 圆要素，继承于[Overlay](#overlay)

### exmaple

```js
let position = new DC.Position(120, 20)
let circle = new DC.Circle(position, 200)
```

### creation

- **_constructor(center, radius)_**

  DC.Billboard 构造函数

  - 参数
    - `{DC.Position} center`：坐标
    - `{String} radius`：半径
  - 返回值：`billboard`

### properties

- `{DC.Position} center`：坐标
- `{String} radius`：半径

### methods

- **_setLabel(text, textStyle)_**

  设置标签

  - 参数
    - `{String} text`：文本
    - `{String} textStyle`：文本样式，详情参考：[DC.Label](#dc-label)
  - 返回值：`this`

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式，详情参考：[EllipseGraphics](https://cesium.com/docs/cesiumjs-ref-doc/EllipseGraphics.html)
  - 返回值：`this`

  ```json
  // 样式参数(可选)
  {
    "height": 1, //高度
    "extrudedHeight": 0, //拉升高度
    "stRotation": 0, //旋转角度
    "material": DC.Color.WHITE, //材质
    "outline": false, //是否显示边框
    "outlineColor": DC.Color.BLACK, //边框颜色
    "outlineWidth": 0, //边框宽度
    "shadows": 0, //阴影类型，0：禁用、1：启用 、2：投射、3：接受
    "distanceDisplayCondition": {
      "near": 0, //最近距离
      "far": Number.MAX_VALUE //最远距离
    }, //根据距离设置可见
    "classificationType": 2, //分类 是否影响地形，3D切片或同时影响这两者。0:地形、1:3D切片、2：两者
    "zIndex": 0 //层级
  }
  ```

## DC.Model

> 模型要素，继承于[Overlay](#overlay)

### exmaple

```js
let position = new DC.Position(120, 20)
let model = new DC.Model(position, '**/**.glb')
```

### creation

- **_constructor(position, modelUrl)_**

  DC.Model 构造函数

  - 参数
    - `{DC.Position} position`：坐标
    - `{String} modelUrl`：模型地址
  - 返回值：`model`

### properties

- `{DC.Position} position`：坐标
- `{String} modelUrl`：模型地址

### methods

- **_setLabel(text, textStyle)_**

  设置标签

  - 参数
    - `{String} text`：文本
    - `{String} textStyle`：文本样式，详情参考：[DC.Label](#dc-label)
  - 返回值：`this`

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式，详情参考：[ModelGraphics](https://cesium.com/docs/cesiumjs-ref-doc/ModelGraphics.html)
  - 返回值：`this`

  ```json
  // 样式参数(可选)
  {
    "scale": 1, //比例
    "minimumPixelSize": 0, //指定模型的最小像素大小，而不考虑缩放
    "maximumScale": 0, //指定模型的最大比例
    "shadows": 0, //阴影类型，0：禁用、1：启用 、2：投射、3：接受
    "silhouetteColor": DC.Color.RED, //轮廓颜色
    "silhouetteSize": 0, //轮廓宽度
    "lightColor": DC.Color.RED, //模型着色时指定灯光颜色
    "distanceDisplayCondition": {
      "near": 0, //最近距离
      "far": Number.MAX_VALUE //最远距离
    } //根据距离设置可见
  }
  ```

## DC.Tileset

> 3Dtiles 模型要素，继承于[Overlay](#overlay)

### exmaple

```js
let position = new DC.Position(120, 20)
let tileset = new DC.Tileset('**/tileset.json')
```

### creation

- **_constructor(url,[options])_**

  DC.Tileset 构造函数

  - 参数
    - `{String} url`：模型地址
    - `{Object} options`：详情参考：[Tileset](https://cesium.com/docs/cesiumjs-ref-doc/Cesium3DTileset.html)
  - 返回值：`model`

### properties

-`{Promise} readyPromise`：加载完成后的异步函数

### methods

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式，详情参考：[TileStyle](https://github.com/CesiumGS/3d-tiles/tree/master/specification/Styling)
  - 返回值：`this`

  ```js
  let style = new DC.TilesetStyle({
    color: {
      conditions: [
        ['${Height} >= 100', 'color("purple", 0.5)'], //Height 为模型设置的属性
        ['${Height} >= 50', 'color("red")'],
        ['true', 'color("blue")']
      ]
    },
    show: '${Height} > 0'
  })
  ```

- **_setPosition(position)_**

  设置位置

  - 参数
    - `{DC.Position} position`：位置
  - 返回值：`this`

- **_setHeight(height,duration)_**

  设置高度

  - 参数
    - `{Number} height`：高度
    - `{Number} duration`：间隔，单位：秒
  - 返回值：`this`

- **_setFeatureProperty(properties)_**

  根据现有的属性添加属性

  - 参数
    - `{Array<Object>} properties`: 属性
  - 返回值：`this`

```json
//属性参数
{
  "key": "name", //已有属性名称
  "keyValue": "1", //已有属性值
  "propertyName": "highlight", //新增属性名称
  "propertyValue": true //新增属性值
}
```

## DC.DivIcon

> DivIcon 要素，继承于[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let divIcon = new DC.DivIcon(position, '<div></div>')
```

### creation

- **_constructor(position, content)_**

  DC.DivIcon 构造函数

  - 参数
    - `{DC.Position} position`：坐标
    - `{String|Element} content`：内容
  - 返回值：`divIcon`

### properties

- `{DC.Position} position`：坐标

### methods

- **_addClass(name)_**

  添加 Css 类名

  - 参数
    - `{String} name`：类名
  - 返回值：`this`

## Effect

> 效果基类

:::warning
该类无法实例化
:::

### properties

- `{Sting} id`：唯一标识 **_`readonly`_**
- `{Sting} type`：类型 **_`readonly`_**

### methods

- **_addToViewer(viewer)_**

  添加效果到场景

  - 参数
    - `{DC.Viewer} viewer`：场景
  - 返回值：`this`

## DC.RainEffect

> 雨天效果，继承于[Effect](#effect)

### exmaple

```js
let rainEffect = new DC.RainEffect('rain')
viewer.addEffect(rainEffect)
```

### creation

- **_constructor(id)_**

  DC.RainEffect 构造函数

  - 参数
    - `{String} id`：唯一标识
  - 返回值：`rainEffect`

## DC.SnowEffect

> 雪天效果，继承于[Effect](#effect)

### exmaple

```js
let snowEffect = new DC.SnowEffect('rain')
viewer.addEffect(snowEffect)
```

### creation

- **_constructor(id)_**

  DC.SnowEffect 构造函数

  - 参数
    - `{String} id`：唯一标识
  - 返回值：`snowEffect`

## DC.FogEffect

> 雾天效果，继承于[Effect](#effect)

### exmaple

```js
let fogEffect = new DC.FogEffect('fog', DC.Color.RED)
viewer.addEffect(fogEffect)
```

### creation

- **_constructor(id,color,trength)_**

  DC.FogEffect 构造函数

  - 参数
    - `{String} id`：唯一标识
    - `{DC.Color} color`：颜色
    - `{Number} trength`：强度
  - 返回值：`fogEffect`

## DC.BloomEffect

> 泛光效果，继承于[Effect](#effect)

### exmaple

```js
let bloomEffect = new DC.BloomEffect('fog', DC.Color.RED)
viewer.addEffect(bloomEffect)
```

### creation

- **_constructor(id)_**

  DC.BloomEffect 构造函数

  - 参数
    - `{String} id`：唯一标识
  - 返回值：`bloomEffect`

### properties

- `{Number} contrast`：对比度 **_writeonly_**
- `{Number} brightness`：亮度 **_writeonly_**

## DC.RadarScanEffect

> 雷达扫描效果，继承于[Effect](#effect)

### exmaple

```js
let position = new DC.Position(120, 20)
let radarScanEffect = new DC.RadarScanEffect(
  'radar',
  position,
  200,
  DC.Color.RED,
  5
)
viewer.addEffect(radarScanEffect)
```

### creation

- **_constructor(id,position,radius,color,duration)_**

  DC.RadarScanEffect 构造函数

  - 参数
    - `{String} id`：唯一标识
    - `{DC.Position} position`：位置
    - `{Number} radius`：半径
    - `{DC.Color} color`：颜色
    - `{Number} duration`：间隔，单位：秒
  - 返回值：`radarScanEffect`

## DC.CicleScanEffect

> 雷达扫描效果，继承于[Effect](#effect)

### exmaple

```js
let position = new DC.Position(120, 20)
let cicleScanEffect = new DC.CicleScanEffect(
  'circle',
  position,
  200,
  DC.Color.RED,
  5
)
viewer.addEffect(cicleScanEffect)
```

### creation

- **_constructor(id,position,radius,color,duration)_**

  DC.CicleScanEffect 构造函数

  - 参数
    - `{String} id`：唯一标识
    - `{DC.Position} position`：位置
    - `{Number} radius`：半径
    - `{DC.Color} color`：颜色
    - `{Number} duration`：间隔，单位：秒
  - 返回值：`cicleScanEffect`

## DC.GlobeRotate

> 地球自转

### example

```js
new DC.GlobeRotate(viewer, 5, () => {})
```

### creation

- **_constructor(viewer,duration,callback,context)_**

  DC.GlobeRotate 构造函数

  - 参数
    - `{DC.Viewer} viewer`：3D 场景
    - `{Number} duration`：间隔，单位：秒
    - `{Function} callback`：回调函数
    - `{Object} context`：回调上下文
  - 返回值：`globeRotate`

## DC.T

> 坐标转换

```js
let cartesian3 = DC.T.transformWSG84ToCartesian(new DC.Position(120, 20))
```

### static methods

- **_transformCartesianToWSG84(cartesian)_**

  世界坐标转换为 84 坐标

  - 参数
    - `{Cartesian3} cartesian`：世界坐标
  - 返回值：`position`

- **_transformWSG84ToCartesian(position)_**

  84 坐标转换为世界坐标

  - 参数
    - `{DC.Position} position`：84 坐标
  - 返回值：`cartesian`

- **_transformWSG84ToCartographic(position)_**

  84 坐标转换为制图坐标

  - 参数
    - `{DC.Position} position`：84 坐标
  - 返回值：`cartographic`

- **_transformCartesianArrayToWSG84Array(cartesianArr)_**

  世界坐标数组转 84 坐标数组

  - 参数
    - `{Array<cartesian3>} cartesianArr`：世界坐标数组
  - 返回值：`array`

- **_transformWSG84ArrayToCartesianArray(WSG84Arr)_**

  84 坐标数组转世界坐标数组

  - 参数
    - `{Array<cartesian3>} WSG84Arr`：84 坐标
  - 返回值：`array`

- **_transformWGS84ToGCJ02(lng,lat)_**

  WGS84 to GCJ02

  - 参数
    - `{Number} lng`：经度
    - `{Number} lat`：纬度
  - 返回值：`position`

- **_transformGCJ02ToWGS84(lng, lat)_**

  GCJ02 to WGS84

  - 参数
    - `{Number} lng`：经度
    - `{Number} lat`：纬度
  - 返回值：`position`

- **_transformWGS84ToBD09(lng, lat)_**

  WGS84 to BD09

  - 参数
    - `{Number} lng`：经度
    - `{Number} lat`：纬度
  - 返回值：`position`

- **_transformBD09ToWGS84(lng, lat)_**

  BD09 to WGS84

  - 参数
    - `{Number} lng`：经度
    - `{Number} lat`：纬度
  - 返回值：`position`

- **_transformBD09ToGCJ02(lng, lat)_**

  BD09 to GCJ02

  - 参数
    - `{Number} lng`：经度
    - `{Number} lat`：纬度
  - 返回值：`position`

## DC.Util

> 工具类

### static methods

- **_uuid(prefix)_**

  生成 uuid

- **_merge(dest, ...sources)_**

  属性合并

## DC.DomUtil

> Dom 工具类

### static methods

- **_create(tagName, className, container)_**

  创建 dom

- **_addClass(el, name)_**

  添加类名

- **_removeClass(el, name)_**

  删除类名

<style>
.theme-default-content:not(.custom){
max-width:900px !important;
}
.theme-default-content code{
color: #e96900 !important;
}
.theme-default-content li a:has(> code){
color: #e96900 !important;
}
.hiden{
hight: 0;
}
</style>

## DC.GaeaService

> Gaea 服务类

### examples

```js
DC.GaeaService.url = ''
DC.GaeaService.getLayerTree()
```

### static methods

- **_getLayerTree()_**

  获取图层数

- **_suggestSearch()_**

  关键字搜索

- **_propSearch(postData)_**

  属性搜索

- **_propSearchByAmap(key, searchText, nowPage, pageSize)_**

  高德属性搜索

- **_getBufferOp(postData)_**

  缓冲

- **_interSpaceSearch(postData)_**

  交叉搜索

- **_getFeature(postData)_**

  获取要素
