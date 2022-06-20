# Actions FTP自動デプロイ

サイトの更新作業を効率的にする。

[<img alt="Deployed with FTP Deploy Action" src="https://img.shields.io/badge/Deployed With-FTP DEPLOY ACTION-%3CCOLOR%3E?style=for-the-badge&color=2b9348">](https://github.com/SamKirkland/FTP-Deploy-Action)

## Flow

1. 更新sourceをdevelopブランチにpush。（通常の開発作業）
2. 公開段階になったらGitHub上でプルリク
3. mainにマージ
4. アクションが走る（4分弱？かかる）
5. 本番サーバーデプロイ完了

## 🌱 Initial deployment

👇 初回手順

### 1. ブランチの準備

- developブランチを作成（👆新規作成は上部セレクターで実施）
- [デフォルト設定はリポジトリのSettingsで行う](https://github.com/chum9625/actions-ftp-deploy/settings/branches)

### 2. [Actions secretsの設定](https://github.com/chum9625/actions-ftp-deploy/settings/secrets/actions)

- ホスティングサーバー値を設定＆追加。
  - FTP_SERVER
  - FTP_USERNAME
  - FTP_PASSWORD
  - FTP_SERVER_DIR 

### 3. 最新版 main.yml を使うこと

- 2022/6/13 実行テスト済み
- ~除外ファイルがうまく機能していないようだ~ 🆗 2022/6/14 確認済

#### 例）WordPressテーマ開発

- localはテーマディレクトリルートでgit init

### 4. Pull Requests の実行

1. developブランチからmainブランチへ[プルリク](https://github.com/chum9625/actions-ftp-deploy/pulls)
2. マージ

## 🌼 Regular update work

👆 公開段階で**手順4**を実施。
