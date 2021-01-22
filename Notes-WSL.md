## WSL general setup

## Notes：
Note that all commands (especially the WSL related ones) may change according to the WSL updates.


### Installation
bash....

### Uninstallation


### reset


### General commands:
- Check the wsl related commands: ```wsl -``` or ```wsl --help``` 
- Check the detail info. of all distributions (including running status): ```wsl -l -v```
- Shut down all runing distributions: ``` wsl --shutdown```
- Terminate a specific distributions: ```wsl  -t <Distro>```



## Ubuntu (WSL)
### General command
- Check Ubuntu version: ```lsb_release -a```

- Update: ```sudo apt update && sudo apt -y upgrade```

### GUI environment setup
Note: Windows 10 is going to release official GUI support (waiting for official release)

Reference:
https://techcommunity.microsoft.com/t5/windows-dev-appconsult/running-wsl-gui-apps-on-windows-10/ba-p/1493242
https://medium.com/@japheth.yates/the-complete-wsl2-gui-setup-2582828f4577




## Anaconda
### Spyder GUI
- Download mobaxterm
- ```sudo apt-get install qtbase5-dev``` (source: https://github.com/Microsoft/WSL/issues/1246)
- ```conda update qt pyqt -c conda-forge``` (source: https://github.com/spyder-ide/spyder/issues/4426)
