既存の単元に授業ファイルを1コマ追加する。

## 入力情報の受け取り方

引数（$ARGUMENTS）がある場合はそれを使う。なければユーザーに以下を確認する：
- 年度・科目（例：2026 / 情報Ⅰ）
- 単元番号・単元名（例：01 / 情報社会と情報モラル）
- 授業番号・授業タイトル（例：03 / 著作権と情報モラル）
- 授業の内容・概要

## 作業手順

1. 以下のコマンドで作業ブランチを作成・切り替える：
   ```bash
   git checkout -b add/YYYY-informaX-NN-lessonMM
   ```
2. `docs/_template/授業/授業.md` を読み込む
3. 以下のファイルを作成する：
   - `docs/YYYY/informaX/NN_単元名/授業/MM_タイトル.md`
4. `docs/YYYY/informaX/NN_単元名/01_単元計画.md` を Read し、授業構成テーブルの該当行にリンクを追加する：
   ```markdown
   | MM | [タイトル](授業/MM_タイトル.md) | ... |
   ```
5. 作成・更新内容を報告してレビューを促す
6. ユーザーがレビューOKを出したら GitHub にプッシュする

## 授業ファイルの生成ルール

`docs/_template/授業/授業.md` をベースに以下を埋める：
- 「本時の目標」は単元目標と授業内容に即して具体的に記述
- 「授業展開」は導入・展開・まとめの時間配分と学習活動を具体的に記述（50分想定）
- 「板書・スライド構成」は授業の流れに沿った構成を提案
- 「本時の評価」は単元の評価基準と対応する観点・方法を記述
- 「準備物・教材」は授業内容に合わせて具体的に記述

授業内容を生成する前に `docs/YYYY/informaX/NN_単元名/01_単元計画.md` を Read し、単元目標・評価基準との整合性を確認する。

## 完了後・GitHub へのプッシュ

1. 作成したファイルのパスと更新箇所を報告し、内容のレビューを促す
2. ユーザーが「OK」「問題ない」などレビュー完了を伝えたら、以下を実行する：
   ```bash
   git add docs/（該当パス）/
   git commit -m "Add lesson: MM_タイトル（YYYY 情報X NN_単元名）"
   git push origin add/YYYY-informaX-NN-lessonMM
   ```
3. プッシュ後、main へのマージを案内する：
   ```bash
   git checkout main
   git merge add/YYYY-informaX-NN-lessonMM
   git push origin main
   git branch -d add/YYYY-informaX-NN-lessonMM
   ```
4. マージ完了後、GitHub Pages のデプロイが自動で走ることを伝える（`.github/workflows/deploy.yml` による）
