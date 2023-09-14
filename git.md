## 事前準備

- [ ]  Githubアカウントに2段階認証の設定をする

セキュリティ向上のため、2段階認証の設定をします。
[こちらの公式ドキュメント](https://docs.github.com/ja/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)に従い、アカウントに2段階認証を設定しましょう。

- [ ]  トークンの発行をする

Githubは、パスワードの代わりにトークンを要求される場合があります。
[こちらの公式ドキュメント](https://docs.github.com/ja/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#creating-a-token)に従い、アクセストークンを発行しましょう。発行時には、以下のポイントを守ってください。

- トークン名は「Github Token」とする
- Expiration（有効期限）は「90days」を指定する
- スコープ（チェックボックス）は全て選択する
- 発行されたトークンはメモ帳に一時保存しておく
（※ 一度ページを離れたら2度と確認できなくなります）

## 基礎知識

### 参考リンク

以下のスライド・リンクも参考にしてみてください。
上の2つは読み物なので、ぜひ一読してください。

[Github導入説明資料](https://docs.google.com/presentation/d/1XtPKNIcdWVsu4h_DhEiU4UQ_NEpLgHsFqBM8Z3G4vBM/edit?usp=sharing)

[Perl-Entrance-Textbook/git.md at master · perl-entrance-org/Perl-Entrance-Textbook](https://github.com/perl-entrance-org/Perl-Entrance-Textbook/blob/master/git.md)

[Git入門編](https://paiza.jp/works/git/primer)

### 解説

- リモート（クラウド）にあるプロジェクトを自身のローカル（PC）に取得：clone（クローン）

```jsx
$ git clone https://プロジェクトのurl
```

- ブランチの新規作成

```jsx
$ git checkout -b 新規ブランチ名
```

- 既存ブランチの切り替え

```yaml
$ git switch 新規ブランチ名
```

- 追跡可能なリモートブランチの情報を取得する

```yaml
$ git fetch origin main
```

- リモートブランチの情報を取得する：pull（プル）

```yaml
$ git pull origin ブランチ名
```

※ git pull だけの場合、自動的に現在選択中のブランチ情報を取得します

- コミット対象の選定（反映する対象の選定）：add

```yaml
$ git add ファイルパス
```

※ git add . （ピリオド）で全選択が可能

- ローカルブランチに変更を反映（反映の確定）：commit（コミット）

```yaml
$ git commit -m "作業内容コメント"
```

※ #Github番号をコメントに入れると、issueやpull requestと紐づけることができます
（例）git commit -m “日付登録処理の修正 #12”
また、コミットコメントは作業履歴の追跡に使うため、とても重要です。以下のサイトも参考にしてみてください。
（これいきなりできたらモテます）
https://qiita.com/konatsu_p/items/dfe199ebe3a7d2010b3e


- リモートブランチに変更を反映：push（プッシュ）

```yaml
// 通常
$ git push origin ブランチ名
// 初回の場合
$ git push -u origin ブランチ名
```

※ pull同様、git push だけの場合は自動的に選択中のブランチ名と同名のリモートブランチが指定されます

## 課題の進め方
1. 課題を上から順番に指示に従いこなすこと
2. 不明点や質問があればメンターに相談をすること

## 課題

- [ ]  git cloneをして以下のプロジェクトを取得
[https://github.com/visionary-japan/github_training.git](https://github.com/visionary-japan/github_training.git)
パスワードを要求されるが、トークンを入力すること
- [ ]  mainブランチを起点に、自身のブランチを切る
ブランチ名は、**feature/アカウント名** とする
- [ ]  作成したブランチにdevelopブランチの情報を取り込む
※ エラーが発生します。この状態を、コンフリクトと言います
- [ ]  コンフリクトを解消し、コミット・プッシュをして新規ブランチを発行する
- [ ]  以下のコードを、**index.js**のファイルの最下部に追加する

```yaml
console.log('H');
console.log('E');
console.log('L');
console.log('L');
console.log('O');
```

- [ ]  コミット・プッシュをする
- [ ]  プルリクエストを作成する
- [ ]  レビューの修正をする
- [ ]  マージされるまで修正を繰り返す
