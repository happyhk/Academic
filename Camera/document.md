# 线阵相机开发
Spyder3 SG-34 GigE Vision (GEV)是一款高灵敏度、双线性扫描彩色相机。在高灵敏度(双线性)模式下工作时，Spyder3 GEV相机的响应率是Teledyne DALSA的Spyder2线扫描相机的三倍。此外，GigE Vision界面消除了对帧抓取器的需求，从而大大节省了系统成本。<br>
本次使用的是SG-34-02K80-00-R型号的相机，其中的主要配置描述如下：<br>
| Model Number | Description |
| ------ | ------ | 
| SG-34-02K80-00-R | 2K resolution, 80 MHz data rate, 18KHz line rate |
| Pixel Size | 14um * 14um |
| resolution | 2048 pixels |
| 曝光时间 | 3~3000us |
| 最大线速率 | 18KHz |
| 相机尺寸 | 72mm  x 60 mm x 65 mm |
| 输入电压 | +12V ~ +15v |
<br>
本相机支持的系统为Window XP 或者Windows 7，之后的版本是否支持暂不知晓。<br>

| priority Number | Color of status LED  | Meaning |
| ------ | ------ | ------|
| 1 | Flashing Red | Fatal Error. For example, camera temperature is too high and camera thermal shutdown has occurred |
| 2 | Flashing Green | Camera initialization or executing a long command |
| 3 | Solid Green | Camera is operational and functioning correctly |
<br>
最大帧率(Frame Rate)/行频(Line Rate)：即相机采集传输图像的速率，对于面阵相机一般为每秒采集的帧数(Frames/Sec.)，对于线阵相机为每秒采集的行数(Hz)。<br>
编码器为2000脉冲/转，即编码器每转一圈，在一分频的情况下，线阵相机可以扫2000行。<br>

