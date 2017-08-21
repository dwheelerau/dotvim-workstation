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

Open vim and use `:PlugInstall`  

Some of the plugins may require compilation, namely YCM.  
see: https://github.com/Valloric/YouCompleteMe  
`cd ~/.vim/plugged/YouCompleteMe/`  
`./install.py`  

This should compile.

### Then clone the dottmux repo to get tmux integration working  
https://github.com/dwheelerau/dottmux  

### Syntastic packages  
```bash
sudo apt-get install nodejs
sudo apt-get install npm
# try jslint from command line
sudo npm install -g jslint
# if that does not work install the following
sudo apt-get install nodejs-legacy

# this is for python
sudo apt-get install pyflakes
```
**for javascript highlighting.**  

Create `~/.tern-config` containing the following  
```bash
{
  "plugins": {
    "node": {},
    "es_modules": {}
  },
  "libs": [
    "ecma5",
    "ecma6"
  ],
  "ecmaVersion": 6
}
```
