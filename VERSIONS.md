# バージョン履歴

`index.html`(本番配信ファイル)は常に**最新Vol**のコピー。過去の各Volのスナップショットは`versions/`フォルダに保存し、いつでも見比べられるようにしている。

| Vol | 日付 | 内容 | ファイル |
|---|---|---|---|
| 1.0 | 2026-07-11 | MVP初版。業界6種×面接段階3種の面接練習フロー、5観点添削レポート | [versions/Vol1.0_mvp.html](versions/Vol1.0_mvp.html) |
| 2.0 | 2026-07-12 | UI全面刷新: Appleミニマル白基調＋壁打ち復習ノート・共有機能 | [versions/Vol2.0_apple-ui-redesign.html](versions/Vol2.0_apple-ui-redesign.html) |
| 3.0 | 2026-07-13 | ホームを製品ヒーロー構成に刷新（写真ヒーロー＋事実コピー）、ランディング/セットアップの2段フロー分離 | [versions/Vol3.0_hero-home.html](versions/Vol3.0_hero-home.html) |
| 4.0 | 2026-07-13 | 企業データ大拡張: 11社→57社、業界6→11 | [versions/Vol4.0_company-data-expansion.html](versions/Vol4.0_company-data-expansion.html) |
| 5.0 | 2026-07-13 | 合言葉パスワードゲート追加（友人限定アクセス）、画面遷移アニメーション | [versions/Vol5.0_password-gate.html](versions/Vol5.0_password-gate.html) |
| 6.0 | 2026-07-14 | 3層質問生成システム（実出題→推定出題→業界フォールバック）実装、企業データ109社に拡張 | [versions/Vol6.0_three-tier-questions.html](versions/Vol6.0_three-tier-questions.html) |
| 7.0 | 2026-07-14 | 面接フィードバックレポート改善: スコア説明力バグ修正／`DEEP_TYPES`拡張／メーターの参考表示／自由質問欄のtextarea化／コーチ返答分岐拡張 | [versions/Vol7.0_feedback-report-improvements.html](versions/Vol7.0_feedback-report-improvements.html) |
| 8.0 | 2026-07-14 | 添削レポートの根拠強化: 「あなたの文章」原文引用トグル／文ごとの評価タグ／質問タイプ別の分量基準／長さと構成のトレードオフ／主体性判定の柔軟化／繰り返し語の減点＋具体表現の加点／単位つき数字の厳格検出 | [versions/Vol8.0_evidence-based-feedback.html](versions/Vol8.0_evidence-based-feedback.html) |
| **9.0** | 2026-07-17 | 知識ベース統合: 就活データPDF9本を`knowledge/`に収録し、NG定番表現辞書／抽象強み語の言い換え提案／STAR4要素の抜け検出／弱み回答の改善行動セット評価を添削エンジンに追加。頻出質問50選から13問を段階別プールに拡充 | [versions/Vol9.0_knowledge-base-integration.html](versions/Vol9.0_knowledge-base-integration.html) ＝現在の`index.html` |

## 運用ルール
- 作業は**このリポジトリの`index.html`を直接編集**する(セッション固有のscratchpadに依存しない。scratchpadは会話が終わると消えるため)。
- 意味のあるまとまり(バグ修正・機能追加など)が完了するごとに、`index.html`を`versions/VolX.Y_短い説明.html`としてコピー保存してからコミットする。
- 次の新しい作業は **Vol 10.0** から開始する。
