# APICloudModule

免费的APICloud  自定义模块集群

- [ ] moduleAppInfo
- [ ] moduleCustomWebView
- [ ] moduleRhymingVoice
- [ ] moduleScanner
- [ ] moduleVibration
- [ ] modulechoosepicture
- [ ] moduleWXMiniProgramPay



## moduleAppInfo

获取Android手机应用列表

```javascript
var moduleAppInfo;

function apiready() {
  moduleAppInfo = api.require('moduleAppInfo');
}

function startRecord() {
  moduleAppInfo.appinfo({},function(ret,err){
    //ret返回AppInifo列表
  });
}
```



## moduleCustomWebView

自定义应用内打开网页

```javascript
var moduleCustomWebView;

function apiready() {
  moduleCustomWebView = api.require('moduleCustomWebView');
}

function startRecord() {
  moduleCustomWebView.openWebView({
    url:'http://www.baidu.com',//打开Web页url
		isShowNavigation:false,　//是否显示标题栏
		isShowBackItem:true,　//　是否显示返回按钮
		title:'标题',　//　栏标题文字
  },function(ret,err){
    
  });
}
```



## moduleRhymingVoice

监听手机音乐音量频率

```javascript
var moduleRhymingVoice;

function apiready() {
  moduleRhymingVoice = api.require('moduleRhymingVoice');
}

function startRecord() {
  moduleRhymingVoice.startRecord({},function(ret,err){
    
  });
}
```



## moduleScanner

自定义扫一扫二维码、条形码

```javascript
var moduleScanner;

function apiready() {
  moduleScanner = api.require('moduleScanner');
}

function scanHandle() {
  moduleScanner.scanHandle({
    isLight:true,//是否打开闪光灯
    cancelText:"Cancel",//设置取消按钮文字
    cancelColor:"000000",//设置取消按钮颜色
    scanPrompt:"请将二维码放入扫描框内"
  },function(ret,err){
    
  });
}
```





## moduleVibration

手机振动

``` javascript
var moduleVibration;

function apiready() {
  moduleVibration = api.require('moduleVibration');
}

function vibrationHandle() {
  moduleVibration.vibrationHandle({
    time:3000 //振动3s,time参数只对android有效
  },function(ret,err){
    
  });
}
```



## modulechoosepicture

手机相册多图、视频选择

```javascript
var moduleGetPicture;

function choosePicture(){
    moduleGetPicture.getPictureHandle({
        maximages:"6", //最多只能选6张图片
        targetWidth:"800",//限制图片的宽度
        targetHeight:"1024",//限制图片的高度
    },function(ret,err){
    	//反回结束 {code:"1",images:[“imageURL1","imageURL2"]}
    });
}

function apiready() {
    moduleGetPicture = api.require('GetPicture');
}
```



## moduleWXMiniProgramPay

微信小程序支付

```javascript

var huijuPayModule；
function apiready() {
    huijuPayModule= api.require('huijuPayModule');
}

//微信小程序支付
function pay(){
			huijuPayModule.toSmall({
						   userName:'gh_*****',
						   payee_name:'商品名称',
						   original_id:'gh_268a4c909296',
                           product_name:'网上购物-*****',//商品名称
                           order_amout:'0.01',
                           app_id:'52642300', //APPID
                           trx_no:'6436354011324773',
                           order_no:'345456341315282'
			},function(ret,err){
				var msg = "点击了第个按钮";
				api.toast({
					msg:msg
				});
			});
		}

//内置微信分享
huijuPayModule.openWebView({
						   url:'http://www.baidu.com',
						   isShowNavigation:false,
						   isShowBackItem:true,
						   title:'helloworld',
			},function(ret,err){

			});
```





------

如果您需要自定义APICloud模块，请咨询QQ:1274336210  或微信:DeqiuTseng

其它问题欢迎加入我的QQ技术交流群:474691105













