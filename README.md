# netShell
Gb以上规模的高速网络接口
脚本支持Gb以上规模的高速网络接口
脚本主要是基于sysfs的虚拟文件系统，这是由内核用来将设备或驱动相关的信息输出到用户空间的一种机制。网络接口的相关分析数据会通过“/ SYS /班/网//统计“输出
eg:
eth0的网口上分析报告会输出到这些文件中：
    /sys/class/net/eth0/statistics/rx_packets: 收到的数据包数据

    /sys/class/net/eth0/statistics/tx_packets: 传输的数据包数量

    /sys/class/net/eth0/statistics/rx_bytes: 接收的字节数

    /sys/class/net/eth0/statistics/tx_bytes: 传输的字节数

    /sys/class/net/eth0/statistics/rx_dropped: 当收到包数据包下降的数据量

    /sys/class/net/eth0/statistics/tx_dropped: 传输包数据包下降的数据量
    这些数据会根据内核数据发生变更的时候自动刷新。因此，你可以编写一系列的脚本进行分析并计算流量统计。下面就是这样的脚本（感谢 joemiller 提供）。第一个脚本是统计每秒数据量，包含接收（RX）或发送（TX）。而后面的则是一个描述网络传输中的接收（RX）发送(TX)带宽。这些脚本中安装不需要任何的工具。

