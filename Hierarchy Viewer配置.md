# Hierarchy Viewer配置

最近做性能优化，发现需要使用Hierarchy Viewer进行布局分析。
但是发现手机必须root或者允许模拟器才可以查看，但是记忆里是可以直接看的，难道看错了？
果断google，原来google已经有办法处理了。需要在环境变量里配置一下就行了。鉴于现在都是4.0以上的手机，4.0以下的就不介绍了。
方案如下：

#### Windows
1. Click My Computer > Property > Advanced > Environment Variables.
2. Click New.
3. In variables name put: ANDROID_HVPROTO
4. In variable value put: ddm
5. Click OK

#### Mac
1. Edit ~/.bash_profile
2. Add: # Hierarchy Viewer Variable 
    export ANDROID_HVPROTO=ddm
3. source ~/.bash_profile

#### Linux
1. Edit ~/.bash_profile
2. Add: #Hierarchy Viewer Variable 
    export ANDROID_HVPROTO=ddm
3. source ~/.bash_profile

简单几步就可以使用Hirarchy Viewer进行布局查看了

参考链接：[https://developer.android.com/studio/profile/hierarchy-viewer-setup.html](https://developer.android.com/studio/profile/hierarchy-viewer-setup.html)
