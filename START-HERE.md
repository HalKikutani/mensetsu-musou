# START HERE — 面接無双 再開ガイド

新しいセッション/セクションでこのプロジェクトを再開するとき、**まずこのファイルを読めば現在地がわかる**ようにしたもの。

---

## いまどこ？（2026-07-14 時点）

- **最新版: Vol 8.0「添削レポートの根拠強化」— 完成・本番反映済み**
- 本番URL: https://halkikutani.github.io/mensetsu-musou/ （GitHub Pages、`index.html`をそのまま配信）
- Artifact（Claude上の確認用、同一URLで毎回更新）: https://claude.ai/code/artifact/2fb47276-8ff3-4708-9499-047e0de820a6
- リポジトリ: https://github.com/HalKikutani/mensetsu-musou 、ローカルは `~/Projects/mensetsu-musou`
- 最新コミット: `fb69d32 Vol 8.0: 添削レポートの根拠を強化`（push済み・作業ツリーはクリーン）
- パスワードゲート: "Micheal Jackson"（Michael可、大文字空白ゆらぎOK）

## ファイルの場所（一目で把握）

```
~/Projects/mensetsu-musou/
├── index.html        ← アプリ本体。常に最新Vol（今はVol 8.0）のコピー。これを直接編集する
├── versions/         ← 各フェーズの完成版スナップショット（Vol1.0〜Vol8.0）
├── VERSIONS.md       ← どのVolで何をやったかの一覧表
├── START-HERE.md     ← このファイル（再開ガイド）
├── CLAUDE.md         ← 開発メモ。各Volの詳細な仕様・実装内容・決定事項
└── README.md         ← ユーザー向け概要・クレジット
```

各Volの中身は [VERSIONS.md](VERSIONS.md) を、Vol 8.0の詳しい実装内容は [CLAUDE.md](CLAUDE.md) の「Vol 8.0」セクションを見る。

## 再開のしかた（次にやる新規作業＝Vol 9.0）

1. このファイルと [VERSIONS.md](VERSIONS.md)・[CLAUDE.md](CLAUDE.md) を読む
2. `~/Projects/mensetsu-musou/index.html` を**直接編集**する（scratchpadは使わない＝会話終了で消えるため）
3. 区切りがついたら：構文チェック → ブラウザ実機検証 → `versions/Vol9.0_短い説明.html` へコピー → commit → push → 本番確認
4. Artifactを更新するときは index.html の内容を scratchpad にコピーしてから、Artifactツールに `url: https://claude.ai/code/artifact/2fb47276-8ff3-4708-9499-047e0de820a6` を渡して同じURLへ再公開

### 動作確認コマンド
```bash
# ローカルプレビュー
python3 -m http.server 8642 --directory ~/Projects/mensetsu-musou
# → http://localhost:8642/index.html

# JS構文チェック
cd ~/Projects/mensetsu-musou && python3 -c "
import re
h = open('index.html', encoding='utf-8').read()
scripts = re.findall(r'<script>(.*?)</script>', h, re.S)
open('/tmp/_main_script.js','w',encoding='utf-8').write(max(scripts, key=len))
" && node --check /tmp/_main_script.js
```

## 運用ルール（Halの希望）
- 5時間の利用上限を避けたい → 大きいファイルはgrepで行特定してから小さくRead、ブラウザ検証など重い作業はサブエージェントに委譲、区切りごとにcommit/push。
- どのフェーズを作っているか常に **Vol 番号**（Vol 9.0…）で管理し、`versions/` にスナップショットを残す。
- 実装作業（特に大きな改修）は Fable 5 モデルのエージェントに委譲する運用でも可。
