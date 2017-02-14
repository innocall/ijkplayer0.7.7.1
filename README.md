# ijkplayer0.7.7.1

 ijkplayer是Bilibili根据ffmpeg编译的播放器，支持硬解码、软解码、修改视频尺寸，支持视频格式多，但存在部分bug。下面我将记录在虚拟机上Ubuntu编译ijkplayer。
 
## 环境准备

1、下载配置jre环境变量
    
    sudo apt-get install default-jre
    
2、下载配置android_sdk、android_ndk环境变量
 
  下载地址：http://www.androiddevtools.cn/
  在ubuntu环境下，进入home/xxx/ 
  xxx代表你的名字，进入目录后按Ctrl+H就可以看到隐藏的文件，你就可以看到： .bashrc 
  打开后在最下面添加：
```
    #android sdk ndk path
    ANDROID_NDK=/home/wuxiaotie/Documents/java_path/android-ndk-r13b
    export ANDROID_NDK
    ANDROID_SDK=/home/wuxiaotie/Documents/java_path/android-sdk-linux
    export ANDROID_SDK
    export PATH=$PATH:$ANDROID_NDK:$ANDROID_SDK
```

注意：sdk和ndk的环境key必须用ANDROID_SDK和ANDROID_NDK。

3、编译

```
   git clone https://github.com/Bilibili/ijkplayer.git ijkplayer-android
   cd ijkplayer-android
   git checkout -B latest k0.7.7.1
   
   ./init-android.sh
   
   cd android/contrib
   ./compile-ffmpeg.sh clean
   ./compile-ffmpeg.sh all
   
   cd ..
   ./compile-ijk.sh all
```
注意：编译过程中需要下载ffmpge需要翻墙编译。

4、用android studio导入android/ijkplayer/ 运行即可。
