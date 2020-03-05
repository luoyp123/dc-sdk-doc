---
sidebar: auto
---

# 快速上手 ✍

## 简介

> GSpace

- '零'客户端，无需安装任何插件，只需浏览器支持 WebGL
- 多端支持，支持跨平台和跨浏览器
- 二维、三维一体
- 敏捷开发，开发人员通过简单的代码就可以开发 3D 应用，接口简单，可以快速二次开发
- 支持各类地图的加载，包括 google 地图、arcgis 地图、天地图、百度、高德、腾讯以及自定义离线地图
- 支持各类开放协议的数据，包括 shp 、 3dmax、gltf 、glb、 kml,、czml、geoJson、3d tiles(流式文件) 、 las(点云数据)
- 支持第三方数据可视化插件， 包括 echarts、mapv、heatmap 等
- 提供地图的常用的工具，包括测距、面积、点位拾取、位置查询等。用户也可以通过开放接口自定义地图工具
- 提供 WebGL 动画，包括爆炸扩散、道路动画、点位闪烁以及各类天气等
- 提供开放式的接口服务，包括堵控圈、道路规划、路径纠正、空间计算等
- 提供可视化控件，包括轨迹回放、指北针、位置信息、视频控件、图层树等
- 提供统一的数据编辑工具，包括模型摆放、专题数据采集、漫游数据规划等
- 支持亿级数据的展示

## 环境准备

> 操作系统

**`推荐 Win10`**

> 浏览器：

**`浏览器需支持 WegGL`**

<sub>表格中的数字表示支持 WegGL 的第一个浏览器版本号。</sub>

<table>
  <tr>
   <td>浏览器</td>
   <td> <img src="//gspace.sz-map.com/images/compatible_chrome.gif" style="width:30px;height:30px" /></td>
   <td> <img src="//gspace.sz-map.com/images/compatible_ie.gif" style="width:30px;height:30px"/> </td>
   <td> <img src="//gspace.sz-map.com/images/compatible_firefox.gif" style="width:30px;height:30px"/></td>
   <td> <img src="//gspace.sz-map.com/images/compatible_safari.gif" style="width:30px;height:30px"/></td>
   <td> <img src="//gspace.sz-map.com/images/compatible_opera.gif" style="width:30px;height:30px" /></td>
  </tr>
  <tr>
   <td>版本</td>
   <td>4.0</td>
   <td>9.0</td>
   <td>2.0</td>
   <td>3.1</td>
   <td>9.0</td>
  </tr>
</table>

> 客户端硬件推荐：

<table>
  <tr>
   <th>机器</th>
   <th width="20%" >硬件</thwidth="30%">
   <th width="30%">最低配置</th>
   <th width="30%">推荐配置</th>
  </tr>
  <tr>
   <td rowspan='3'>笔记本</td>
   <td >CPU</td>
   <td >I5-9400</td>
   <td >I7-9750</td>
  </tr>
  <tr>
   <td >显卡</td>
   <td >NVIDIA GTX1660Ti 6G</td>
   <td >NVIDIA RTX2060 6G </td>
  </tr>
  <tr>
   <td >内存</td>
   <td >16G</td>
   <td >32G</td>
  </tr>
  <tr>
   <td rowspan='3'>台式机</td>
   <td >CPU</td>
   <td >I5-9600</td>
   <td >I7-9700</td>
  </tr>
  <tr>
   <td >显卡</td>
   <td >NVIDIA GTX1060 6G</td>
   <td >NVIDIA RTX2060 6G</td>
  </tr>
  <tr>
   <td >内存</td>
   <td >16G</td>
   <td >32G</td>
  </tr>
  <tr>
   <td rowspan='3'>工作站</td>
   <td >CPU</td>
   <td >至强 e3-1225</td>
   <td >至强 e5-2650</td>
  </tr>
  <tr>
   <td >显卡</td>
   <td >NVIDIA M4000</td>
   <td >NVIDIA M5000</td>
  </tr>
  <tr>
   <td >内存</td>
   <td >16G</td>
   <td >32G</td>
  </tr>
</table>

> 服务器硬件推荐：

<table>
  <tr>
   <th>硬件</th>
   <th >配置</th>
  </tr>
  <tr>
  <tr>
   <td >CPU</td>
   <td >16核</td>
  </tr>
  <tr>
   <td >内存</td>
   <td >64G</td>
  </tr>
  <tr>
   <td >硬盘</td>
   <td >1T SSD * 2</td>
  </tr>
</table>

> 资源服务器：

**Niginx、Apache Httpd、Node**

## 开发准备

> 开发者需要熟悉 Js、Html5、Css3，了解 Canvas 开发

> 前端开发工具或 IDE

## SDK

> 该 SDK 为基础,使用 GSpace 时需要添加，还需加载 GSpace 框架包。
> [SDK 包]()

### Web SDK

::: danger
该 SDK 需要申请许方可使用，请联系相关人员申请。
:::

> 本地环境

::: danger
请与相关人员联系，获取本地 SDK
:::

> 开发环境

```html
<script
  type="text/javascript"
  src="//gspace.gaeainfo.com/lib/gs/v2/gs.core.js"
></script>
<link rel="stylesheet" href="//gspace.sz-map.com/lib/gs/v2/gs.core.css" />
```

::: warning
开发环境有水印，发布项目时请使用生产环境的框架
:::

> 生产环境

```html
<script
  type="text/javascript"
  src="//gspace.gaeainfo.com/lib/gs/v2/gs.core.min.js"
></script>
<link rel="stylesheet" href="//gspace.sz-map.com/lib/gs/v2/gs.core.min.css" />
```

### 类图

> SDK 中类，使用时需要添加命名空间

 <img src="//gspace.gaeainfo.com//images/gs-sdk.png" style="width:100%;height:800px">

### API 说明

<a href="../api" target="_blank" rel="noopener noreferrer" class="nav-link external"><svg xmlns="http://www.w3.org/2000/svg" aria-hidden="true" x="0px" y="0px" viewBox="0 0 100 100" width="15" height="15" class="icon outbound"><path fill="currentColor" d="M18.8,85.1h56l0,0c2.2,0,4-1.8,4-4v-32h-8v28h-48v-48h28v-8h-32l0,0c-2.2,0-4,1.8-4,4v56C14.8,83.3,16.6,85.1,18.8,85.1z"></path> <polygon fill="currentColor" points="45.7,48.7 51.3,54.3 77.2,28.5 77.2,37.2 85.2,37.2 85.2,14.9 62.8,14.9 62.8,22.9 71.5,22.9"></polygon></svg></a>

<style>
  .theme-default-content:not(.custom){
   max-width: 85% !important;
  }

  .bull{
    text-align:center;
    font-size:20px;
    font-weight:bold;
  }
  
</style>
