# oudun
  + HAL_CANRx485out
    Implement CAN interrupt-driven reception for magnetic encoder rotation speed and position data, alongside XYZ-axis gyroscope data acquisition. Process the collected data, then output via UART printing and transmit over the RS-485 interface. Firmware deployment is performed using an ST-Link debugger.
    对磁编码器的旋转速度和位置数据以及 XYZ 轴陀螺仪数据采用 CAN 中断驱动接收方式。对采集到的数据进行处理，然后通过 UART 输出并通过 RS-485 接口进行传输。使用 ST-Link 调试器进行固件部署
    
  + HAL_CANRx485out1.1
    HAL_CANRx485out1.1 has one additional button compared to HAL_CANRx485out; the encoder data is transmitted via 485 only when the button is pressed.
    HAL_CANRx485out1.1比HAL_CANRx485out 多一个按键，如果按键按下485才会发送编码器数据
    
  + HAL_CANRx485out1.2
    Compared to HAL_CANRx485out1.1, HAL_CANRx485out1.2 transmits an additional 485 data frame containing the button count and two joystick axes. The button status is encoded using a bitmask scheme supporting up to 8 inputs, with a maximum value of 0xFF(Binary).
    HAL_CANRx485out1.2 比 HAL_CANRx485out1.1多发送一组485数据，内容是按键个数和遥感2个方向，按键是二进制算法最多获取8个按键值，最大表示0xFF
    
  + HAL_CANRx485out1.3
    Compared with HAL_CANRx485out1.2, HAL_CANRx485out1.3 has 2 additional ADCs in the RS-485 transmission. Its configuration includes: 4 ADC reading modules, 8 IO port readings (maximum value 0xFF), RS-485 data transmission, and USART serial port printing.
    与 HAL_CANRx485out1.2 相比，HAL_CANRx485out1.3 在 RS-485 传输部分多增加了 2 个 ADC。其配置包括：4 个 ADC 读取模块、8 个 I/O 端口读取（最大值为 0xFF）、RS-485 数据传输以及 USART 串行端口打印。
    
  + PWMControlServo
    Output frequency: 50Hz-20ms，When PA1 is detected to be high level, PB1 outputs a pulse width of 500，When PA1 is detected to be low level, PB1 outputs a pulse width of 1500，On power-on, PA1 defaults to high level
    输出频率：50Hz-20ms，当检测到PA1 为高电平时候 PB1输出脉宽是 500 ，当检测到PA1 为地电平时候 PB1输出脉宽是 1500 ，开机默认PA1 为高电平

+ 2-RemoteSensing485out
  Obtain 2 sets of ADC data from the remote sensing, use the serial port print assistant to observe the ADC data. Send 485 arrays in 4 directions respectively, and send 485 arrays during the return process.(Another remote sensing reservation)
  After the button is pressed, a 485 array is sent every 1000 milliseconds. Press it again to stop the transmission.
  从遥感设备获取两组 ADC 数据，使用串口打印助手来查看 ADC 数据。分别在四个方向发送 485 数组，并在返回过程中也发送 485 数组。(另一个遥感预留)
  按下按钮后，每 1000 毫秒发送一个 485 数组。再次按下按钮可停止传输。
  
+ 3-RemoteSensing485out
  Acquire telemetry data and transmit it via RS-485 (using USART1 on PA8, PA9, and PA10) at a 10 ms interval. The OLED display should show the telemetry data in both decimal and hexadecimal formats.
Hardware Pinout & Control:
 * Telemetry Input: ADC1 (PA0, PA1)
 * OLED Mirror: PA7
 * OLED Refresh Rate Control: PB12
  检测遥感数据，并用485每次10ms发送一次数据，在OLED显示遥感十进制数据和16进制数据
  PA7 是反转OLED显示的 ;
  PB12是控制OLED刷新速度的 ;
  485发送用的USART1  PA8、PA9、PA10 ;
  遥感接收用的ADC1   PA0 、PA1 

+ 3-FreeRTOS_Mutex
  "Implement the 3-RemoteSensing485out project utilizing the FreeRTOS Mutex mechanism for resource protection."
  (实现 3-RemoteSensing485out 工程，利用 FreeRTOS 互斥锁机制进行资源保护。)
  
