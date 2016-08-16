##Bluetooth connection
    remember device across OS
    enable bluetooth after resume from sleep

## Timezone problem between Windows and Ubuntu
sudo sed -i 's/UTC=no/UTC=yes/' /etc/default/rcS


## Thundermail
buntu下：在当前os用户的主目录home下，找到隐藏的 .thunderbird配置文件夹，修改 profiles.ini 文件 的 “Path=rruqn7mg.default” 配置（可能你的不是该值）。建立一个指向 共用profile的软链接，修改值“rruqn7mg.default”为该软链接。 
　　windows下：添加 thunderbird 启动参数 “-profile=共用的profile文件夹”
　　
## GRUB 2 Theme
http://tieba.baidu.com/p/4196513782?pn=1
https://www.gnome-look.org/p/1009533/

第一步 : 复制GRUB2主题包到/boot/grub/themes
因为涉及修改系统文件，用root身份，终端操作设置。
（Ubuntu开终端, Ctrl + Alt + T)
第一个命令， 在/boot/grub里创建GRUB2打主题目录themes

    sudo mkdir -p /boot/grub/themes/mytheme

复制GRUB2-themes_20151204主题包文件到目录/boot/grub/themes sudo cp -an ~/桌面/GRUB2-themes_20151204/* /boot/grub/themes

## GWwireless network
https://www.reddit.com/r/gwu/comments/3h831q/linux_and_gwireless/

Edit: This is copy pasted directly from the email IT sent. It worked for me, can't promise for you. I was using Ubuntu 14.10, if that helps.

"Enable the wireless service on your device

Select the SSID GWireless

Select PEAP for the EAP method and MSCHAPV2 for phase 2 authentication

Enter your NetID (NetID@gwu.edu) for your identity

Enter the password that corresponds with your e-mail address

Select Connect"


## Monitor brighterless + PWM control (both startup and wakeup from sleep)

## 我的brightness 和actual_brightness 文件并不能写。所以我就要更改它们的权限了。

    chmod 777 /sys/class/backlight/intel_backlight/brightness

    chmod 777 /sys/class/backlight/intel_backlight/actual_brightness

    sudo gedit /etc/rc.local #加入下面几行到 exit 0 之前
    ( echo 6440 | sudo intel_reg write 0xC8254 0x65c065c ) &
    echo 423  > /sys/class/backlight/intel_backlight/brightness &
    echo 423  > /sys/class/backlight/intel_backlight/actual_brightness &



### Run script on wakeup from sleep
http://askubuntu.com/questions/226278/run-script-on-wakeup

    sudo chmod a+x /lib/systemd/system-sleep/pwm




## Text input method
    im-config

language support
https://wiki.archlinux.org/index.php/Fcitx_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#.E7.AC.AC.E4.B8.89.E6.96.B9.E6.8B.BC.E9.9F.B3.E8.BE.93.E5.85.A5.E6.B3.95



有必要就再删除干净fcitx相关的

    sudo apt-get remove fcitx

    sudo apt-get remove fcitx*  

    sudo apt-get autoremove   // 删除依赖包，不再使用的package

    sudo apt-get -f install   // 尝试修正安装过程中出现的依赖性关系

    sudo apt-get install fcitx-rime // 还是Rime好用，虽然没有云词库

    sudo apt-get fcitx-googlepinyin //fcitx 下的google拼音（手机移植）

    sudo apt-get install fcitx-module-cloudpinyin // 安装fcitx的云拼音模块



## Good Softwares

### Matlab

### Netease music

### Calibre 
http://calibre-ebook.com/download

### Chrome

### Medeley

### Unity tweak tool

### Conky

### Redshift
http://jonls.dk/redshift/

    sudo apt-get install redshift
    





  

