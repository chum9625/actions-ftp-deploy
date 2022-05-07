# Actions FTP自動デプロイ

1. 更新したsourceをdevelopブランチにpush。（通常の開発作業）
2. 公開段階になったらGitHub上でプルリク
3. マージ
4. アクションが走る（4分弱？かかる）
5. 本番サーバーデプロイ完了

## Initial deployment

初回配備の流れ。

### 1. ブランチの準備（👆上部セレクター）

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
