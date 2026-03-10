# oudun
  HAL_CANRx485out
    Implement CAN interrupt-driven reception for magnetic encoder rotation speed and position data, alongside XYZ-axis gyroscope data acquisition. Process the collected data, then output via UART printing and transmit over the RS-485 interface. Firmware deployment is performed using an ST-Link debugger.
    对磁编码器的旋转速度和位置数据以及 XYZ 轴陀螺仪数据采用 CAN 中断驱动接收方式。对采集到的数据进行处理，然后通过 UART 输出并通过 RS-485 接口进行传输。使用 ST-Link 调试器进行固件部署
  HAL_CANRx485out1.1
    HAL_CANRx485out1.1 has one additional button compared to HAL_CANRx485out; the encoder data is transmitted via 485 only when the button is pressed.
    HAL_CANRx485out1.1比HAL_CANRx485out 多一个按键，如果按键按下485才会发送编码器数据
    
