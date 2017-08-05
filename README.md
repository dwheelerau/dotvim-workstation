## My vimrc file
### Instuctions  
`mkdir -p ~/dotvim && cd ~/dotvim`  
`git clone git@github.com:dwheelerau/dotvim.git`  

Symlink your vimrc to this repo  
`ln -s vimrc ~/.vimrc`  

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
