#  [EZUIKit-JavaScript-npm][ezuikit-js]
>轻应用npm版本，降低接入难度，适配自定义UI，适配主流框架

> 低延时预览，云存储回放，SD卡回放

> 功能API丰富，如:play 控制，音频控制，视频截图，实时get 视频OSDTime，视频录制，Device 对讲，电子放大，fullscreen等



### get ezuikit-js

```
$ npm install ezuikit-js
```
### 引入ezuikit-js

```
import EZUIKit from 'ezuikit-js';
```

#### 如果你使用原生 method ,可以通过标签引用
```
  <script src="./ezuikit.js"></script>
```

### start 使用 - initialization
>基本使用

create DOM

```
  <div id="video-container"></div>
```

## play 器initialization
### 直播
```
    var player = new EZUIKit.EZUIKitPlayer({
      id: 'video-container', // 视频容器ID
      accessToken: 'at.3bvmj4ycamlgdwgw1ig1jruma0wpohl6-48zifyb39c-13t5am6-yukyi86mz',
      url: 'ezopen://open.ys7.com/G39444019/1.live',
      width: 600,
      height: 400,
    })
```
### 回放
```
    var player = new EZUIKit.EZUIKitPlayer({
      id: 'video-container', // 视频容器ID
      width: 600,
      height: 400,
      accessToken: 'at.3bvmj4ycamlgdwgw1ig1jruma0wpohl6-48zifyb39c-13t5am6-yukyi86mz',
      url: 'ezopen://open.ys7.com/G39444019/1.rec'
    })
```
#### tips
为方便开发者快速接入  

我们提供了测试accessToken,测试play address，并提供了几种常用场景使用示例。你可以通过使用示例，使用测试play address，测试accessToken，在你的应用快速接入。  

<b>测试play address:</b> ezopen://open.ys7.com/G39444019/1.live  

你可以通过以下addressget 到测试accessToken <a href="https://open.ys7.com/jssdk/ezopen/demo/token" target="_blank">get 测试accessToken</a> 用来play 上述测试play address。 

#### 最佳实践tips

1. 我们在v0.6.2及以上版本持用户通过Turn on 谷歌实验室特性启动多线程解码，多线程模式将大大提升解码效率，降低解码内存消耗。  

