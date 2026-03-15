# 第5時：SQLの基礎（CREATE・INSERT・SELECT）

## 本時の目標

1. SQLのCREATE TABLE文でテーブルを作成し、データ型と制約を設定できる
2. INSERT INTO文でデータを挿入できる
3. SELECT文でWHERE・ORDER BY・LIMITを使ってデータを検索・絞り込みできる

## 取り扱う学習指導要領の内容

- エ-(イ) データベースの設計と活用
- エ-(ウ) プログラミング

## 準備物・教材

- 教師：SQL演習環境（SQLite on Colab、またはDB Browser for SQLite）
- 生徒：PC、Google Colab またはDB Browser

## 授業展開

| 時間 | 段階 | 学習活動 | 指導上の留意点 |
|---|---|---|---|
| 10分 | 導入 | 「SQLはデータベースに話しかける言語」というたとえで導入。WorldWide WebでのSQLの浸透度（多くのアプリがDBを使っている）を伝える | SQLが現実のシステム開発で必須であることを動機づけとして伝える |
| 30分 | 展開 | ①CREATE TABLE：booksテーブルを作成（isbn・title・author・year）（5分）②データ型（TEXT・INTEGER・REAL・DATE）と制約（NOT NULL・PRIMARY KEY・UNIQUE）を解説（5分）③INSERT INTO：練習データを5件挿入（5分）④SELECT：全件取得・WHERE絞り込み・ORDER BY並び替え・LIMIT件数制限（10分）⑤SQLクイズ：「2020年以降の本を著者名の昇順で3件取得せよ」（5分） | 構文エラーはメッセージを読む習慣をつけさせる。「SQLはタイポが多い」ことを伝え、丁寧に入力させる |
| 10分 | まとめ | 図書管理システムの全テーブルをCREATEするSQLを作成して保存。振り返りシートに記入 | 次時でUPDATE・DELETE・JOINを学ぶことを予告する |

## 板書・スライド構成

- スライド1：SQLとは（データベースに話しかける言語）
- スライド2：CREATE TABLE構文とデータ型・制約の一覧
- スライド3：INSERT INTOとSELECTの基本構文
- スライド4：WHERE・ORDER BY・LIMITの使い方（例付き）
- スライド5：今日のSQLクイズ

## 本時の評価

- 観点：知識・技能
- 評価方法：SQLクイズの正答
- 評価基準：WHERE・ORDER BY・LIMITを組み合わせた検索SQLを正確に記述できる

## 備考・メモ

<!-- 実施後の気づきなど -->
