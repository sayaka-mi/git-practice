# Git 基本操作まとめ

## 1. git init
新しいリポジトリを作成し、フォルダをGit管理下に置く。
```bash
git init
```

## 2. git add
ファイルの変更を「ステージ」に追加する。
```bash
git add ファイル名
```

## 3. git commit
ステージにある変更を記録する。
```bash
git commit -m "コミットメッセージ"
```
「-m」はメッセージを付けるオプション

## 4. git status
現在の変更状況を確認できる。
```bash
git status
```

## 5. git log
コミットの履歴を表示する。
```bash
git log
```
## 6. GitHubリポジトリ作成（Web画面）
GitHubにログインし新しいリポジトリを作成する。
リポジトリ名を決めて「Create repository」をクリックする。

## 7. リモートリポジトリの追加
ローカルリポジトリにGitHubのリモートリポジトリを登録する。
```bash
git remote add origin https://github.com/ユーザ名/リポジトリ名.git
```
(例)
```bash
git remote add origin https://github.com/sayaka-mi/git-practice.git
```

## 8. ブランチ名をmainに変更
```bash
git branch -M main
```

## 9. ローカルのコミットをGitHubにプッシュする
初めてリモートリポジトリにプッシュするときに使う。
```bash
git push -u origin main
```
- ユーザー名とパスワード(Personal Access Token)が求められる。
- パスワードの代わりにPersonal Access Tokenを入力する。

## 10. Personal Access Token(PAT)の作成
GitHubのパスワード認証は廃止されており、代わりにPATを使用する。
1. GitHubの「Settings」>「Developer settings」>「Personal access tokens」>「Tokens (classic)」
2. 「Generate new token (classic)」をクリックする。
3. トークン名を入力（例：VSCode Push Token）
4. 有効期限を設定する。
5. 「repo」権限にチェックを入れる。
6. 「Generate token」をクリックし、表示されたトークンをコピーする。
7. プッシュ時のパスワード欄にこのトークンを貼り付けて使う。

## 11. Gitの認証情報をWindows資格情報マネージャーで保存する
```bash
git config --global credential.helper manager-core
```
この設定をすると、初回の認証情報を保存し、以降は入力不要となる。

## 12. git clone
リモートリポジトリ（GitHub上のもの）を自分のPCに丸ごと複製する。
初めてリポジトリをローカルにコピーしたいときに使う。
```bash
git clone https://github.com/ユーザ名/リポジトリ名.git
```
（例）
```bash
git clone https://github.com/sayaka-mi/git-practice.git
```

## 13. git pull
リモートリポジトリで他の人が自分の更新した内容を、ローカルの自分のPCに取り込んで最新の状態にする。
```bash
git pull origin ブランチ名
```
（例）mainブランチの最新を取り込む場合
```bash
git pull origin main
```
- 複数のブランチがある場合は作業中のブランチに合わせてリモートの同じブランチを指定する。
- 異なるブランチの更新は、まずそのブランチに切り替えてからgit pullする。

## 14. git branch
ブランチの一覧や新しいブランチの作成に使う。
```bash
# 現在のブランチ一覧を表示
git branch

# 新しいブランチを作成（例：feature-branch）
git branch feature-branch
```

## 15. git checkout
作業するブランチを切り替えるコマンド。
```bash
# 既存のブランチに切り替える
git checkout ブランチ名

# 例：feature-branchに切り替える
git checkout feature-branch

# 新しいブランチを作りながら切り替える場合
git checkout -b 新しいブランチ名
```

