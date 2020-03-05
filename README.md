# 转码测试程序说明
## 一 支持平台说明
该程序支持多种Linux环境，目前Ubuntu 16.04 和CentOS 7.4已验证。
没有插TPU卡的机器，使用软件转码。如需要使用硬件转码，请购买比特大陆TPU算力加速卡。

## 二 编译步骤
- 在程序包中执行./compile.sh, 编译成功后，会编译出一个可执行程序fftrans。
## 三 程序参数说明
- --bps:设置转码输出比特率，单位bps，默认32K
- --dev_num: 当前测试机器中的设备节点数，即/dev/bm-sophon+设备号（0～最大数-1）的个数。
- --devid_start: 要使用的设备起始号码，默认3
- --fps：设置输出的帧率，默认25
- --height：设置转码输出图像高度，默认288
- --width：设置转码输入图像宽度，默认 352
- --num：设置总的转码路数，默认1
- --inputfile：设置输入的测试文件，目前支持264裸流,mp4等文件。
- --max_frame：当前转码多少帧，超过之后程序会结束。

## 四 运行示例
- 运行144路转码 ./fftrans --inputfile=../wkc.264 --devid_start=0 --dev_num=9 --num=144
- 实现N路转码 ./fftrans --inputfile=test.264 --num=N 

