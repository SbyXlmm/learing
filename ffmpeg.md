# ffmpeg在windows环境安装
* [下载地址](https://ffmpeg.zeranoe.com/builds/)
* 环境变量配置Path ffmpeg/bin
# 常见命令
### 视频截取
`ffmpeg -i in.mp4 -ss 00:00:10 -t 00:00:06 -acodec aac -vcodec h264 -strict -2 out.mp4`   
//从00:00:10开始，截取的长度为00:00:06
* 参数解释：  
-i  代表输入待处理的文件  
-ss 代表开始的时间   
-t 代表截取的长度  
-acodec 音频编解码器  
-vcodec 音频编解码器 
### 视频转gif
`ffmpeg -i v.mp4 -s 76x76 -f gif -r 1 g.gif`
* 参数解释：  
-i  代表输入待处理的文件  
-s 代表图像放缩参数  
-r 代表帧率  
### gif转视频
`ffmpeg -i g.gif out1.mp4`
* 参数解释：  
-i  代表输入待处理的文件  
### 视频压缩，降低分辨率
`ffmpeg -i v1.mp4 -vf scale=360:640 -acodec aac -vcodec h264 out.mp4`  
-i 代表输入，  
-vf 的全称是video filter，即：视频滤镜，缩放其实就是给视频添加一个滤镜。  
scale=360:640 scale是一种滤镜，缩放滤镜，格式是：scale=width:height，其中，width和height分别是处理后的宽和高
### 视频旋转
`ffmpeg -i v1.mp4 -vf rotate=PI/2:ow=1080:oh=1920 out.mp4`
* 参数解释：  
rotate=PI/2  rotate是旋转滤镜，后面的“PI/2”旋转角度（正数代表顺时针），这里是90度    
rotate除了指定旋转角度的参数外，还有其他一些参数：  
ow 全称是out width，输出视频的宽度，如果不指定，默认是输入视频的宽度  
oh 全称是out height，输出视频的高度，如果不指定，默认是输入视频的高度
### 查看视频的详细信息
`ffmpeg -i v1.mp4 ` 
