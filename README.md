# cordova-plugin-serial-port
基于cordova编写的安卓串口通信插件


# API

#### 打开连接
param: 
- config  配置
- success 成功返回 
- error 失败返回

config:
- dev: 串口
- baudrate: 波特率
- flags:  srdial端口标志
- isHex: 如果要使用hexString，则应将其设置为true.


example:
```
cordova.plugins.SerialPortPlugin.openDevice([{dev:'/dev/ttyS2',baudrate:38400, flags:0, isHex:true}],
    result=>alert(result),
    error=>alert(error));
}
```

#### 关闭连接
example:
```
cordova.plugins.SerialPortPlugin.closeDevice(
    result=>alert(result),
    error=>alert(error)
);

```

#### 读数据
example:
```
cordova.plugins.SerialPortPlugin.read(
  res=> {
        console.log(res);
        alert(res);
  },
  error=> {
      alert(error);
  });
```

#### 写数据
example:
```
cordova.plugins.SerialPortPlugin.write('8A',
  res=> {
        console.log(res);
        alert(res);
  },
  error=> {
      alert(error);
  });
```

#### 写数据然后等返回
响应数据可能不完整，您可以使用(read)api获取其余信息.

param: 
- arg1: data
- arg2: timoutMs

example:
```
cordova.plugins.SerialPortPlugin.sendDataAndWaitResponse('8A',1000,
  res=> {
        console.log(res);
        alert(res);
  },
  error=> {
      alert(error);
  });

```

#### setHex
you can change the hexString | string  after openDevice

example:
```
cordova.plugins.SerialPortPlugin.setHex(true);
```



