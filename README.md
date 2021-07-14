# setup_macOS

MBP などの MacOS の環境構築をする時にやることをメモっておく

# 最初に入れておくと良い CLI ツール

```
git
git-secrets
jq
```

# Git 初期設定

Mac の Finder やエディタが自動的に生成するファイルをコミットしない

```
touch ~/.gitignore_global
curl https://raw.githubusercontent.com/github/gitignore/master/Global/macOS.gitignore >> ~/.gitignore_global
curl https://raw.githubusercontent.com/github/gitignore/master/Global/VisualStudioCode.gitignore >> ~/.gitignore_global
curl https://raw.githubusercontent.com/github/gitignore/master/Global/Vim.gitignore >> ~/.gitignore_global
curl https://raw.githubusercontent.com/github/gitignore/master/Global/Emacs.gitignore >> ~/.gitignore_global
git config --global core.excludesfile ~/.gitignore_global
```

# AWS や GCP の認証情報がコミットされないようにする

```
brew install git-secrets
git secrets --register-aws --global
git secrets --add 'private_key' --global
git secrets --add 'private_key_id' --global
git secrets --add 'kind: Secret' --global
```
