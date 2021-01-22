## WSL general setup

### Installation
bash....

### Uninstallation
### reset


### General commands:
- Check the wsl related commands: ```wsl -``` or ```wsl --help``` 
- Check the detail info. of all distributions (including running status): ```wsl -l -v```
- Shut down all runing distributions: ``` wsl --shutdown```
- Terminate a specific distributions: ```wsl  -t <Distro>```





## Anaconda
### Spyder GUI
- Download mobaxterm
- ```sudo apt-get install qtbase5-dev``` (source: https://github.com/Microsoft/WSL/issues/1246)
- ```conda update qt pyqt -c conda-forge``` (source: https://github.com/spyder-ide/spyder/issues/4426)
