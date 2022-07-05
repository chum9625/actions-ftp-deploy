[<img alt="Deployed with FTP Deploy Action" src="https://img.shields.io/badge/Deployed With-FTP DEPLOY ACTION-%3CCOLOR%3E?style=for-the-badge&color=0077b6">](https://github.com/SamKirkland/FTP-Deploy-Action)

# 概要

Webサイトのデプロイを自動化する GitHub Action のひな形。

## 🌱 Flow

1. 更新sourceをdevelopブランチにpush。（通常の開発作業）
2. 公開段階になったらGitHub上でプルリク
3. mainにマージ
4. アクションが走る
5. 本番サーバーデプロイ完了（所要時間10数秒くらい）

## ⚙ 初回Setting

### 1. ブランチの準備

- developブランチを作成
- [developブランチをデフォルトに設定する](https://github.com/chum9625/actions-ftp-deploy/settings/branches)

### 2. [Actions secretsの設定](https://github.com/chum9625/actions-ftp-deploy/settings/secrets/actions)

- ホスティングサーバー値を設定＆追加。
  - FTP_SERVER
  - FTP_USERNAME
  - FTP_PASSWORD
  - FTP_SERVER_DIR 
- **最新版 main.yml を使うこと**

## 🆙 Regular work
 
### Pull Requests の実行

1. developブランチからmainブランチへ[プルリク](https://github.com/chum9625/actions-ftp-deploy/pulls)
2. マージを実行

---

## WordPressテーマ開発のルートディレクトリ

- テーマディレクトリのルートで `git init` 
