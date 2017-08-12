## My vimrc file
### Instuctions  
From your home directory clone the repo:  
`git clone https://github.com/dwheelerau/dotvim.git`  

Symlink your vimrc to this repo  
`ln -s /home/dwheeler/dotvim/vimrc ~/.vimrc`  

### Install plugins using plug  
Follow the instructions at this webpage:  
https://github.com/junegunn/vim-plug  
but basically..  
`curl -fLo ~/.vim/autoload/plug.vim --create-dirs \`  
`    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim`  

Open vim and use `:PluginInstall`  

Some of the plugins may require compilation, namely YCM.  
see: https://github.com/Valloric/YouCompleteMe  
`cd ~/.vim/plugged/YouCompleteMe/`  
`./install.py`  

This should compile.

### Then clone the dottmux repo to get tmux integration working  
https://github.com/dwheelerau/dottmux  
