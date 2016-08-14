###Bluetooth connection
    remember device across OS
    enable bluetooth after resume from sleep

### Timezone problem between Windows and Ubuntu
sudo sed -i 's/UTC=no/UTC=yes/' /etc/default/rcS


### Thundermail
buntu下：在当前os用户的主目录home下，找到隐藏的 .thunderbird配置文件夹，修改 profiles.ini 文件 的 “Path=rruqn7mg.default” 配置（可能你的不是该值）。建立一个指向 共用profile的软链接，修改值“rruqn7mg.default”为该软链接。 
　　windows下：添加 thunderbird 启动参数 “-profile=共用的profile文件夹”
　　
### GRUB 2 Theme
http://tieba.baidu.com/p/4196513782?pn=1
https://www.gnome-look.org/p/1009533/

第一步 : 复制GRUB2主题包到/boot/grub/themes
因为涉及修改系统文件，用root身份，终端操作设置。
（Ubuntu开终端, Ctrl + Alt + T)
第一个命令， 在/boot/grub里创建GRUB2打主题目录themes
sudo mkdir -p /boot/grub/themes/mytheme
复制GRUB2-themes_20151204主题包文件到目录/boot/grub/themes sudo cp -an ~/桌面/GRUB2-themes_20151204/* /boot/grub/themes

###GWwireless network
https://www.reddit.com/r/gwu/comments/3h831q/linux_and_gwireless/
Edit: This is copy pasted directly from the email IT sent. It worked for me, can't promise for you. I was using Ubuntu 14.10, if that helps.
"Enable the wireless service on your device
Select the SSID GWireless
Select PEAP for the EAP method and MSCHAPV2 for phase 2 authentication
Enter your NetID (NetID@gwu.edu) for your identity
Enter the password that corresponds with your e-mail address
Select Connect"


### Startup monitor brighterless + PWM control
我的brightness 和actual_brightness 文件并不能写。所以我就要更改它们的权限了。
chmod 777 /sys/class/backlight/intel_backlight/brightness
chmod 777 /sys/class/backlight/intel_backlight/actual_brightness

sudo gedit /etc/rc.local
echo 423  > /sys/class/backlight/intel_backlight/brightness &
echo 423  > /sys/class/backlight/intel_backlight/actual_brightness &
( echo 6440 | sudo intel_reg write 0xC8254 0x65c065c )



### Run script on wakeup from sleep
http://askubuntu.com/questions/226278/run-script-on-wakeup




  

