- [X] Windows环境下需要网卡名（例如'WLAN'）及其ID（例如'{4D36E972-E325-11CE-BFC1-08002BE10318}'） (2020-12-04 18:45)
  - [X] snipper.py中snipper部分需要网卡名，而filter需要的指定网卡的IP需要根据ID查询 (2020-12-04 18:47)
  - [X] 所以snitter.py正好和list_nic.py相反：它是需要根据网卡名获取其ID (2020-12-04 18:49)
    - [X] 参考：https://blog.csdn.net/Singvis/article/details/101639742#222__Windows_146 (2020-12-04 18:50)
  - [X] list_ic.py在Windows下运行得到的NIC列是ID形式 (2020-12-04 18:45)
  - [X] 需要修改list_nic.py根据ID查询注册表获取其名字以替换NIC列内容 (2020-12-04 18:46)
