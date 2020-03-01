# macOS_dotfiles
mastro35's dotfiles for macOS
-----------------------------

thanks to https://www.atlassian.com/git/tutorials/dotfiles


To start:
--------
```
alias config='/usr/bin/git --git-dir=$HOME/.macos/ --work-tree=$HOME'
git clone --bare https://github.com/mastro35/macOS_dotfiles.git $HOME/.macos
alias config='/usr/bin/git --git-dir=$HOME/.macos/ --work-tree=$HOME'
config checkout
```

The step above might fail with a message like:

```
error: The following untracked working tree files would be overwritten by checkout:
    .zshrc
    .gitignore
Please move or remove them before you can switch branches.
Aborting
```

This is because your $HOME folder might already have some stock configuration files which would be overwritten by Git.
The solution is simple: back up the files if you care about them, remove them if you don't care and rerun 

```
config checkout
```

Finally:
```
config config --local status.showUntrackedFiles no
```

Happy life!
D.
