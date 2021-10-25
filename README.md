## secretsで設定する箇所

- FTP_SERVER
- FTP_USERNAME
- FTP_PASSWORD

## 適宜設定する箇所

- LOCAL_DIR
- REMOTE_DIR

```bash
  FTP_SERVER: ${{ secrets.FTP_SERVER }}
          FTP_USERNAME: ${{ secrets.FTP_USERNAME }}
          FTP_PASSWORD: ${{ secrets.FTP_PASSWORD }}
          LOCAL_DIR: ./
          REMOTE_DIR: "/***/***/public_html/***/wp-content/themes/my-theme"
```
