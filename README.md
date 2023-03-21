## コンテナの起動
```bash
docker-compose up -d
```

### MEMO

- react hot reload が効かない件  
docker-compose.ymlのports`"3000:3000"`について、ホスト側のポート番号を一致させていないとホットリロードがうまく動作しなくなるので、`"3000:3000"`にしています。

- entrypoint.sh について
`entrypoint: bash -c ./entrypoint.sh`をコメントアウトしているのは、create-react-appでReact環境を構築するためにコンテナ内のユーザをnodeにするためのもの。
スクリプトを動作させる時には、rootユーザでないと起動できなかったので、コメントアウトしている。
