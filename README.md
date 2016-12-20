#一步 (One Step)

![](http://static.smartisanos.cn/common/img/third-medium/one-step-icon_8dab923f53.png)

> 锤子科技的一小步，智能手机进化的一大步

----

### 什么是一步（One Step）？
通过拖拽完成将信息发送至应用或联系人的动作，节省了在不同应用之间切换的诸多步骤，第一次打通了手持设备中应用间的边界

[进一步了解 One Step](http://www.smartisan.com/m1/#/os?section=onestep)

----

### 写在前面的话
1. 我们开源 One Step 是希望其他厂商能将这一功能集成在系统中，共同改善安卓用户体验、提升操作效率。 
2. 我们把 One Step 所有接口封装在 android.view.onestep 包下，考虑到第三方应用集成时的复杂度，请在不改变现有接口的前提下进行扩展。同时也欢迎通过 commit 向我们提交反馈。
3. 由于人力有限，我们仅在 Nexus6（Code Base：Android 6.0.1_MOB31K）的真机上进行了相关测试，理论上其他的机型也可以进行编译运行，但不排除会有bug 出现。最后，我们为你提供了 Nexus6 的 [build](https://github.com/SmartisanTech/SmartisanOS_Build_Release)。

----

### One Step涉及的工程列表：
* frameworks_base (需要更改WindowManager) <https://github.com/SmartisanTech/android_frameworks_base>
* frameworks_native (需要更改input, 响应调整window后touch事件)<https://github.com/SmartisanTech/android_frameworks_native>
* packages_apps_OneStep(OneStep UI层) <https://github.com/SmartisanTech/packages_apps_OneStep>
* build（加入smartisanos框架编译以及OneStep应用） <https://github.com/SmartisanTech/android_build>
* external_sepolicy (为新引入的OneStepService设置权限)<https://github.com/SmartisanTech/android_external_sepolicy>
* frameworks_smatisanos_base (smartisanos 框架层) <https://github.com/SmartisanTech/android_frameworks_smartisanos-base>
* SmartisanSDK (为第三方应用接入提供接口，以及一个简单的demo)<https://github.com/SmartisanTech/SmartisanOS-SDK>

----

### Getting Started
下载之前你需要熟悉：

* [Build Environment](http://source.android.com/source/initializing.html)
* [Git and Repo](http://source.android.com/source/using-repo.html)
* [Preparing to Build](http://source.android.com/source/building.html)

初始化仓库：

```sh
    $ repo init -u https://github.com/SmartisanTech/android.git -b smartisan-m-onestep_bigboom -m manifest.xml
```
> `Tips`: 中国的开发者可以使用清华的镜像，[使用帮助](https://mirrors.tuna.tsinghua.edu.cn/help/AOSP/)

开始同步代码：

```sh
    $ repo sync -cdj4
```

同步完成后进行编译：

> `Tips`: 如果你打算用Nexus6的真机体验的话，别忘了在编译前去下载对应的驱动。代码的基线是 Nexus 6 (Mobile) for Android 6.0.1 (MOB31K) 下载地址：<https://developers.google.com/android/drivers>

```sh
     $ . build/envsetup.sh
     $ lunch aosp_shamu-userdebug
     $ make -j4;
```
> `Tips`:我们提供了Nexus6的build [传送门](https://github.com/SmartisanTech/SmartisanOS_Build_Release)

编译完成后Nexsu6真机的刷机， 请参考 <http://source.android.com/source/running.html#flashing-a-device>
或者使用模拟器，可能配置不对，会有黑屏的问题
```sh
     $ emulator
```
