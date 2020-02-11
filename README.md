# LinuxStaff
## WPS
WPS中文语言包和缺失字体
下载WPS.zip  
将mui中的zh_CN复制到/usr/lib/office6/mui，点击右上角的A切换语言  
解压字体包，点击字体，然后安装  
另外参考[https://blog.csdn.net/davidhopper/article/details/78898881](https://blog.csdn.net/davidhopper/article/details/78898881)将Windows字体导入manjaro  
## Wechat
### 安装方法
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
    [参考链接，有改动](https://github.com/wszqkzqk/deepin-wine-ubuntu/issues/32)  
    ```bash
    sudo dpkg -i --force-all libjpeg62-turbo_1.5.2-2+b1_i386.deb
    ```
5. 解决不能打开公众号文章的问题  
    [参考链接](https://github.com/wszqkzqk/deepin-wine-ubuntu/issues/197)
    本质上仍然无法打开公众号文章，但是利用微信最新版（2.8.0版）可以实现基本上可用的效果。
    - 首先按照链接中的方法替换微信文件
        > 1. 微信官网下载 WeChatSetup.exe 最新版本
        > 2. 退出正在登录的微信
        > 3. Ubuntu桌面：点击 WeChatSetup.exe 右键选择提取到此处
        > 4. 进入 WeChatSetup 目录，找到最多的文件，替换 `~/.deepinwine/Deepin-WeChat/drive_c/Program Files/Tencent/WeChat ` 目录里文件，重启即可
        > 
        该部分文件我已经[下载](https://pc.qq.com/detail/8/detail_11488.html)并提取了，exe为`./WeChat/WeChatSetup_2.8.0.116.exe` ，提取在`./WeChat/WeChatSetup_2.8.0.116` ，直接复制`./WeChat/WeChatSetup_2.8.0.116` 中的文件到`~/.deepinwine/Deepin-WeChat/drive_c/Program Files/Tencent/WeChat ` 目录即可，重名目录合并，同名文件替换。  
        很奇怪在微信官网下载的是2.7版，在第三方野鸡网站可以下载到最新版，不知道为什么。  
        ps:如果没有退出微信就覆盖了，需要重新运行`sudo dpkg -i --force-all deepin.com.wechat_2.6.8.65deepin0_i386.deb` 最后仍然是最新版。  
    - 然后重新打开微信，设置中设置用默认浏览器打开公众号文章。  

    由于新版微信用三栏显示了公众号的历史文章，所以不会出现之前的版本中由于wine崩溃而导致历史文章无法查看的尴尬情况。  
    ![公众号](_v_images/20200211222809764_2071566260.png)
### 依赖问题
更新：  
按照上述方法安装其他程序会显示deepin-wine的依赖未解决，
```
# 卸载
sudo apt install -f
# 重装
wget -O- https://deepin-wine.i-m.dev/setup.sh | sh
# 安装微信
sudo apt-get install deepin.com.wechat
```
### 尚存的问题：  
1. 不能打开小程序
