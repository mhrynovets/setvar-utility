# setvar-utility
A small bash script to create and use files with `key=value` data, with bash autocompletion

## About this script
Utility is designed to work with text files, that contains lines with `key=value` pairs.  
By setting `key=value` pair destination file will be created.
Operations `set`, `unset` cause overwriting destination file.  

### Usage
Set and overwrite `key=value` pair  
`setvar FILE set KEY VALUE`
Remove `key=value` pair (all arguments after `KEY` ignored)  
`setvar FILE unset KEY [...]`
Show all saved `key=value` pairs  
`setvar FILE show`
Show VALUE of `key=value` pair (all arguments after `KEY` ignored)  
`setvar FILE show KEY [...]`

### Side effect
Generated destination file FILE can be used to set environment variables with command  
`source FILE`

### Enabling bash autocompletion
1. Script should have enabled execution bit, that can be done by  
`chmod a+x setvar`
1. Script should be placed into PATH directories (`/bin`, `/usr/bin`, etc.).  
Without elevating privilages script can be placed to user local PATH at `$HOME/bin`  
`cp setvar $HOME/bin` 
1. Then completion script must be added to user environment. It can be done by adding in `$HOME/.bashrc` file next command  
`complete -C setvar setvar`

After copying script PATH ditectory and modifying environment - user should logout from system and login back to applying changes.