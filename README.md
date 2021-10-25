# GitHub ActionsでFTP自動デプロイ

- 机上のVscodeからdevelopブランチにpush。（通常の開発作業）
- GitHub上でプルリクし、マージする（アクションが走り、本番サーバーにデプロイ）

## 1. ブランチの準備

- developブランチを作成し、デフォルトに設定。

## 2. Secretsで値を設定

- FTP_SERVER
- FTP_USERNAME
- FTP_PASSWORD

## 3. ディレクトリの設定

- LOCAL_DIR
- REMOTE_DIR

### ftpdeploy.yml 抜粋

```bash
  FTP_SERVER: ${{ secrets.FTP_SERVER }}
          FTP_USERNAME: ${{ secrets.FTP_USERNAME }}
          FTP_PASSWORD: ${{ secrets.FTP_PASSWORD }}
          LOCAL_DIR: ./
          REMOTE_DIR: "/***/***/public_html/***/wp-content/themes/my-theme"
```

## 4. Pull Requests の実行

- developブランチからmainブランチへプルリクする
- 自分でマージする
