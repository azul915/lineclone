# Nuxt.js + FirebaseでLINEのクローンを作る

## Nuxt.jsってなに？
* Vue.js製のフレームワーク
* SSR（サーバーサイドレンダリング）の基盤提供
(<-Vue単体でやるとするとvue-routerをパッケージインストールする必要がある)
* ただ、コーディング自体はVueファイルを作って行うので実質、Vue.js

## 環境
* Nuxt.js 2.9.2
* Firebase
* Docker

## 環境構築手順
1. 任意のディレクトリにline_cloneフォルダを置く
2. docker-compose buildでイメージ作る（以下例）

```bash
~/Desktop/line_clone $ docker-compose 

#[補足] キャッシュを使ってイメージを作りたくないとき
~/Desktop/line_clone $ docker-compose --no-cache
```
3. docker-compose up -dでコンテナを作成（以下例）

```bash
# バックグラウンドで実行している（コマンドはdocker-compose.ymlがあるディレクトリで実行する）
~/Desktop/line_clone $ docker-compose up -d 

# コンテナの起動を確認する
~/Desktop/line_clone $ docker ps -a
```

4. コンテナに入る

```bash
# コンテナID指定でもいいが、docker-compose.ymlでコンテナ名を定義している
~/Desktop/line_clone $ docker exec -it line_clone /bin/ash
```

5. コンテナ内でNuxtのアプリサーバーを起動（基本的に立ち上げっぱなし、「Ctrl + c」で停止）

```
/var/www/project # yarn dev
```

6. ブラウザでlocalhost:3000にアクセスする