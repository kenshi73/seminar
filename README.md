# 患者さん向けセミナー 告知ページ

GitHub Pages で公開する、患者さん向けセミナーの告知ページ集です。
セミナーを増やすときは、フォルダを1つ足して、一覧に1行足すだけです。

```
index.html          セミナー一覧（seminars.json から自動で並ぶ）
seminars.json       一覧に載せるセミナーの情報
assets/style.css    全ページ共通の見た目
_template/          新しいセミナー用のひな形
2027-gimap/         セミナー1回分のページ（フォルダ名がURLになる）
```

公開URL: `https://kenshi73.github.io/seminar/`
各回: `https://kenshi73.github.io/seminar/<フォルダ名>/`

## 新しいセミナーを足す

1. `_template` フォルダをコピーして、名前を `年-テーマ`（半角英数字とハイフン）にする。例: `2027-adrenal`
2. コピーした `index.html` の【　】を全部埋める。
3. `seminars.json` に1件足す。

```json
{
  "slug": "2027-adrenal",
  "title": "題名",
  "subtitle": "副題",
  "date": "2027-01-20",
  "dateLabel": "2027年1月20日（水）19:00〜20:00",
  "status": "draft"
}
```

`status` の意味:

| status | 一覧に出るか | 使うとき |
|---|---|---|
| `draft` | 出ない | 下書き。医師の確認前 |
| `open` | 「受付中」に出る | 公開して申込を受ける |
| `closed` | 「終了」に出る | 開催が終わった |

## 公開する前に必ず

- 【　】が残っていないか確かめる。
- 医師の確認を受ける（医療広告。効果の保証・体験談・比較優良の表現は書かない）。
- 各ページの `<meta name="robots" content="noindex,nofollow">` の行を消す。
- `seminars.json` の `status` を `open` にする。

`draft` でもページ自体はURLを知っていれば開けます。一覧に出ないだけです。

## 書いてはいけないこと

- 患者さんの名前や、個人が分かる話
- 「治る」「必ず良くなる」などの効果の保証
- 院内データの数字（載せるなら注記つきで医師が判断）

## GitHub Pages の設定（最初の1回だけ）

`Settings` → `Pages` → `Deploy from a branch` → `main` / `/(root)` で保存。
