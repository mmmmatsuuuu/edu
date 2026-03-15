ユーザーから提供された「年度・科目・単元構成」の情報をもとに、科目ディレクトリと計画ファイルを作成する。

## 入力情報の受け取り方

引数（$ARGUMENTS）がある場合はそれを使う。なければユーザーに以下を確認する：
- 年度（例：2026）
- 科目（情報Ⅰ / 情報Ⅱ）
- 単元一覧（単元名と授業時数）

## 作業手順

1. `docs/_template/01_年間計画.md`・`docs/_template/02_評価まとめ.md`・`docs/_template/03_振り返り.md` を読み込む
2. 以下のディレクトリ・ファイルを作成する：
   - `docs/YYYY/informaX/01_年間計画.md`
   - `docs/YYYY/informaX/02_評価まとめ.md`
   - `docs/YYYY/informaX/03_振り返り.md`
3. `mkdocs.yml` を更新する
4. 作成内容を報告してレビューを促す
5. ユーザーがレビューOKを出したら GitHub にプッシュする

## 各ファイルの生成ルール

### 年間計画.md
テンプレートをベースに以下を埋める：
- 科目名・年度をタイトルに反映
- 「科目の目標」「目指す生徒像」は学習指導要領に基づき、高校情報科として適切な内容をAIが提案する
- 「科目の評価基準」は観点別（知識・技能／思考・判断・表現／主体的に学習に取り組む態度）で具体的に記述
- 「評価方法」の割合は一般的な比率を提案する
- 「年間単元一覧」は提供された単元名・時数を表に整理する

### 02_評価まとめ.md・03_振り返り.md
テンプレートをベースに科目名・年度を埋め、それ以外は空欄のままにする。

## docs/index.md の更新

`docs/index.md` を Read してから Edit で科目へのリンクを追加する。

年度ベースの場合は `## 年度一覧` セクションに追加：
```markdown
- [YYYY年度 情報X](YYYY/informaX/01_年間計画.md)
```

`docs/pbp/` など年度によらない場合は `## PBP（プロジェクトベース）` セクションを作成して追加：
```markdown
## PBP（プロジェクトベース）

- [PBP 情報X](pbp/informaX/01_年間計画.md)
```

該当セクションがなければ新規に作成する。

## mkdocs.yml の更新

`mkdocs.yml` を Read してから Edit で nav セクションに科目エントリを追加する。

年度ベース（`docs/YYYY/`）の場合、`YYYY年度` セクション配下に追加：
```yaml
- YYYY年度:
  - 情報X:
    - 年間計画: YYYY/informaX/01_年間計画.md
    - 評価まとめ: YYYY/informaX/02_評価まとめ.md
    - 振り返り: YYYY/informaX/03_振り返り.md
```

`docs/pbp/` など年度によらないディレクトリの場合、対応するセクション配下に追加：
```yaml
- PBP（プロジェクトベース）:
  - 情報X:
    - 年間計画: pbp/informaX/01_年間計画.md
    - 評価まとめ: pbp/informaX/02_評価まとめ.md
    - 振り返り: pbp/informaX/03_振り返り.md
```

該当セクションが存在しない場合は新規に作成する。

## 完了後・GitHub へのプッシュ

1. 作成したファイルの一覧とパスを報告し、内容のレビューを促す
2. ユーザーが「OK」「問題ない」などレビュー完了を伝えたら、以下を実行する：
   ```bash
   git add docs/（該当パス）/ docs/index.md mkdocs.yml
   git commit -m "Add subject plan: YYYY 情報X"
   git push origin main
   ```
3. プッシュ完了後、GitHub Pages のデプロイが自動で走ることを伝える（`.github/workflows/deploy.yml` による）
