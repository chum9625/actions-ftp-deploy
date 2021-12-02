# Actions FTP自動デプロイ

1. 更新sauceをdevelopブランチにpush。（通常の開発作業）
2. 公開段階になったらGitHub上でプルリク→マージ（アクションが走り、本番サーバーにデプロイされる）

## Initial deployment

初回配備の流れ。

### 1. ブランチの準備（GitHub側：Settings＞Branches）

- developブランチを作成しデフォルトにする。

### 2. Actions secretsの設定（GitHub側：Settings＞Secrets）

- ホスティングサーバー値を設定＆追加。
  - FTP_SERVER
  - FTP_USERNAME
  - FTP_PASSWORD

### 3. ディレクトリの設定（エディター側）

- LOCAL_DIR
- REMOTE_DIR

#### 例（WordPressテーマ）

- ftpdeploy.yml 抜粋

```bash
  FTP_SERVER: ${{ secrets.FTP_SERVER }}
          FTP_USERNAME: ${{ secrets.FTP_USERNAME }}
          FTP_PASSWORD: ${{ secrets.FTP_PASSWORD }}
          LOCAL_DIR: ./
          REMOTE_DIR: "/***/***/public_html/***/wp-content/themes/my-theme"
```

### 4. Pull Requests の実行（GitHub側：Pull requests＞New pull request）

- developブランチからmainブランチへプルリクし、マージする。

## Regular update work

- 公開段階で手順4を実施。
