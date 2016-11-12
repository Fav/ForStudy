---
layout: post
title: cesium-viewer
tags: cesiumjs
categories: cesiumjs教程
---

调用方法
new Cesium.Viewer(container, options)

名称 | 类型 | 描述
--- |---|---
container | Element or String   | 放置地图部件的 DOM对象或者ID
options   | Object              | 参数(见下表)

名称 | 类型 | 默认值 | 描述
---|---|---|---
animation | Boolean | TRUE | 是否创建 Animation 控件
baseLayerPicker | Boolean | TRUE | 是否创建 基础图层选择 控件
fullscreenButton | Boolean | TRUE | 是否创建 全屏 控件
vrButton | Boolean | FALSE | 是否创建 vr按钮 控件
geocoder | Boolean | TRUE | 是否创建 查询 控件 
homeButton | Boolean | TRUE | 是否创建 初始位置 控件
infoBox | Boolean | TRUE | 是否创建 infoBox 控件
sceneModePicker | Boolean | TRUE | 是否创建 2D/3D选择 控件
selectionIndicator | Boolean | TRUE |是否创建 selectionIndicator 控件
timeline | Boolean | TRUE | 是否创建 时间线 控件
navigationHelpButton | Boolean | TRUE | 是否创建 导航帮助按钮 控件
navigationInstructionsInitiallyVisible | Boolean | TRUE | 为是时，初始显示导航帮助面板，否则只有用户点击导航帮助按钮才显示
scene3DOnly | Boolean | FALSE | 为是时，所有的集合体将会以3D状态显示来节约GPU资源
clock | Clock | new Clock() | 初始化当前时间
selectedImageryProviderViewModel | ProviderViewModel |  | 设置当前基础图层的视图模式,不可用时会使用默认地图列表中第一个，只有baseLayerPicker为true才能设置
imageryProviderViewModels | Array.<ProviderViewModel> | createDefaultImageryProviderViewModels() | 设置可选地图服务的类型，baseLayerPicker为true时可用
selectedTerrainProviderViewModel | ProviderViewModel |  | 设置基础地形，baseLayerPicker为true时可用
terrainProviderViewModels | Array.<ProviderViewModel> | createDefaultTerrainProviderViewModels() | 设置当前地形服务,不可用时会使用默认地图列表中第一个，只有baseLayerPicker为true才能设置
imageryProvider | ImageryProvider | new BingMapsImageryProvider() |设置地图服务，baseLayerPicker为false时可用
terrainProvider | TerrainProvider | new EllipsoidTerrainProvider() | 设置地形服务
skyBox | SkyBox |  | 设置天空背景，未定义时使用默认星空
skyAtmosphere | SkyAtmosphere |  | 设置蓝天，地球周围的光圈
fullscreenElement | Element or String | |全屏时显示在屏幕上的元素
useDefaultRenderLoop | Boolean | TRUE | 是否能控制渲染循环
targetFrameRate | Number |  | 设置刷新速率，使用默认渲染循环时可用
showRenderLoopErrors | Boolean | TRUE | 设置是否弹出错误提示框
automaticallyTrackDataSourceClocks | Boolean | TRUE | 设置为True，时间会自动更新
contextOptions | Object |  | 设置[Scene]()中的Context 和 WebGL 属性
sceneMode | SceneMode | SceneMode.SCENE3D | 设置初始化显示模式
mapProjection | MapProjection | new GeographicProjection() | 设置投影
globe | Globe | new Globe(mapProjection.ellipsoid) | 是否显示三维球，设置成false不添加(可用)
orderIndependentTranslucency | Boolean | TRUE | 顺序无关透明度？
creditContainer | Element or String | | 设置版权信息，时间条上的描述字段
dataSources | DataSourceCollection | new DataSourceCollection() | 可选的由小部件可视化的数据源的集合。如果提供了这个参数，则假定该实例被调用方拥有，并且在销毁的时候不会被销毁
terrainExaggeration | Number | 1 | 可选一个用于夸大地形的标量。请注意，地形渲染不会修改任何其他原始的，因为他们是相对的椭球体。
shadows | Boolean | FALSE | 是否显示阳光照射的阴影
terrainShadows | [ShadowMode]() | ShadowMode.RECEIVE_ONLY | 是否接收或反射太阳光
mapMode2D | [MapMode2D]() | MapMode2D.INFINITE_SCROLL | 设置二维地图是否可旋转或者水平方向添加滚动条



### 属性
***
**allowDataSourcesToSuspendAnimation** : Boolean  
**animation** *readonly* : Animation 获取Animation控件.  
**baseLayerPicker** *readonly* : BaseLayerPicker 获取BaseLayerPicker控件.  
**bottomContainer** *readonly* :  获取文字描述控件
**camera** *readonly* : Camera 获取 camera.  
**canvas** *readonly* : Canvas 获取 canvas.  
**cesiumLogo** *readonly* : 获取 Cesium logo element.  
**cesiumWidget** *readonly* : CesiumWidget Gets the CesiumWidget.  
**clock** *readonly* : Clock 获取clock.  
**container** *readonly* : Element 获取父控件.  
**dataSourceDisplay** *readonly* : DataSourceDisplay Gets the display used for DataSource visualization.  
**dataSources** *readonly* : DataSourceCollection Gets the set of DataSource instances to be visualized.  
**entities** *readonly* : EntityCollection Gets the collection of entities not tied to a particular data source. T  
**fullscreenButton** *readonly* : FullscreenButton Gets the FullscreenButton.  
**geocoder** *readonly* : Geocoder 获取 Geocoder.  
**homeButton** *readonly* : HomeButton 获取 HomeButton.  
**imageryLayers** *readonly* : ImageryLayerCollection 获取imageryLayers集合      
**infoBox** *readonly* : InfoBox 获取 info box.  
**navigationHelpButton** *readonly* : NavigationHelpButton 获取 NavigationHelpButton.  
**resolutionScale** : Number 屏幕640x480时设置0.5会显示320x240；默认值为1  
**scene** *readonly* : Scene Gets the scene.  
**sceneModePicker** *readonly* : SceneModePicker Gets the SceneModePicker.  
**screenSpaceEventHandler** *readonly* : ScreenSpaceEventHandlerGets the screen space event handler.  
**selectedEntity** : Entity Gets or sets the object instance for which to display a selection indicator.  
**selectionIndicator** *readonly* : SelectionIndicator Gets the selection indicator.  
**shadowMap** *readonly* : ShadowMap Get the scene's shadow map  
**shadows** : Boolean Determines if shadows are cast by the sun.  
**targetFrameRate** : Number   
**terrainProvider** : TerrainProvider The terrain provider providing surface geometry for the globe.  
**terrainShadows** : ShadowMode Determines if the terrain casts or shadows from the sun.  
**timeline** *readonly* : Timeline Gets the Timeline widget.  
**trackedEntity** : Entity Gets or sets the Entity instance currently being tracked by the camera.  
**useDefaultRenderLoop** : Boolean   
**vrButton** *readonly* : VRButton Gets the VRButton.  

### 方法
***
**destroy**()  移除时调用  
**extend**(mixin, options)   
**flyTo**(target, options)   
**forceResize**()  
**isDestroyed**() → Boolean   
**render**()  
**resize**()  
**zoomTo**(target, offset) → Promise.<Boolean>  
