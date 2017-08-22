## My vimrc file
### Instuctions  
From your home directory clone the repo:  
```bash
git clone https://github.com/dwheelerau/dotvim.git
```  

Symlink your vimrc to this repo  
```bash
ln -s /home/dwheeler/dotvim/vimrc ~/.vimrc
```  

### Install plugins using plug  
Follow the instructions at this webpage:  
https://github.com/junegunn/vim-plug  
but basically..  
```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

Open vim and use `:PlugInstall`  

Some of the plugins may require compilation, namely YCM.  
see: https://github.com/Valloric/YouCompleteMe  
```bash
cd ~/.vim/plugged/YouCompleteMe/
# for go and jscript
./install.py  --gocode-completer --tern-completer
```
This should compile.

### Syntastic support for jscript and python  
*This is painful*, I needed up using eslint, but this req upgrade node.  
 
```bash
sudo apt-get install npm
sudo npm install n -g
sudo n latest
sudo npm install -g eslint
sudo npm install -g eslint-config-google
#then run and follow instructions, chose popular style (google) and json formt)
sudo eslint --init

#sudo apt-get install nodejs
# try jslint from command line
#sudo npm install -g jslint
# if that does not work install the following
#sudo apt-get install nodejs-legacy
```
Add the following to your vimrc
```bash
let g:syntastic_javascript_checkers = ['eslint']
```

For python:
```bash
# this is for python
sudo apt-get install pyflakes
```
**For javascript highlighting.**  

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

### Then clone the dottmux repo to get tmux integration working  

```bash
git clone https://github.com/dwheelerau/dottmux
ln -s /home/dwheeler/dottmux/tmux.conf ~/.tmux.conf
```
