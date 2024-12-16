---
noteId: "4f5e2fa2bb5d11ef9afcbdf112268252"
tags: []

---

# データベース演習問題
この演習では、これまで学んだJavaとDBの基礎知識を活用したプログラムを作成する。

作成するのは原始的なデータベース利用方法であるJDBCを用いたデータベース利用プログラムである。

<br>

# 実習の準備
## ベースとなるプロジェクトの準備
* Git Bash でクローンするために、ディレクトリを作成して移動する（cd を使って、カレントディレクトリにする）
* `Prmn2024Fall`のリモートリポジトリを以下のようにクローンする
```
$ git clone https://github.com/Sgfrd24-35/Prmn2024Fall.git
```
* IntelliJ IDEAを起動する
* `Prmn2024Fall`の`Documents`から`db_prac`のpom.xmlをIntelliJで開く（プロジェクトとして開く）

<br>

## データベースの初期登録
* [データベースの基本的な設定](../DB/DB_基本設定.md) を見てデータベースを作成する

<br>


# 物理データモデルの実行


## 学生情報テーブルを追加
* Databaseウィンドウに登録されている`db_prac`で右クリックし、 コンソール（デフォルト） を選ぶ
* 開かれたコンソールに、以下のSQLを実行する

![学生情報テーブル](https://github.com/b2211700/prmn2023/assets/109058900/b094f89f-9e78-4b8b-ae90-469471626693)

> もしうまくテーブルが作れなかった、間違ったテーブルが作成されてしまった、などの場合は`drop table`ステートメントを使うとよい
>
> ```
> -- 例）学生情報テーブルを削除したいとき
> drop table 学生情報;
> ```

<br>

## タプルの登録
* 以下のSQLを実行する

![学生情報タプル](https://github.com/b2211700/prmn2023/assets/109058900/283b4632-d188-4c6d-9d64-e89e39c52289)

<br>

### 演習1
以下のSQLを実行すると、どのような結果が表示されるか確認しよう

![演習1 selectAll](https://github.com/b2211700/prmn2023/assets/109058900/788a4057-de03-42ed-9d46-fe19afd10457)

<br>

ここまでできたらGitHubにcommit/pushをしてください

* IntelliJのターミナルを開く
* 以下のコマンドを入力する
> Windowsの場合は画面下側にあるターミナルを開き、ターミナル上部の右側にある”Ｖ”を押し、ターミナルを**Git Bash**に変更してからコマンドを1行ずつ実行してください
```
git add .
git commit -m "学生情報テーブルを作成した"
git push
```

# select(検索)ステートメントをJDBCで実行する
学生情報テーブルからある点数未満のデータを取り出すことを例に、JDBCを利用したプログラムを作成する

<br>

## 学生情報クラス（PreExam.java）
* `src` > `main` > `Java` > `jp.ac.chitose.db_prac` の中に、**PreExam**クラスを作成する
* これは、学生情報テーブルからの検索結果を格納するインスタンスを生成するためのクラスである

> もし「Git に次のファイルを追加しますか？」と言われたら`追加(A)`を選択してください

<br>

![PreExamクラス](https://github.com/b2211700/prmn2023/assets/109058900/280555ae-bebb-40bc-a5a8-f544362aee8c)

<br>

## データべースを利用するクラス（PreExamDAO.java）
* **PreExamDAO** クラスを作成する
* DAOは**Data Access Object**の略で、データベース（テーブル）への接続を担当するインスタンスを作るためのクラスである
* selectPreExams メソッドに基準となる点数を`lessThan`引数として渡すと、その点数未満のタプルを学生情報テーブルから検索するようにしたい

![PreExamDAOクラス完成版](https://github.com/b2211700/prmn2023/assets/109058900/43ca5af5-b6ea-47d3-a383-33c45fc35517)

<br>

### 演習2
* プログラムの中の空白の部分をこれまでのlectureを思い出しながら埋めよう
> ヒント1：入力した基準の点数をSQL文の中に組み込むにはプレースホルダーとして`?`を使う
> 
> ヒント2：SQLは8単語

<br>

## データべースを利用するクラス（SelectDemoクラス）
* **SelectDemo**クラスを作成する
* これはPreExamDAO をインスタンス化し、selectPreExamsメソッドを実行するものである
  
![SelectDemoクラス](https://github.com/b2211700/prmn2023/assets/109058900/b24b7295-6b11-4d15-af0d-3147faeb4265)

<br>

### 演習3
* ここまでのプログラムが完成したら**SelectDemo**クラスの main メソッドを実行する
* 不合格者の基準点を`90`点としたとき実行結果がどうなるか確認しよう
* 不合格者の基準点を`80`点としたとき実行結果がどう変わるか確認しよう

<br>

ここまでできたらGitHubにcommit/pushをしてください

* IntelliJのターミナルを開く
* 以下のコマンドを入力する
> Windowsの場合はローカルのタブの右側にある`∨`を押し、`Git Bush`を選択してからコマンドを入力してください

```
git add .
git commit -m "Selectクラスを作成した"
git push
```


# delete（削除）ステートメントをJDBCで実行する


## データべースを利用するクラス（PreExamDAO.java）
* 作成した**PreExamDAO**クラスに、**deletePreExam**メソッドを追加する
* deletePreExamメソッドに、データ削除の対象となる学生コードを引数として渡すと、その学生コードのタプルを学生情報テーブルから削除するようにしたい

![PreExamDAOクラスdeletePreExamメソッド完成版](https://github.com/b2211700/prmn2023/assets/109058900/d327645a-617e-4bfb-b68f-6c05a9291f62)

<br>

### 演習4
* プログラムの中の空白の部分をこれまでのlectureを思い出しながら埋めよう
> ヒント：SQLは7単語

<br>

## データべースを利用するクラス（DeleteDemoクラス）
* **DeleteDemo**クラスを作成する
* これはPreExamDAO をインスタンス化し、deletePreExamsメソッドを実行するものである

![DeleteDemoクラス](https://github.com/b2211700/prmn2023/assets/109058900/2be4ed4e-488b-4af3-8202-9ed750a46f0e)

<br>

### 演習5
* ここまでのプログラムが完成したら**DeleteDemo**クラスの main メソッドを実行する
* 中間テストの点数を削除する学生コードに`C012`を入力すると実行結果がどうなるか確認しよう
* 演習3のように、**SelectDemo**クラスのmainメソッドを実行し、不合格者の基準点に`90`を入力した時に、実行結果に表示される内容はどのように変化しているか確認しよう

<br>

ここまでできたらGitHubにcommit/pushをしてください

* IntelliJのターミナルを開く
* 以下のコマンドを入力する
> Windowsの場合はローカルのタブの右側にある`∨`を押し、`Git Bush`を選択してからコマンドを入力してください

```
git add .
git commit -m "Deleteクラスを作成した"
git push
```

# insert(追加)ステートメントをJDBCで実行する


## データべースを利用するクラス（PreExamDAO.java）
* 作成した**PreExamDAO**クラスに、**insertPreExam**メソッドを追加する
* insertPreExamメソッドに、学生コードと氏名、得点をそれぞれ`gakusekiCode`, `familyname`, `firstname`, `point`引数として渡すと、学生情報テーブルのタプルとして追加するようにしたい

![PreExamDAOクラスinsertPreExamメソッド完成版](https://github.com/b2211700/prmn2023/assets/109058900/8fb6823d-ee79-4c98-a028-80e0e761c42d)

<br>

### 演習6
* プログラムの中の空白の部分をこれまでのlectureを思い出しながら埋めよう
> ヒント：プレースホルダーを含んだタプルを書くときは`(?,?,?,?)`と書く

<br>

## データべースを利用するクラス（InsertDemoクラス）
* **InsertDemo**クラスを作成する
* これはPreExamDAO をインスタンス化し、insertPreExamsメソッドを実行するものである

![InsertDemoクラス](https://github.com/b2211700/prmn2023/assets/109058900/878bcfd7-9703-414b-9738-8d701097aa98)

<br>

### 演習7
* ここまでのプログラムが完成したら**InsertDemo**クラスの main メソッドを実行する
* 中間テストの点数を追加する学生コードに`C012`、氏名に`ニシヤマ`、`タケル`、得点に`85`を入力すると実行結果がどうなるか確認しよう
* 演習3のように、**SelectDemo**クラスのmainメソッドを実行し、不合格者の基準点に`90`を入力した時に、実行結果に学生が追加されていることを確認しよう

<br>

ここまでできたらGitHubにcommit/pushをしてください

* IntelliJのターミナルを開く
* 以下のコマンドを入力する
> Windowsの場合はローカルのタブの右側にある`∨`を押し、`Git Bush`を選択してからコマンドを入力してください

```
git add .
git commit -m "Insertクラスを作成した"
git push
```

データベース演習パートはここまでです。お疲れさまでした！

[目次](../README.md)へ



