# 常用命令行

## IO 监控
`iostat -d -k 2`

参数 -d 表示，显示设备（磁盘）使用状态；-k某些使用block为单位的列强制使用Kilobytes为单位；2表示，数据显示每隔2秒刷新一次。

输出信息的意义
```
tps：该设备每秒的传输次数（Indicate the number of transfers per second that were issued to the device.）。"一次传输"意思是"一次I/O请求"。多个逻辑请求可能会被合并为"一次I/O请求"。"一次传输"请求的大小是未知的。

kB_read/s：每秒从设备（drive expressed）读取的数据量；
kB_wrtn/s：每秒向设备（drive expressed）写入的数据量；
kB_read：读取的总数据量；
kB_wrtn：写入的总数量数据量；这些单位都为Kilobytes。
```

## 多线程下载

### axel

`sudo apt install axel`
`axel -n 10 -a download_link_addr`
用十个线程来开始下载

### aria2

`sudo apt install aria2`
`aria2c -x10 download_link_addr`
用十个线程来开始下载

### 读取文件数及文件夹数

1.统计当前文件夹下文件的个数
`ls -l |grep "^-"|wc -l`

2.统计当前文件夹下目录的个数
`ls -l |grep "^d"|wc -l`

3.统计当前文件夹下文件的个数，包括子文件夹里的
`ls -lR|grep "^-"|wc -l`

4.统计文件夹下目录的个数，包括子文件夹里的
`ls -lR|grep "^d"|wc -l`
