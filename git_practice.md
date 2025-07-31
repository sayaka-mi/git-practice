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
1. GitHubの「Setting」➔「Developer settings」➔「Personal access tokens」➔「Tokens(classic)」
2. 「Generate new token (classic)」をクリック
3. トークン名を入力（例：VSCode Push Token）
4. 有効期限を設定
5. 「repo」権限にチェックを入れる
6. 「Generate token」をクリックし、表示されたトークンをコピー
7. プッシュ時のパスワード欄にこのトークンを貼り付けて使う