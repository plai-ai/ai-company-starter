# AI社員の会社テンプレート — ai-company-starter

**コマンドを実行するだけで、AI社員つきの「会社」があなたのパソコンに立ち上がります。**

これは、YouTube動画「Claude CodeでAI社員チームを使って会社経営する方法」の特典テンプレートです。
動画と同じ手順で進めれば、CEO＋6人のAI社員がいる「1人会社」の土台がそのまま手に入ります。

---

## これは何？

- Claude Code で動く「AI社員の会社」の土台です
- 中身は **ただのフォルダとテキストファイル** 。特別なアプリは入っていません
- 社長AI（CEO）に話しかけるだけで、CEOが適切なAI社員に仕事を振り、成果物が `output/` に貯まっていきます

```
ai-company-starter/
├── CLAUDE.md                    ← 会社の動かし方（Claude Codeが最初に読む）
├── .claude/commands/            ← コマンド（/kickoff・/staff・/shigoto）
├── knowledge/
│   └── company-profile.md       ← 会社のナレッジ（事業内容・ターゲット。最初の会話でCEOが埋めます）
└── departments/                 ← 部署とAI社員（1人＝1フォルダ）
    ├── ceo/                     ← 社長AI（あなたの右腕）
    ├── marketing/
    │   ├── sns-marketer/        ← 集客担当（SNS投稿）
    │   ├── lp-designer/         ← LP担当（販売ページ・登録ページ）
    │   └── content-creator/     ← コンテンツ担当（記事・台本）
    ├── education/
    │   └── step-message-writer/ ← 教育担当（ステップ配信）
    ├── product/
    │   └── product-builder/     ← 商品担当（講座・資料の中身）
    └── sales/
        └── sales-writer/        ← 販売担当（案内文・セールス文）
```

**AI社員1人のフォルダは、いつも同じ3つでできています。**

```
sns-marketer/
├── skills/      ← スキル（仕事の定義）  : 指示書 SKILL.md
├── knowledge/   ← ナレッジ（判断基準）  : quality-bar.md（合格ライン）・feedback.md（直しの台帳）
└── output/      ← アウトプット（正解例）: 作った成果物。合格したものが次の見本になる
```

ビジネスの5つの部品 —— **集客 → LP・コンテンツ → 教育 → 商品 → 販売** —— それぞれに担当AI社員がいます。

---

## 必要なもの

- Claude のアカウント（Claude Code を使うため。Pro プラン以上を推奨）
- Mac または Windows のパソコン
- （任意）[Obsidian](https://obsidian.md/) — 会社の中身をきれいに見るためのメモアプリ。無料

---

## 手順（動画と同じ流れです）

### Step 1. Claude Code を入れる

すでに入っている方は Step 2 へ。

**Mac**: 「ターミナル」を開いて、次の1行を貼り付けて Enter

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows**: 「PowerShell」を開いて、次の1行を貼り付けて Enter

```powershell
irm https://claude.ai/install.ps1 | iex
```

入ったか確認:

```bash
claude --version
```

> うまくいかない場合は公式ドキュメント: https://docs.anthropic.com/ja/docs/claude-code/setup

### Step 2. この会社をダウンロードする

ターミナル（PowerShell）で、次の1行を実行:

```bash
git clone https://github.com/plai-ai/ai-company-starter.git
```

> `git` が無いと言われたら: このページ上部の緑の「**Code**」ボタン →「**Download ZIP**」→ 解凍でもOKです。

### Step 3.（任意）Obsidian で開く

1. Obsidian を起動 → 「**保管庫としてフォルダーを開く**（Open folder as vault）」
2. さきほどの `ai-company-starter` フォルダを選ぶ

これで会社の中身（組織図・各社員の skills / knowledge / output）が見やすくなります。やらなくても動きます。

### Step 4. 会社を起動する

ターミナルで:

```bash
cd ai-company-starter
claude
```

Claude Code が立ち上がったら、次のコマンドを打つだけです:

```
/kickoff
```

社長AI（CEO）が事業内容を1問ずつ聞いてくれるので、答えていくだけで会社ができあがります。
（事業内容が決まっていれば `/kickoff パーソナルジムの集客支援` のように続けて書いてもOK。まだ決まっていなくても、CEOが候補を出しながら一緒に決めてくれます）

### Step 5. AI社員に仕事を頼む

使えるコマンドは3つだけです。

| コマンド | 何が起きるか |
|---|---|
| `/kickoff` | 会社を立ち上げる（事業内容を決めて全AI社員に共有） |
| `/staff` | AI社員7人と、それぞれに頼めることを一覧で見る |
| `/shigoto <依頼>` | 担当AI社員が自動で選ばれて仕事をする |

例:

```
/shigoto SNS投稿を10本作って
```

```
/shigoto 商品のLPを作って
```

```
/shigoto LINEのステップ配信を5通作って
```

```
/shigoto 講座の目次と中身を作って
```

コマンドを使わず、ふつうに「SNS投稿を10本作って」と話しかけても同じように動きます。

成果物は、担当したAI社員の `output/` フォルダ（例: `departments/marketing/sns-marketer/output/`）に貯まっていきます。

---

## この先の話（大事）

このテンプレートでできるのは、あくまで **会社の「土台」** です。

そのまま出てくる成果物は、正直まだ「AIっぽさ」が残ります。実戦で使えるレベルにするには、この土台の上に **3つのフォルダの厚み** —— スキル（指示書の磨き込み）・ナレッジ（自分の会社のルール・フィードバックの蓄積）・アウトプット（合格した正解例）—— を足していく必要があります。各社員の `knowledge/feedback.md` に経営者の直しを1行ずつ足していくのが、その第一歩です。

その磨き方は、YouTubeで実際の経営の現場から発信していきます。

---

## 注意

- AI社員の成果物は、**必ず自分の目でチェックしてから**使ってください（数字・固有名詞・表現はとくに）
- このテンプレートに個人情報・機密情報を入れた場合の管理は自己責任でお願いします

## ライセンス

MIT License — 自由に使ってください（再配布時は著作権表示を残してください）
