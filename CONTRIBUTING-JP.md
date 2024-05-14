# 開発者用ガイド
こちらは開発者用のガイドになります
## ブランチのルール
基本的に年月日名前の順で打ちこんでください ex )24-05-15ryoji

#### 個人的おすすめのターミナルの設定
前提条件：Mac OS、zshディレクトリを使っている

bashかzshでやり方が異なるので、自分のPCのシェルを改めて確認してください。
```
echo $SHELL
```
(何も表示されない場合はzsh、bashもないので```mkdir ~/.zsh```で作成してください。 )

#### ターミナルにブランチを表示させるためのプロンプトをダウンロードします。
```
cd ~/.zsh
curl -o git-prompt.sh https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
```
#### .zshrcファイルに設定を記載します
```open ~/.zshrc```で.zshrcを開きましょう、そこから以下のコマンドを**一番上から**打ち込んでいってください、なおvimを利用したやり方もありますが、かなり面倒なのでおすすめしません。
```
source ~/.zsh/git-prompt.sh

GIT_PS1_SHOWDIRTYSTATE=true
GIT_PS1_SHOWUNTRACKEDFILES=true
GIT_PS1_SHOWSTASHSTATE=true
GIT_PS1_SHOWUPSTREAM=auto

setopt PROMPT_SUBST ; PS1='%F{green}%n%f: %F{cyan}%D%~%f %F{red}$(__git_ps1 "(%s)")%f \$ '
```

#### こちらの[URL](https://qiita.com/SabaCrevette/items/56dff171b36888f0445b)を参考にして編集しました、是非ご覧になってください

#### 注意
```setopt PROMPT_SUBST ; PS1='%F{green}%n%f: %F{cyan}%D%~%f %F{red}$(__git_ps1 "(%s)")%f \$ '```
は参考にしている[URL](https://qiita.com/SabaCrevette/items/56dff171b36888f0445b)のものとは異なります。
ブランチのルールに沿っとり、ターミナル内に年月日がでるようにしていますのでご了承ください。