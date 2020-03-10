1. Ubuntu 的软件源配置文件是 /etc/apt/sources.list。
   将系统自带的该文件做个备份，将该文件替换为下面内容.
   https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/
   sudo cp /etc/apt/sources.list /etc/apt/sources.list.old
   sudo gedit /etc/apt/sources.list

2. sudo apt-get update
   sudo apt-get upgrade
   sudo apt-get install git vim
   
3. install shadowsocks-qt5
   sudo add-apt-repository ppa:hzwhuang/ss-qt5
   sudo apt-get update
   sudo apt-get install shadowsocks-qt5
   # config shadowsocks in https://clashcloud.net/
   
   install tsocks:
   sudo apt-get install tsocks
   sudo vim /etc/tsocks.conf
   change to:
     server = 127.0.0.1
     server_type = 5
     server_port = 1080
   use: tsocks wget http://xxx.zip

4. install chrome:
   tsocks wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
   sudo dpkg -i 安装包名称.deb
   # https://github.com/FelisCatus/SwitchyOmega/releases
   # download .crx file, 建议直接先登录在输入Google账户同步
   open setting->network->proxy->manual->socks host: 
   127.0.0.1 1080
   配置完成后只有chrome浏览器可以上国外网站
   login and sync
   # so download SwitchyOmega in chrome shop directly
   firefox上国外网站需要另行配置

5. install zsh, oh-my-zsh
   sudo apt-get install wget curl
   Install and set up zsh as default:
   sudo apt install zsh
   zsh --version
   # Make it your default shell: chsh -s $(which zsh)，重启后才会变成默认
   sh -c "$(tsocks wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   # it will ask if change your default shell to zsh?
   # plugins
   cd ~/.oh-my-zsh/plugins
   git clone git://github.com/zsh-users/zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
   vim ~/.zshrc
   change to:
     ZSH_THEME="ys"
     plugins=(
         git
         zsh-autosuggestions
         zsh-syntax-highlighting
     )
   source ~/.zshrc

6. ubuntu挂载移动硬盘出现错误：mount:unknown filesystem type 'exfat':
   sudo apt-get install exfat-fuse

7. install pycharm
   # https://medium.com/@singh.shreya8/how-to-install-pycharm-in-ubuntu-16-04-ubuntu-14-04-ubuntu-18-04-linux-easiest-way-5ae19d052693
   tar -xzf pycharm-professional-2019.3.3.tar.gz -C ~/
   cd ~/pycharm-2019.3.3/bin
   ./pycharm.sh

8. install Anaconda:
   https://medium.com/@menuram1126/how-to-install-anaconda-on-ubuntu-16-04-538009ca7936

9. install QQ and Wechat
   https://github.com/wszqkzqk/deepin-wine-ubuntu
   wechat error:
   deepin-wine不升级到2.18-19，无法安装最新版本的微信
   https://blog.csdn.net/qq_33254440/article/details/103295245

10. install sogou pinyin
   https://blog.csdn.net/weixin_40728485/article/details/80194775
   问题：中文切换有时会有问题


   
   
   
   
    
   
