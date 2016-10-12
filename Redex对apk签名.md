### Redex
这个工具是facebook发布的，用于压缩apk，提高应用性能的工具。
地址[https://github.com/facebook/redex](https://github.com/facebook/redex)

### 签名过程
今天使用这个工具对apk进行了压缩，发现还是可以压缩一些的。
执行命令如下:

```
redex source.apk -o target.apk
```

但是编译release版本后，安装apk提示Failure [INSTALL_PARSE_FAILED_NO_CERTIFICATES]，显然是没有对包签名的缘故。
但是打release包的时候已经签名了。遂去github上看了看。
[My app fails to install with Failure [INSTALL_PARSE_FAILED_NO_CERTIFICATES]](https://github.com/facebook/redex#my-app-fails-to-install-with-failure-install_parse_failed_no_certificates)
看了已经有过这个问题了。

解决方案：

```
redex source.apk -o target.apk --sign -s path/to/keystore/file -a "keyAlias" -p "keyPassword"
```
经过这个折腾，签名又回来了
