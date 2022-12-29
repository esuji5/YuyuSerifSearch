# yuyusearch
- 4コマ漫画のセリフを検索して結果の画像などを表示するためのアプリです。
- フロント側にVue.js 3、検索エンジンにMeilisearchを利用することを想定しています。
- その他、検索用のセリフデータ、表示用のコマ画像データなどが必要です
    - そちらのデータ作成はhttps://github.com/esuji5/yonkoma2data を参考できるかもしれません
- 以下、ローカル環境で動かす想定で記述します

# 環境変数の用意
dev環境用に .env.devファイルを用意

```.env.dev
VUE_APP_API_HOST = http://127.0.0.1:7700
VUE_APP_API_KEY = your-master-key
VUE_APP_DISPLAY_KOMA_IMAGE = 1
```

# Meilisearch
- localhost:7700でMeilisearchが動いている想定
- `meilisearch  --master-key="your-master-key"`

その後、インデックス名`yuyu-serif`に以下のようなデータを入れています。（例：三上小又著『ゆゆ式』1巻10ページ1コマ目）

- koma_serif_id: 1-010-1-0
- koma_id: 1-010-1
- serif_id: 0
- serif: 今日の体育つかれたーもう帰っていーかなー?
- serif_chara: 縁
- kanji: 1
- img_path: /Users/hoge/image/yuyushiki01/1-010-1.jpg
- hiragana:  きょうのたいいくつかれたーもうかえっていーかなー?
- koma_image_url: https://bucket-name.s3.ap-northeast-1.amazonaws.com/yuyushiki01/1-010-1.jpg

お手持ちのデータに合わせて適宜変更してください。

# serve, build
serve
- ローカル環境： `yarn serve-dev`
- 本番用の設定をサーブ: `yarn serve-prod`

build
- 本番用の設定をビルド: `yarn build-prod`

