---
description: 仕事を依頼する（担当AI社員を自動で選んで実行・その社員の output/ に保存）
---

経営者からの依頼: $ARGUMENTS

社長AI（CEO）として、`departments/ceo/skills/01-company-operations/SKILL.md` の「依頼を受けたら」の手順で処理してください。

1. 依頼を1文に要約して復唱する
2. `CLAUDE.md` の組織図から担当AI社員を選び、その社員の `skills/*/SKILL.md`（仕事の定義）と `knowledge/quality-bar.md`・`knowledge/feedback.md`（判断基準）を読んで **その社員になりきって** 実行する
3. `knowledge/company-profile.md` の事業内容・ターゲット・トーンを必ず反映する
4. 成果物をその社員の `output/YYYY-MM-DD_<テーマ>.md` にファイル保存する（チャットに書くだけで終わらせない）
5. `quality-bar.md` のチェックを通してから、ファイルの場所・要約3行・次の一手1つを報告する
