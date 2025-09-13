This dotfiles similarly follows one of [Atlassian Blog](https://www.atlassian.com/git/tutorials/dotfiles) which originally from [Hacker News thread](https://news.ycombinator.com/item?id=11071754)

The workflow should be similar except replication part of blog (Following that is also valid though)

## Setup
```sh
git init --bare $HOME/.dotfiles
alias dotfiles ='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles config status.showUntrackedFiles no
dotfiles remote add origin git@github.com:Sherwin-77/dotfiles.git
```

## Cloning
```sh
git clone --separate-git-dir=$HOME/.dotfiles https://github.com/Sherwin-77/dotfiles.git .dotfiles-tmp
# Do some sync or recursive move all the contents if you want to replace existing one
rm --recursive .dotfiles-tmp
```

## Example
```sh
dotfiles status
dotfiles add config
dotfiles commit -m "Add config"
dotfiles push
```