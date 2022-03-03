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

### The vim-zettal plugin for zettelkasten method of note taking  
See https://github.com/michal-h21/vim-zettel.  

The method creates a network of ideas. The rules for this method are:  
1. Write down the idea in your own words  
2. Record all knowledge, more ideas create more links
3. Think through each idea and reduce it to its kernal
4. Link up kernals with other ideas

Typically you want the title of the idea to summarise it, this makes it easy to link the ideas latter.  

I'm not sure if you should have multiple libraries ie work, home etc, or consider all the ideas interlinked, I think the former.  

I don't yet understand all the short cuts. This plugin is based on `vimwiki`, which stores the notes in a folder called `~/vimwiki/`, each note is a file named after the link. You can link notes together by linking to the file of the note that you want to reference. Apparently you are meant to be able to search but I can't workout how. This would be good to link up notes via searching for the topics or tags that can also be added to notes.  

The shortcuts are (work in progress):   
But see https://github.com/michal-h21/vim-zettel/blob/master/doc/zettel.txt
and https://www.reddit.com/r/Zettelkasten/comments/fidaum/vimzettel_an_addon_for_the_vimwiki_addon_for_vim/
and http://vimwiki.github.io/  

```
from http://vimwiki.github.io/

    <Leader>ww – Open the default wiki index file
    <Leader>ws – Select and open wiki index file
    <Enter> – Follow/Create wiki link
    <Backspace> – Go back to parent(previous) wiki link
    <Tab> – Find next wiki link
    <Shift-Tab> – Find previous wiki link

# to link a note (ie link to the note file
[[./filename]]

# search for notes via note VimWikiSearch
:VWS <pattern>

# link to file but create real world description ie this will show 'list of chores'
[[./filepath|list of chores]

## vim-zettel
# search using silversearcher-ag
# requires silver search:  apt-get install silversearcher-ag
# in insert mode
just type "[[" will bring up a list of files etc, select hit enter
# in normal mode after you save a note you can get a link by using "T", then paste it
# and it automatically inserts the link to that file (have to save it first)

You can create a new note with the selected text as the note title by typing z.
" xnoremap z :call zettel#vimwiki#zettel_new_selected()<CR>
xmap z <Plug>ZettelNewSelectedMap

# titles and date MD at top of note
%title this is a title
%date

# tags
:tag1:tag2:

# use <leader>vt to search for a tag



```