>>[Turn on 多线程方式1](https://open.ys7.com/help/384)  (https://open.ys7.com/help/384)

>>[Turn on 多线程方式2](https://open.ys7.com/help/385)(https://open.ys7.com/help/385)  

2. 视频解码库默认从开放平台远程拉取，你可以将解码库放到本地或者你的服务内，可以提升Load 解码库速度。 

 >> <b>使用本地解码库提升Load 速度</b>  <a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/localDecoder.html" target="_blank">本地解码库示例</a> 

### 使用示例
> 1. 快速create 视频play 页面  

&emsp;&emsp;&emsp;&emsp;<b>基本使用:</b>  <a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/base.html" target="_blank">基本使用示例</a>  

> 2. forward往[开放平台轻应用模板管理页](https://open.ys7.com/console/ezuikit/template.html)create 一个主题，可以动态配置你的play 主题，控件，示例展示了get 一个主题后使用示例。  

&emsp;&emsp;&emsp;&emsp;<b>自定义主题:</b>  <a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/template.html" target="_blank">自定义主题示例</a>  

> 3. 你可以本地create 一个主题配置，可以本地配置你的play 主题，控件，示例展示了本地配置项使用示例。  

&emsp;&emsp;&emsp;&emsp;<b>本地主题配置:</b>  <a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/themeData.html" target="_blank">本地主题配置示例</a>  

> 4. 我们提供了一些universal场景的主题，PC端预览，PC端回放，移动端预览，移动端回放，你也可以直接使用。  


&emsp;&emsp;&emsp;&emsp;<b>PC端预览-固定主题:</b>
<a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/pcLive.html" target="_blank">PC端预览-固定主题示例</a>  

&emsp;&emsp;&emsp;&emsp;<b>PC端回放-固定主题:</b>
<a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/pcRec.html" target="_blank">PC端回放-固定主题示例</a>  

&emsp;&emsp;&emsp;&emsp;<b>移动端预览-固定主题:</b>
<a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/mobileLive.html" target="_blank">移动端预览-固定主题示例</a>  

&emsp;&emsp;&emsp;&emsp;<b>移动端回放-固定主题:</b>
<a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/mobileRec.html" target="_blank">移动端回放-固定主题示例</a>  

>同一个页面play 多个视频，可以参考:  

&emsp;&emsp;&emsp;&emsp;<b>单页面多实例(视频多窗口):</b>
<a href="https://github.com/Ezviz-OpenBiz/EZUIKit-JavaScript-npm/blob/master/demos/base-demo/multi.html" target="_blank">单页面多实例(视频多窗口)示例</a>  

#### 附录: initializationparameter 说明

<table>
<tr><th>parameter 名</th><th>类型</th><th>描述</th><th>是否必选</th></tr>
<tr><td>id</td><td>String</td><td>play 器容器DOM的id</td><td>Y</td></tr>
<tr><td>accessToken</td><td>String</td><td>授权过程get 的access_token</td><td>Y</td></tr>
<tr><td>url</td><td>String</td><td>

#### 直播
##### 标清
ezopen://
/${Device 序列号}/{通道号}.live<br/>
##### 高清
ezopen://open.ys7.com/${Device 序列号}/{通道号}.hd.live<br/>

#### 回放
##### sd卡回放
initializationparameter  url值为:<br/>
ezopen://open.ys7.com/${Device 序列号}/{通道号}.rec?begin=yyyyMMddhhmmss
##### 云存储回放
initializationparameter  url值为:<br/>
ezopen://open.ys7.com/${Device 序列号}/{通道号}.cloud.rec?begin=yyyyMMddhhmmss
视频ezopen协议play address 详见:<a href="https://open.ys7.com/help/23" target="_blank">ezopen协议</a>	</td><td>Y</td></tr>
<tr><td>audio</td><td>boolean</td><td>是否默认Turn on 声音 true:打开（默认） false: Close 	</td><td>N</td></tr>
<tr><td>width</td><td>int</td><td>视频宽度，默认值为容器容器DOM宽度	</td><td>Y</td></tr>
<tr><td>height</td><td>int</td><td>视频高度，默认值为容器容器DOM高度</td><td>Y</td></tr>
<tr><td>template</td><td>String</td><td>  


<table style="display:inline-block;width:700px">
<tr><th>模板值</th><th>描述</th></tr>

<tr><td>simple</td><td>极简版 *固定模板 仅包含视频play 窗口，create 实例后通过 method 集控制视频播<br />放相关功能</td></tr>

<tr><td>standard</td><td>标准版;   *固定模板 包含视频窗口，叠加了stop，录制，fullscreen控件（通过<br />控件快捷Transfer method 集合控制视频play 相关功能，但你仍然可以通过 method 集直接控制视频play 相关功<br />能。下同）</td></tr>

<tr><td>security</td><td>安防版(预览回放);  *固定模板 包含视频窗口，叠加了录制，fullscreen控件，<br />标清/高清 switch，预览录制 switch控件*</td></tr>
<tr><td>voice</td><td>voice版;  *固定模板 包含视频窗口，叠加了录制，fullscreen控件，Voice Broadcast，voice<br />对讲控件*</td></tr>
<tr><td>pcLive</td><td>	*固定模板 button列表，颜色，底部头部背景色固定，可用于pc端预览，如需<br />修改button配置，头部底部背景色，可参考 {{自定义themeId}}，或者使用<br />themeData本地配置*</td></tr>
<tr><td>pcRec</td><td>	*固定模板 button列表，颜色，底部头部背景色固定， 可用于pc端回放，如需<br />修改button配置，头部底部背景色，可参考 {{自定义themeId}}，或者使用themeData<br />本地配置*</td></tr>
<tr><td>mobileLive</td><td>	*固定模板  button列表，颜色，底部头部背景色固定，可用于移动端预<br />览，如需修改button配置，头部底部背景色，可参考 {{自定义themeId}}，或者使用themeData<br />本地配置*</td></tr>
<tr><td>mobileRec</td><td>*固定模板 button列表，颜色，底部头部背景色固定， 可用于移动端回放，<br />如需修改button配置，头部底部背景色，可参考 {{自定义themeId}}，或者使用themeData<br />本地配置*</td></tr>
<tr><td>自定义themeId</td><td>自定义主题，<a href="https://open.ys7.com/console/ezuikit/template.html" target="_blank">forward往开放平台控制台配置页面get </a><br />（v0.6.2版本及以上支持，建议使用 自定义themeId，或者使用themeData本地<br />配置）;</td></tr>
</table>

</td></tr>
<tr><td>themeData</td><td>Object</td><td>
themeData将主题数据本地化，设置本地数据，需要删除templateparameter  <br /> 
你可以通过themeData修改button位置，颜色，头部底部颜色等配置。  

配置示例:  

<pre><code>

{
    "autoFocus": 5,
    "poster":"https://resource.eziot.com/group1/M00/00/89/CtwQEmLl8r-AZU7wAAETKlvgerU237.png",
    "header": {
        "color": "#1890ff",
        "activeColor": "#FFFFFF",
        "backgroundColor": "#000000",
        "btnList": [
            {
                "iconId": "deviceID",
                "part": "left",
                "defaultActive": 0,
                "memo": "顶部Device 名称",
                "isrender": 1
            },
            {
                "iconId": "deviceName",
                "part": "left",
                "defaultActive": 0,
                "memo": "顶部Device ID",
                "isrender": 1
            },
            {
                "iconId": "cloudRec",
                "part": "right",
                "defaultActive": 0,
                "memo": "头部云存储回放",
                "isrender": 0
            },
            {
                "iconId": "rec",
                "part": "right",
                "defaultActive": 0,
                "memo": "头部本地回放",
                "isrender": 0
            }
        ]
    },
    "footer": {
        "color": "#FFFFFF",
        "activeColor": "#1890FF",
        "backgroundColor": "#00000021",
        "btnList": [
            {
                "iconId": "play",
                "part": "left",
                "defaultActive": 1,
                "memo": "play ",
                "isrender": 1
            },
            {
                "iconId": "capturePicture",
                "part": "left",
                "defaultActive": 0,
                "memo": "截屏button",
                "isrender": 1
            },
            {
                "iconId": "sound",
                "part": "left",
                "defaultActive": 0,
                "memo": "声音button",
                "isrender": 1
            },
            {
                "iconId": "pantile",
                "part": "left",
                "defaultActive": 0,
                "memo": "云台控制button",
                "isrender": 1
            },
            {
                "iconId": "recordvideo",
                "part": "left",
                "defaultActive": 0,
                "memo": "录制button",
                "isrender": 1
            },
            {
                "iconId": "talk",
                "part": "left",
                "defaultActive": 0,
                "memo": "对讲button",
                "isrender": 1
            },
            {
                "iconId": "zoom",
                "part": "left",
                "defaultActive": 0,
                "memo": "电子放大",
                "isrender": 1
            },
            {
                "iconId": "hd",
                "part": "right",
                "defaultActive": 0,
                "memo": "清晰度 switchbutton",
                "isrender": 1
            },
            {
                "iconId": "webExpend",
                "part": "right",
                "defaultActive": 0,
                "memo": "web page fullscreenbutton",
                "isrender": 1
            },
            {
                "iconId": "expend",
                "part": "right",
                "defaultActive": 0,
                "memo": "global fullscreenbutton",
                "isrender": 1
            }
        ]
    }
}
</code></pre>

</td><td>N</td></tr>
<tr><td>plugin</td><td>String</td><td>按需Load 插件，可选值: talk:对讲，示例:plugin:["talk"] </td><td>N</td></tr>
<tr><td>handleSuccess</td><td>function</td><td>Automatic play  success Callback</td><td>N</td></tr>
<tr><td>seekFrequency </td><td>function</td><td>为避免频繁拖动play abnormal，可设置模板回放时间轴拖动防抖间隔，默认值为2000（2秒），可取2000（2秒），3000（3秒），4000（4秒），5000（5秒）</td><td>N</td></tr>
</table>


###  method Transfer
> 同步 method （方式1）
>  method 支持通过promise Callback，可通过 Callback方式implement 下一步动作（方式2）。

#### start play 
```
  // 方式1
  player.play();
  // 方式2
  player.play()
  .then(()=>{
    console.log("implement play  success后 other 动作");
  });
```
#### stopplay 

```
  // 方式1
  player.stop();
  // 方式2
  player.stop()
  .then(()=>{
    console.log("implement stop success后 other 动作");
  });
```
#### Turn on 声音

```
  // 方式1
  player.openSound();
  // 方式2
  player.openSound()
  .then(()=>{
    console.log("implement Turn on 声音 success后 other 动作");
  });
```
#### start 录制
> 因录制解码库Load 限制，录制库Load 需要3S秒左右，请保证录制时长需要大于5秒。
> 录制 file需要使用play 器，play 器下载address <a href="https://service.ys7.com/downloadInfoSite/admin">play 器下载</a>
```
  // 方式1
  player.startSave("唯一 file名");
  // 方式2
  player.startSave("唯一 file名")
  .then(()=>{
    console.log("implement start 录制 success后 other 动作");
  });
```
#### stop录制并下载 file

```
  // 方式1
  player.stopSave();
  // 方式2
  player.stopSave()
  .then(()=>{
    console.log("implement stop录制 success后 other 动作");
  });
```
#### screenshot

```
  // 方式1 - 下载到本地
  player.capturePicture(" file名");
  // 方式2 - returnbase64格式
  const capCallback = (data) => {
    console.log("data",data)
  }
  player.capturePicture('default',capCallback)
```
#### Start intercom

```
  player.startTalk();
```

#### End the intercom

```
  player.stopTalk();
```

#### fullscreen

```
  player.fullScreen();
```
#### Cancel fullscreen

```
  player.cancelFullScreen();
```
#### get OSD时间

```
   player.getOSDTime()
  .then((time)=>{
    console.log("get 到的当forwardplay 时间", time);
  });
```

####  switchaddressplay 

> 可用于在play 中 switchDevice ， switchplay parameter ，以及直播 switch回放等。请注意，频繁 switch可能导致abnormal， switch间隔至少需要1秒

```
  player.changePlayUrl(options)
  .then(()=>{
    console.log(" switch success")
  });
```
optionsparameter 说明

|parameter 名|类型|是否必选|默认值|描述|
|:--|:--|:--|:--|:--|
|type|	String|	Y|无|play address类型，"live":预览，"rec":回放；“cloud.rec”:云存储回放|
|deviceSerial | String | Y |无|Device 序列号,存在英文字母的Device 序列号，字母需为大写|
|channelNo    | int    | Y | 无 | 通道号|
|accessToken|	String|	N | initialization时get  | 授权过程get 的access_token|
|hd    | boolean    |  N |initialization时get |是否为高清 true-主码流（高清） false-子码流(标清)   |
|validCode	|String	|N| initialization时get  |	Device verification 码（加密Device play 需要输入verification 码）|
|validCode	|String	|N| initialization时get  |	Device verification 码（加密Device play 需要输入verification 码）|
|begin|	String	|N|initialization时get |type类型为回放有效，start 时间 格式为“YYYYMMDDHHmmss”	|
|end|	String	| N| initialization时get |type类型为回放有效，结束时间 格式为 “YYYYMMDDHHmmss”	|


  

####  switch模板主题  
> 可用于在play 中 switch模板主题，请 switchplay address success后Transfer

```
  player.Theme.changeTheme(template)

  // 预览切回放场景示例
  player.changePlayUrl({type:"rec"});
  .then(()=>{
    console.log("address switch success，start  switch模板主题");
    player.Theme.changeTheme("pcRec");
  });
  

```
templateparameter 说明

|parameter 名|类型|描述|是否必选|
|:--|:--|:--|:--|
|type|	String| 模板名称，详见initializationparameter template|	Y|


#### Turn on electronic zoom
>建议使用模板，模板中的电子放大功能更全

```
  // 方式1
  player.enableZoom();
  // 方式2
  player.enableZoom()
  .then(()=>{
    console.log("Turn on electronic zoom success");
  });
```
####  Close 电子放大

```
  // 方式1
  player.closeZoom();
  // 方式2
  player.closeZoom()
  .then(()=>{
    console.log(" Close 电子放大 success");
  });
```

#### 重置画面宽高

```
  player.reSize(width, height);
```

### 使用示例

> 如果使用原生js，可参考demos => base-demo

> 如果使用react，可参考demos => react-demo

> 如果使用vue，可参考demos => vue-demo
