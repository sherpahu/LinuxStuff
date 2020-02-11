# Wechat
1. 第一步参考教程：[初步安装微信](https://blog.csdn.net/sinat_27672523/article/details/102507714)
    本来的过程
    ```bash
    git clone https://gitee.com/wszqkzqk/deepin-wine-for-ubuntu.git
    ./install.sh
    ```
    已经下载好，在./WeChat/deepin-wine-for-ubuntu下
    故此处只需要：
    ```
    cd ./WeChat/deepin-wine-for-ubuntu/
    ./install.sh
    ```
2. 安装微信helper
    [参考链接](https://github.com/wszqkzqk/deepin-wine-ubuntu/issues/180)
    ```bash
    cd ..
    sudo dpkg -i --force-all deepin-wine-helper_1.2deepin8_i386.deb
    ```
3. 安装微信
    本来的下载地址[微信](https://mirrors.aliyun.com/deepin/pool/non-free/d/deepin-wine-helper/)
    我已经下载好了此时（2020年2月11日）的最新版，在./WeChat/deepin-wine-for-ubuntu下
    ```bash
    sudo dpkg -i --force-all deepin.com.wechat_2.6.8.65deepin0_i386.deb
    ```
4. 解决不能发图片的问题
    ```bash
    sudo dpkg -i --force-all libjpeg62-turbo_1.5.2-2+b1_i386.deb
    ```
尚存的问题：
1. 不能打开公众号文章
2. 微信版本过久不能打开小程序
