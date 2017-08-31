
##### 文件

* `build-x264.sh` 来自于 https://github.com/kewlbear/x264-ios
* `FFmpeg-iOS-build-script` 来自于 https://github.com/kewlbear/FFmpeg-iOS-build-script
* `gas-preprocessor.pl` 来自于 https://github.com/libav/gas-preprocessor
* `x264` 来自于 http://www.videolan.org/developers/x264.html
* `Build-iOS` 自己编译好的文件(FFmpeg-iOS文件过大，没有上传)

##### Mac安装 FFmpeg

```
brew install ffmpeg
```
##### FFmpeg 简单使用
```
转化格式: ffmpeg -i [fileName] [fileName]
分离视频: ffmpeg -i [fileName] -vcodec copy -an [fileName]
分离音频: ffmpeg -i [fileName] -acodec copy -vn [fileName]
剪切视频：ffmpeg -ss 0:1:30 -t 0:0:20 -i [fileName] -vcodec copy -acodec copy [fileName] //-r 提取图像的频率，-ss 开始时间，-t 持续时间
更多命令  https://github.com/tonydeng/fmj/blob/master/ffmpeg.md
```
##### 编译FFmpeg(iOS)
* `git clone https://github.com/CoderYuChong/FFmpeg-Build.git`
* 复制`gas-preprocessor.pl`到`/usr/local/bin`下
* 修改文件权限：`chmod 777 /usr/local/bin/gas-preprocessor.pl`
* 进入`FFmpeg-iOS-build-script`文件 
* 执行脚本文件：`./build-ffmpeg.sh`

##### 编译X264 
* 进入 `FFmpeg-Build` 文件下
* 修改权限 `sudo chmod u+x build-x264.sh`
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


##### 安装出现的错误


```
Found no assembler
Minimum version is nasm-2.13
If you really want to compile without asm, configure with --disable-asm.
```
##### 解决办法
`brew install nasm`


