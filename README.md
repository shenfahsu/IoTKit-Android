# JFG Android SDK Document

  此帮助文档主要介绍加菲狗Android SDK的大致逻辑。

#[接入流程](doc/API/SDK.md)必看,非常重要！！！

###[API目录](doc/API/SUMMARY.md)
---

###更新说明


#### 3.0.140
  1. 修复NTP时间问题。
  2. KV存储问题。
  
#### 3.0.139
  1. 优化底层代码。 
  
#### 3.0.138
  1. 兼容2.x版本的获取图片的URL
  2. 优化jni 代码。
  3. 修复一些已知bug。

####3.0.137
  1. 重命名获取云存储URL的API，getCloudUrlByType(int type ,int flag ,String fileName,String belong);
   第一个参数，查看JfgEnum.JFG_URL类中的定义。第二个flag，代表着服务器存储的位置（国内外）,由服务器下发。第三个fileName是具体的文件名，必须带后缀。
   第四个belong 为该资源归属哪个设备，如果有就填上设备ID，如果不归属设备，则填空字符串即可。
  2. 修复136版本中存在的bug。 

#### 3.0.136
  1. 更新用户头像。 (流程：使用updateAccountPortrait 接口更新头像成功后，
  调用JFGAccount类中的setPhoto方法，然后发送setAccount.最后服务器会更新JFGAccount中的photoUrl)
  2. 更改设备别名。 (流程：使用setAliasByCid设置设备名后，在OnReportJfgDevices查看具体的设备别名。)
  3. DP空值也会返回到上层。


#### 3.0.134 
  1. 消息透传添加消息来源，caller。
  2. JFGMsgHttpResult 的结果改为byte[]类型。

#### 3.0.133
  1. JFGAccount 类添加一个 resetFlag() 方法。用来清空内部的一个标志。需要在setAccount之后调用。
  2. 因为修改手机号必须要有token ，所以将两个参数合并。 setPhone(String phone,String token);

#### 3.0.132
  1. 添加一个MessagePack的工具类 ‘JfgMessagePackUtils’。 
   
#### 3.0.131
  1. 将DatePoint 中 id 的数据类型为 long 类型。

#### 3.0.130
  1. 修复setAccount中因为空值导致的崩溃。

#### 3.0.118
  1. 为了便于以后扩展，修改onResult回调接口，参数改为JFGResult 类。
  2. 忘记密码，重置密码，修改密码接口。
  3. 分享设备，分享列表。---分享类接口。
  
