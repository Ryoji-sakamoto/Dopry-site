## Branch Rules:
**Please name your branches in the order of year, month, day, and name. Example: 24-05-15ryoji**

Prerequisites: Mac OS, using the zsh directory

#### Since the method differs between bash and zsh, please check your PC's shell.

```
echo $SHELL
```
(If nothing is displayed, it means you don't have zsh or bash installed, so create one with ```mkdir ~/.zsh.```)

#### Download the prompt to display the branch in the terminal.

```
cd ~/.zsh
curl -o git-prompt.sh https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
```
#### Edit the .zshrc file:
Open .zshrc with ```open ~/.zshrc```and **add the following commands at the top**. Although you can use vim to edit, it's quite cumbersome, so I don't recommend it.

```
source ~/.zsh/git-prompt.sh

GIT_PS1_SHOWDIRTYSTATE=true
GIT_PS1_SHOWUNTRACKEDFILES=true
GIT_PS1_SHOWSTASHSTATE=true
GIT_PS1_SHOWUPSTREAM=auto

setopt PROMPT_SUBST
PS1='%F{green}%n%f: %F{cyan}%D%~%f %F{red}$(__git_ps1 "(%s)")%f \$ '
```

Please refer to the following URL:
https://qiita.com/SabaCrevette/items/56dff171b36888f0445b

**Regarding** ```setopt PROMPT_SUBST```, this is different from the referenced URL.
Please note that I have modified it according to the branch rules so that the date appears in the terminal