# minirtu
## 功能：
### （1）采集一台485/422接口的MODBUS传感器的数据
### （2）向[奇迹万物平台](https://www.thingscloud.xyz)上传数据并展示曲线等
### （3）电池供电，能向传感器输出8~24V电压--人工旋转电位器调节电压
### （4）内置4G模组，需要插入一张SIM卡，在信号不好的时注意调节天线的位置、方向

## 代码：
### （1）选择合适的传感器，代码中含有两款温湿度传感器的实例：TH11S_B和CWS21，并且PLATFORM_DEF支持平台向minirtu下发任意的MODBUS指令。如果要自定义传感器，需要参考\APP\uartSensor\uartSensor.c中void RS485_Sensor_Transmit(void)函数的一些实例，构造向传感器下发的指令，并在void app_ProcessSensorTask(void *p_arg) 函数中，参考实例，解析传感器返回的报文并构造JSON上传给服务器
###  (2)设置休眠时间，minirtu每工作60秒，会休眠一段时间，以此来实现间歇采集、延长待机时间。休眠的时间长度由SLEEP_TIME_SECONDS_DEFALT决定，单位是秒

## 编译：
### keil5.25.0
