# VIMWIKI NOTES

# Contents

- [VIMWIKI NOTES](#vimwiki-notes)
    - [USEFUL WEBSITES](#useful-websites)
    - [KEYBINDINGS](#keybindings)
    - [TABLES](#tables)

## USEFUL WEBSITES

    * [VimWiki Homepage](http://vimwiki.github.io)
    * [Markdown Guide](https://www.markdownguide.org/basic-syntax/) 
 
## KEYBINDINGS
    <Leader>ww – Open the default wiki index file
    <Leader>ws – Select and open wiki index file
    <Leader>wr – Rename wiki page you are in
    <Leader>wd – Delete wiki page you are in
    <Enter> – Follow/Create wiki link
    <Backspace> – Go back to parent(previous) wiki link
    <Tab> – Find next wiki link
    <Shift-Tab> – Find previous wiki link

    [[ - go to previous header
    ]] - go to next header
    
    <C-Space> - toggle checkbox of a list item on/off
    gnt - find next unfinished task
    
    "gl" commands for lists
    gl<Space> - remove checkbox
    gL<Space> - remove all checkboxes from sibling list items
    gln - increase done status
    glp - decrease done status
    
    gll - increase level of list item 
    gLl - increase level of list item and children
    glh and gLh - decrease level of list items
    <C-t> and <C-d> when in insert mode to increase / decrease list level
    
    glr - renumber list items
    gl* - make a list item out of a normal line
    gl1 - convert to numbered list
    glx - disable checkbox item 
   
    gqq - reformat table after changes
    
    For more keys, see :h vimwiki-mappings

## TABLES

    To create a table run 
    :VimwikiTable [cols] [rows]
   
    **Now bound to <Leader>wvt**
    
    gqq - reformat table after changes
  
  
## USEFUL COMMANDS

## USEFUL SYNTAX

### Interwiki Links
  (wn.My Name:This is a link)
  
