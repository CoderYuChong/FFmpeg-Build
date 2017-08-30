# FFmpeg


```
build-x264.sh 来自于 https://github.com/kewlbear/x264-ios
FFmpeg-iOS-build-script  https://github.com/kewlbear/FFmpeg-iOS-build-script
gas-preprocessor.pl https://github.com/libav/gas-preprocessor
x264 http://www.videolan.org/developers/x264.html
```

##### Mac安装 FFmpeg

```
brew install ffmpeg
```
##### FFmpeg 使用
```
转化格式: ffmpeg -i [fileName] [fileName]
分离视频: ffmpeg -i [fileName] -vcodec copy -an [fileName]
分离音频: ffmpeg -i [fileName] -acodec copy -vn [fileName]
剪切视频：ffmpeg -ss 0:1:30 -t 0:0:20 -i [fileName] -vcodec copy -acodec copy [fileName] //-r 提取图像的频率，-ss 开始时间，-t 持续时间
```
##### 编译FFmpeg(iOS)
* `git clone https://github.com/CoderYuChong/FFmpeg-Build.git`
* 复制`gas-preprocessor.pl`到`/usr/local/bin`下
* 修改文件权限：`chmod 777 /usr/local/bin/gas-preprocessor.pl`
* 进入`FFmpeg-iOS-build-script`文件 
* 执行脚本文件：`./build-ffmpeg.sh`

##### 编译X264 
* 进入 `FFmpeg-Build` 文件下
* 修改权限 `sudo chmod u+x build-x264.s`
* 执行脚本 `sudo ./build-x264.sh`

#####     iOS项目中集成FFmpeg

* 将编译好的文件夹拖入到工程中
* 添加依赖库: 
 
    ```
    libiconv.tbd
    libz.tbd
    libbz2.tbd
    CoreMedia.framework
    AVFoundation.framework
    ```



