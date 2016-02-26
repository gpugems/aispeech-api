使用Titanium开发基于aispeechapi的ios应用

# 开发环境 #
Mac OS + Titanium

# 创建一个新的IOS应用 #
打开Titanium Developer，点击 **_New Project_** ， **_Project type_** 选择 _Mobile_ 或者 _iPad_ ，填入其他信息后点击 **_Create Project_** 按钮。
然后程序会自动在项目文件夹下生成一些文件和文件夹。打开其中的Resources 文件夹，将 aispeechapi for ios 拷贝到该文件夹中即可。

# 简单例子：音频播放 #
app.js 是整个应用程序的入口文件。在这个例子中，我们开发一个简单的播放器，具有加载音频、播放和停止功能。
  1. 创建一个窗口
```
var win = Ti.UI.createWindow();
```
  1. 导入aispeechapi for ios
```
Ti.include("../aispeech/aispeech.js");
```
  1. 创建播放器
```
var player = new aispeech.AiSound({
    onError: function(message, source, type){
        Ti.API.log("onError: " + message + ", " + source + "," + type);
    },
    onInterrupted: function(source, type){
        Ti.API.log("onInterrupted: " + source + "," + type);
    },
    onResume: function(source, type){
        Ti.API.log("onResume: " + source + "," + type);
    }
});
```
  1. 创建用户界面：包含一个输入框、一个load按钮、一个play按钮和一个stop按钮。
```
//以下是输入框的代码
var audioUrlTextField = Titanium.UI.createTextField({
    color: '#336699',
    value: "",
    height: 35,
    top: 10,
    left: 20,
    width: 220,
    autocapitalization: Titanium.UI.TEXT_AUTOCAPITALIZATION_NONE,
    keyboardType: Titanium.UI.KEYBOARD_DEFAULT,
    returnKeyType: Titanium.UI.RETURNKEY_DEFAULT,
    borderStyle: Titanium.UI.INPUT_BORDERSTYLE_ROUNDED

});
win.add(audioUrlTextField);

//以下是3个按钮的代码
var loadButton = Titanium.UI.createButton({
    title: "load",
    width: 50,
    height: 35,
    left: 250,
    top: 10
});
win.add(loadButton);

var bb1 = Titanium.UI.createButtonBar({
    labels: ["play", "stop"],
    backgroundColor: '#336699',
    top: 50,
    style: Titanium.UI.iPhone.SystemButtonStyle.BAR,
    height: 25,
    width: 260
});
win.add(bb1);
```
  1. 绑定按钮事件
```
var hasLoadedAudio = false;
loadButton.addEventListener("click", function(){//load
    player.load({
        url: audioUrlTextField.value,
        success: function(){
            Ti.API.log("audio load success.");
            hasLoadedAudio = true;
        }
    });
});

bb1.addEventListener("click", function(e){
    if (hasLoadedAudio == false) {
        return;
    }
    if (e.index == 0) { //play
        player.play({
            //position: 0,
            //duration: 3000,
            onStart: function(){
                Ti.API.log("player start");
            },
            onStop: function(){
                Ti.API.log("player stop callback");
            }
        });
    } else if (e.index == 1) { //stop
        player.stop({
            onStop: function(){
                Ti.API.log("player stop");
            }
        });
    }
});
```
  1. 最后，在程序运行时打开该窗口
```
win.open();
```
  1. 现在，您就可以运行该播放器程序了。


# 开发者文档 #
Appcelerator Developer Center - Documentation
http://developer.appcelerator.com/documentation

aispeechapi ios - Documentation