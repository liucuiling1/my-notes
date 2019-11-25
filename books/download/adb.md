#### adb使用

链接：https://www.jianshu.com/p/229dbd25b661

1.检查安装:
> adb

2.未安装指令:
> brew cask install android-platform-tools

3.环境变量置:
> echo 'export PATH=$PATH:~/.android-sdk-macosx/platform-tools/' >> ~/.bash_profile

4.更新配置文件
>source ~/.bash_profile

5.检验是否成功
> adb devices

6.实际操作后，再打印日志   
  log日志信息（日志保存到电脑固定的位置，比如D:\log.txt）
> adb logcat -v time > ~/log.txt   
> control+c   
> logproxy(日志标识)   