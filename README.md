# thinking-memo-web

OneNote「Personal book」の思考メモ索引を、スマホから開くための1ファイル。

- `index.html` … 索引の中身を **AES-256-GCM で暗号化**して埋め込んだページ。
  開くとパスワードを聞かれ、正しければブラウザ内で復号して表示する。
  鍵は PBKDF2-SHA256（20万回）でパスワードから作る。復号は Web Crypto なので
  通信もライブラリも不要。**パスワードはこのリポジトリのどこにも無い。**
- 中身の元データと生成スクリプトは OneDrive 側（`AI操作フォルダ/思考メモ`）にある。
  更新は `python tools/build_artifact.py` → `python tools/build_encrypted.py` の順。

公開リポジトリだが、暗号文しか置いていないため、パスワードを知らない人には読めない。
