# dotvim-workstation
Dotvim for my work workstation

# My vimrc file  
## If starting fresh you need to sinstall the vim-plug  
Instructions are here: `https://github.com/junegunn/vim-plug`.  

But basically.  
```bash  
# downloads plug.vim and puts it in .vim/autoload/ creats dirs on fly
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

Now you are ready to use the shared vimrc file via your dotvim  

## linking up the shared vimrc on a new computer  
After installing `plug-vim` all you to do is clone the repo and symlink the
vimrc file in the repo to a .vimrc file in your home directory.  

That way if you update the repo and pull your link should automatically update
your environment on this computer.  

```bash  
# clone the repo to your home directory  
git clone https://github.com/dwheelerau/dotvim.git
# Symlink your vimrc to this repo Note: if you moved the dir change the path 
ln -s /home/dwheeler/dotvim/vimrc ~/.vimrc
```  

## Starting from scratch with the `plug.vim` demo `.vimrc`.  
1. Copy or overwrite the vimrc file in the git repo with the example vimrc from
the `plug.vim` repo.

2. Delete the plugins that you do not need.  

3. Open vim and call `PlugInstall` to install the plugins listed in the vimrc.  

4. Some packages may require manual compiling outside of vim (see below).  

## Extra instructions for Packages  

### coc-vim for autocompletion  
See instructions here: https://github.com/neoclide/coc.nvim 

Note requires node.js  

Use **ctl-p** in insert mode to scroll options and **ctl-n** (down) and **ctl-p** (up) to
move through the options.  

### coc-pyright  
Python autocomplete for python3: https://github.com/fannheyward/coc-pyright  

Note that I have not set this up for conda, see instructions below, I haven't
worked out how to modify the coc-settings json file to make this work.  

See the coc short cuts above.  

1. press enter to compete with the current top suggestion
2. press <ctl>n to scroll through options, enter to confirm
2. press <ctl>p to scroll back through options, enter to confirm
