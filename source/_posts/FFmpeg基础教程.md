---
uuid: f5075fd0-de72-11e9-af16-252bd33a19aa
title: FFmpeg 基础教程
date: 2019-09-24 10:28:12
updated:
categories:
	- FFmpeg
tags:
	- FFmpeg
---
---
> FFmpeg 基础教程
 
<!-- more -->
### FFmpeg 基本信息查询命令
{% codeblock 显示版本 %}
FFmpeg -version
{% endcodeblock %}

{% codeblock 显示可用的 demuxers %}
FFmpeg -demuxers
{% endcodeblock %}

{% codeblock 显示可用的 muxers %}
FFmpeg -muxers
{% endcodeblock %}

{% codeblock 显示可用的设备 %}
FFmpeg -devices
{% endcodeblock %}

{% codeblock 显示所有编解码器 %}
FFmpeg -codecs
{% endcodeblock %}

{% codeblock 显示可用的解码器 %}
FFmpeg -decoders
{% endcodeblock %}

{% codeblock 显示所有的编码器 %}
FFmpeg -encoders
{% endcodeblock %}

{% codeblock 显示比特流 filter %}
FFmpeg -bsfs
{% endcodeblock %}

{% codeblock 显示可用的格式 %}
FFmpeg -formats
{% endcodeblock %}

{% codeblock 显示可用的协议 %}
FFmpeg -protocols
{% endcodeblock %}

{% codeblock 显示可用的过滤器 %}
FFmpeg -filters
{% endcodeblock %}

{% codeblock 显示可用的像素格式 %}
FFmpeg -pix_fmts
{% endcodeblock %}

{% codeblock 显示可用的采样格式 %}
FFmpeg -sample_fmts
{% endcodeblock %}

{% codeblock 显示 channel 名称%}
FFmpeg -layouts
{% endcodeblock %}

{% codeblock 显示识别的颜色名称%}
FFmpeg -colors
{% endcodeblock %}

### FFmpeg 录屏命令
```
# 录视频
ffmpeg -f avfoundation -i 1 -r 30 out.yuv

# 录声音
ffmpeg -f avfoundation -i :1 out.wav

-f: 指定使用 avfoundation 采集数据
-i: 指定从哪儿采集数据，它是一个文件索引号
-r: 指定帧率
```
```
# 播放
ffplay -s 3360x2100 -pix_fmt uyvy422 out.yuv
```
```
# 查询支持的设备
ffmpeg -f avfoundation -list_devices true -i ""
```
### 多媒体格式转换
```
ffmpeg -i out.mp4 -vcodec copy -acodec copy out.flv
# 单独抽出视频流
ffmpeg -i out.mp4 -an -vcodec copy out.h264
```

### 提取 YUV 原始视频数据
```
ffmpeg -i MV.mp4  -an -c:v rawvideo -pix_fmt yuv420p out.yuv
```

### 提取 PCM 原始音频数据
```
ffmpeg -i MV.mp4 -vn -ar 44100 -ac 2 -f s16le out.pcm

# 播放提取的数据
ffplay -ar 44100 -ac 2 -f s16le out.pcm
```

### 滤镜命令
```
# 宽和高减少200
ffmpeg -i MV.mp4  -vf crop=in_w-200:in_h-200 -c:v libx264 -c:a copy out.mp4
```

### 音视频裁剪
```
ffmpeg -i MV.mp4 -ss 00:00:00 -t 10 out.ts
```

### 音视频合并
```
ffmpeg -f concat -i input.txt out.mp4

input.txt 文件内容为:
file 'out1.mp4'
file 'out2.mp4'
```

### 视频转图片
```
ffmpeg -i out2.mp4 -r 1 -f image2 images-%3d.jpeg
```

### 图片转视频
```
ffmpeg -i image-%3d.jpeg out.mp4
```

### 直播推/拉流
```
ffmpeg -re -i out.mp4 -c copy -f flv rtmp://server/live/streamName

ffmpeg -i rtmp://server/live/streamName -c copy dump.flv
```

***
<!-- 内容 -->
***
{% note info %} 
 #### 相关链接：
 [FFmpeg音视频核心技术精讲与实战](https://www.bilibili.com/video/av67371679/?p=7)
{% endnote %}
{% note warning %} 
 转载请注明出处 
 文章有问题请指出
{% endnote %}