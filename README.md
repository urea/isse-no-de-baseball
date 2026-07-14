# いっせーのーで野球

「いっせーのーで！」でカードを選び、CPUと同じ位置を選べばヒットになる、1人用のブラウザ野球ゲームです。

## 遊ぶ

GitHub Pages公開後は、次のURLで遊べます。

`https://<GitHubユーザー名>.github.io/<リポジトリ名>/`

## 遊び方

1. 対戦相手を選び、性格・選択傾向・セリフを確認する。
2. 場に出た3枚のヒットカードから1枚を選ぶ。
3. CPUと同じ位置ならヒット。カードの種類に応じて単打・二塁打・三塁打・本塁打になる。
4. 位置が違えばアウト。3アウトで攻守交代、3イニング後に得点の多い側が勝ち。

## 特徴

- Dewey、Fireball、Hoots、Rocky、Seedy、Stacky、BSOD、Null Signalの8人と対戦
- キャラクターごとのセリフと選択傾向が、読み合いのヒントになる
- 相手に勝つと、ブラウザのローカルストレージへ実績を保存。対戦相手選択画面に★が付く
- インストール不要。スマートフォン・PCのモダンブラウザで動作

## ローカルで遊ぶ

`index.html`を直接開くか、ローカルサーバーを起動します。

```powershell
cd <リポジトリをcloneしたフォルダ>
python -m http.server 4173 --bind 127.0.0.1
```

`http://127.0.0.1:4173/` をブラウザで開いてください。

## GitHub Pagesで公開する

このリポジトリはビルド不要の静的サイトです。GitHubへpushした後、リポジトリの **Settings → Pages** で次を指定します。

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/(root)`

保存後、GitHub Pagesが公開URLを表示します。`.nojekyll`を含めているため、Jekyllによる不要な処理は行われません。

## 構成

- `index.html` — ゲーム本体（React / Tailwind CDN）
- `assets/` — ゲームで表示する背景・キャラクター画像
- `docs/01_対戦キャラクター設定.md` — キャラクターの性格とセリフ設定

## データとプライバシー

勝利実績はブラウザ内のローカルストレージ（`isse-no-de-baseball.wins.v1`）にだけ保存されます。外部サーバーへ送信するデータはありません。

## ライセンス

ゲームのソースコードは [MIT License](LICENSE) です。画像アセットの扱いは [ASSET_NOTICES.md](ASSET_NOTICES.md) を参照してください。
