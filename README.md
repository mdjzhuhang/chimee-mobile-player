# ChimeeMobilePlayer

这是基于[chimee](https://github.com/Chimeejs/chimee)集成的一套您可以直接使用的HTML5移动端播放器，提供有了默认样式。

并集成了以下官方UI插件：
> 1. [chimee-plugin-mobile-controlbar](https://github.com/Chimeejs/chimee-plugin-mobile-controlbar)
> 2. [chimee-plugin-mobile-state](https://github.com/Chimeejs/chimee-plugin-mobile-state)

## 安装

首先根据您的业务场景，你可以直接将lib目录下适合的打包文件引入您的业务代码中，比如直接使用`<script src='./lib/chimee-mobile-player.browser.js'></script>`引用JS。

或者您的项目基于nodejs环境构建的话，直接执行 `npm install chimee-mobile-player --save`，然后再在代码中`import ChimeeMobilePlayer from 'chimee-mobile-player';`即可。

## 基本用法

基于点播场景，可以这样使用：

```javascript
new ChimeeMobilePlayer({
  wrapper: '#wrapper',  // video dom容器
  src: 'http://cdn.toxicjohann.com/lostStar.mp4',
  autoplay: true,
  controls: true,
  playsInline: true,
  preload: true,
  x5VideoPlayerFullscreen: true,
  x5VideoOrientation: true,
  xWebkitAirplay: true,
  muted: true,
  // removeInnerPlugins: ['chimeeMobiControlbar', 'chimeeState'] // 需要移除的插件
});
```

如果您需要的是直播场景场景，可以根据您的媒体容器类型，参考以下配置：

```javascript
// HLS 直播
new ChimeeMobilePlayer({
  wrapper: '#wrapper',  // video dom容器
  src: 'http://chimee.org/xxx/fff.m3u8',
  isLive: true,
  autoplay: true,
  controls: true,
  playsInline: true,
  preload: true,
  x5VideoPlayerFullscreen: true,
  x5VideoOrientation: true,
  xWebkitAirplay: true,
  muted: true,
  // removeInnerPlugins: ['chimeeMobiControlbar', 'chimeeState'] // 需要移除的插件
});

```

## 注意

0. 默认配置是自带控制条和中部状态的，通过配置可以去掉
1. 暂不支持在该元素上使用缩放 zoom / scale
2. ios 上的声音和机器的声音同步，并非设置 volume 可以改变，muted 是有效果的。
3. 在 chimee@0.8.3 之后将 playsline / x5VideoPlayerType 分开配置。

*希望您用着方便，有相应问题请随时反馈。*
