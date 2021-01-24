## WSL general setup

**Notes：All commands (especially the WSL related ones) may change according to the WSL updates.**

### Installation
#### Step 1 - Enable the Windows Subsystem for Linux
Open "Windows Features and tick the corresponding option, or using the Powershell command:
  ```
  % Powershell
  dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
  ```

#### Step 2 - Check requirements for running WSL 2
For x64 systems: Version 1903 or higher, with Build 18362 or higher.

#### Step 3 - Enable Virtual Machine feature
Open "Windows Features and tick the corresponding option, or using the Powershell command:
  ```
  % Powershell: 
  dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
  ```

#### Step 4 - Download and install the Linux kernel update package
WSL2 Linux kernel update package for x64 machines 

(https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

#### Step 5 - Set WSL 2 as your default version
  ```
  % Powershell: 
  wsl --set-default-version 2
  ```

#### Step 6 - Install your Linux distribution of choice
Open the Microsoft Store, select and install your favorite Linux distribution.

I choose Ubuntu here. 


### Uninstall and Reset （distribution）
- Search Apps & features in the Start menu
- On the Apps & features page in the Settings app, type Ubuntu, or the name of the Linux distribution you want to reset, in the ‘Search this list’ box.
- Ubuntu, or the name of your Linux distribution, will appear. Click it and see "Uninstall" and then click Advanced options for "Reset".

### General commands:
- Check the wsl related commands: ```wsl -``` or ```wsl --help``` 
- Check the detail info. of all distributions (including running status): ```wsl -l -v```
- Shut down all runing distributions: ``` wsl --shutdown```
- Terminate a specific distributions: ```wsl  -t <Distro>```



## Ubuntu (WSL)
### General command
- Check Ubuntu version: ```lsb_release -a```
- Update: ```sudo apt update && sudo apt -y upgrade```
- Check all installed package: ```sudo dpkg --list```
- Check all install software: ```sudo apt list```
- Remove files: ```rm```
- Remove folders: 1. empty directory ```rmdir``` 2. non-empty folder ```rm -r ```

### GUI environment setup
Note: Windows 10 is going to release official GUI support (waiting for official release)

- Best solution: mobaxterm !!! everything is out of box ! with some good handy features as well. It also features a file system browser which you can easily visit， copy, and delete folds and files in the WSL-Ubuntu system (includes text editor to directly open text files).

https://mobaxterm.mobatek.net/

- Alternative ( if you want to torture yourself...)
-- Install xrdp:
  ```
  sudo apt install net-tools
  sudo apt install xrdp -y && sudo systemctl enable xrdp
  ```
-- Install VcXsrv: 

https://sourceforge.net/projects/vcxsrv/



-- Difference between Vanilla Xfce desktop and the one install through ```tasksel```

https://linuxconfig.org/install-xfce-xubuntu-desktop-on-ubuntu-20-04-focal-fossa-linux



**Reference:**

https://techcommunity.microsoft.com/t5/windows-dev-appconsult/running-wsl-gui-apps-on-windows-10/ba-p/1493242

https://medium.com/@japheth.yates/the-complete-wsl2-gui-setup-2582828f4577






## Coding environment

### VScode
https://code.visualstudio.com/docs/remote/wsl


### Anaconda
#### System python and Anaconda python:
Anaconda, by definition, servers as a sandbox that permits you to install packages into strictly defined environments. As long as you're working within one of those environments (running the activate command), your environment will see only those packages that you've installed into it.  So you can basically using the one come with Anaconda and ignore the python 3 come with the Ubuntu installtion.

To see if the conda installation of Python is in your PATH variable:
- On macOS and Linux, open the terminal and run echo $PATH.
- On Windows, open an Anaconda Prompt and run echo %PATH%.

To see which Python installation is currently set as the default:
- On macOS and Linux, open the terminal and run which python.
- On Windows, open an Anaconda Prompt and run where python.


#### Install anaconda
- Go to Anacoda website and obtain the corresponding version download link (https://www.anaconda.com/products/individual)
- Go to Linux terminal (the download link I used is the one below): 
  ```
  wget https://repo.anaconda.com/archive/Anaconda3-2020.11-Linux-x86_64.sh
  ```
- Install Anaconda using : ```sudo bash ~/Anaconda3-2020.11-Linux-x86_64.sh```
   note that the default install location may be displayed as "/root/anaconda3", then change it to the location ```/home/carls_hyx/anaconda3``` according the the Anaconda doc in the reference link. When prompted "Do you wish the installer to initialize Anaconda3", enter ```yes```.


- To make sure the installation will take place effectively, simply reload the shell:
  ```
  source ~/.bashrc
  ```

- Make sure the code line below is written in the .bash_profile file.
  ```
  export PATH=/home/carls_hyx/anaconda3/bin:$PATH
  ```
- Then try 
  ```
  conda --version
  anaconda-navigator
  ```
- Spyder GUI: If you want use  Spyder come with Anaconda (which I don't anymore, I use VScode under Win10 instead). Try the following:

  ```sudo apt-get install qtbase5-dev``` (source: https://github.com/Microsoft/WSL/issues/1246)
  
  ```conda update qt pyqt -c conda-forge``` (source: https://github.com/spyder-ide/spyder/issues/4426)
  
  
#### Uninstall anaconda
  - check out the reference link below.
  - 如果碰到权限问题，check 当前目录文件（夹）权限：```ls -l ~```
  - Change the users 权限：```sudo chown -R carls_hyx:carls_hyx /home/carls_hyx/anaconda3/```
  







**Reference**

https://www.how2shout.com/how-to/install-anaconda-wsl-windows-10-ubuntu-linux-app.html

https://docs.anaconda.com/anaconda/install/linux/

https://docs.anaconda.com/anaconda/install/uninstall/







