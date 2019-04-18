# SuperMap iMobile Support
1. SuperMap iMobile for Android 许可支持包
      本支持包基于SuperMap iMobile for Android产品开发，支持的版本包括官网上的800,801,811，以及9D系列，而不支持未提到的早期
   版本 。由于iMobile的原因，一些版本可能会提示打开Wifi。对此，本支持包无法避免。
   本支持包主要解决原产品包中使用正式许可时获取设备ID和许可在线激活的问题，具体介绍如下：
      1. LicenseEnvironment提供setLicensePath(), initialization(), getDeviceID()三个方法用于替换
         com.supermap.data.Enviroment类中对应名称的方法。
         LicenseUtil用于替换原有产品包的在线激活功能。
      2. 增加正式许可的加密存储，因此只有提供正确的用户许可序列号才能使用正式许可。
      3. 初始化时，增加自动在线激活功能，避免用户再写激活代码。
      4. 解决原有产品中校验设备信息经常出错的问题。
      5. 解决9D部分版本激活后重启初始化后许可仍然无效，以及重复激活的问题。
      6. 兼容正在使用的正式许可，对于8C的许可和9D的离线许可文件，为保证正常使用Android 6.0及以上系统版本仍然需要开启Wifi连接
         网络，以正确获取设备信息。
      7. 需要申请离线正式许可，请通过LicenseEnvironment.getDeviceID()获取设备ID，该方法不要求开启wifi和联网，通过
         LicenseUtil提供的方法在线激活8C产品也可以不使用Wifi联网，而使用移动网络就可以实现。
