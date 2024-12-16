---
noteId: "4f5e56b0bb5d11ef9afcbdf112268252"
tags: []

---

# git

## はじめに

- 分からないときはすぐに担当のb3に聞く
  - 分からないことは次に持ち越さないこと
- 予習/復習は必ず行うこと
  - 前回までの知識は全て習得しているものとして進行します
- **課題はGithub上にpushすること**
  - Githubの使い方を学びます
  - 課題の質問をするときなどにGithub上にあげておくと確認しやすいです
- 時間外の質問/相談はDiscordまたはZoomで  
  - Zoomで聞いた方がいいこともあります
- 解答は確認程度に
  - 課題の解答がありますが、あくまで参考程度としコピペは極力しない
- 連絡はこまめに
  - 既読通知機能がDiscordにはないので...
  - Discordで質問等するときはメンターをメンションして聞いてください

### Githubの準備
以下はGithubアカウントがあることを想定して進めます
- Windowsの人は[GitBashのダウンロード](https://gitforwindows.org/)
Macの人はターミナルで git config でユーザ登録を行なっていない人は以下のコマンドから登録する
```
$ cd
$ git config --global user.name [GitHubに登録したユーザ名]
$ git config --global user.email [GitHubに登録したメールアドレス]
```
現在の登録を確認するコマンド
```
$ git config --global --list
```

- [Github](https://github.co.jp/)にアクセスし、サインインする
- Github上にリモートリポジトリを作成する
  - 以下のボタンをクリック
  	![image](https://i.imgur.com/nF6O0bi.jpg)

 
 - 以下のように入力し、Create Repositoryをクリックする。ここまででリモートリポジトリは完成
  
	![image](https://i.imgur.com/u1ZeqBa.png)

  - リポジトリが作成されると以下のような画面が表示される。この画面のまま置いておく
  
	![image](https://user-images.githubusercontent.com/85465441/198196394-a332b98a-2c7a-4d8c-ac4d-f7792d9bb6b5.png)

- ローカルリポジトリの作成<br>
以下はWindowsの人はGitBash、Macの人はターミナルで操作する
  - リポジトリを作成するディレクトリを作成する
  
  【Mac例】 MacintoshHD>ユーザ>ユーザ名>デスクトップ にディレクトリを作成する場合
  ```
  $ cd
  $ cd Desktop
  $ mkdir Prmn2024Fall
  $ cd Prmn2024Fall
  ```
  
  【Windows例】 Windows(C:)>Users>ユーザ名 にディレクトリを作成する場合
  ```
  $ cd
  $ cd c:
  $ cd Users
  $ cd ユーザ名
  $ mkdir Prmn2024Fall
  $ cd Prmn2024Fall
  ```
  
  ※ 先にファイルを作成する方法もある
  
  ローカルリポジトリを作成したいところで新規ファイルを保存してパスのコピーを行い、cdコマンドの後ろにつける
  
【Windowsの場合】
> ![image](https://user-images.githubusercontent.com/85465441/198379464-4e54be20-1bec-4619-abbf-825b1b450152.png)

【Macの場合】
> ![image](https://user-images.githubusercontent.com/85465441/198379592-a4fcfaaa-351b-4e4e-b6f4-f5d12d8aed14.png)
	
  ```
  $ cd ファイルのパス
  ```
  
  
  

  - Githubの画面に戻り、表示されているコマンドを順番に進める
  
  ![image](https://user-images.githubusercontent.com/85465441/198198525-d11bcbef-9710-4d7d-a65b-f540c87aa9a5.png)
  【例】
  
  ```
  $ echo "# Prmn2024Fall" >> README.md
  $ git init
  $ git add README.md
  $ git commit -m "first commit"
  $ git branch -M main
  $ git remote add origin 各々のGitHubのリンク
  $ git push -u origin main
  ```
- Githubのリポジトリ上にREADE.mdというファイルが上がっていることを確認する

### プロジェクトの作成
- Githubにpushを行うローカルリポジトリを作成したディレクトリ下に ”prmn2024Fall” フォルダを作る
- IntelliJ IDEAを起動し、ファイル　→　新規　→　プロジェクトを選択する。


  
![image](https://i.imgur.com/HXNWYzO.png)


  
- 以下の画面になったら、「Spring Initializer」を選択し、

    - 名前:prmn2024Fall
  
    - 場所：各自の”prmn2024Fall”フォルダのパス

    - 言語:Java

    - 型:Maven

    - JDK:temurin-17

    - version:17

と設定し、「次へ」を押す。


  
![image](https://i.imgur.com/ajQYzge.png)



  
- 以下の画面になったら、「SQL」を選択し、

    - JDBC API

    - H2 DataBase

にチェックを入れ、「作成」を押す。



  
![image](https://i.imgur.com/XcbZot0.png)


### pom.xmlをプロジェクトに反映させる

- pom.xmlファイルを開く
- エディタ上で右クリックし、Maven > プロジェクトの再ロード を選択




### パッケージの作成

- 左側のメニューの “prmn2024Fall” を開く
- ”src” → ”main” → ”java”フォルダを押し、”java”フォルダを右クリックし、New > Packageを選択
- package nameには、”lecture01”と記入しOKを押す

今後特に指示が無い場合は ”lectureXX” の形式で作成する。

例: 第3回講義では、 prmn2024Fall/lecture03/

![image](https://user-images.githubusercontent.com/85465441/198200330-18ced012-4f97-4718-b2b9-4b20a36f1e9a.png)

### Githubにプロジェクトをpushする

- IntelliJのターミナルを開く

![image](https://user-images.githubusercontent.com/85465441/198525531-5e61a929-75da-40c4-bdc8-24b7b7523d0d.png)

- 現在いる場所がプロジェクトになっていることを確認する

![image](https://user-images.githubusercontent.com/85465441/198528268-70986441-812b-4a24-b6f6-f5d30be65c8e.png)

- 以下のコマンドを入力する
※ Windowsの場合は画面下側にあるターミナルを開き、ターミナル上部の右側にある”Ｖ”を押し、ターミナルを**Git Bash**に変更してからコマンドを1行ずつ実行してください
```
$ git add .
$ git commit -m "Github上に表示するコメント文(例:プロジェクト作成)"
$ git push origin main
```


Githubのリポジトリを更新して、プロジェクトがpush出来ていたらOK

GitBashやターミナルでも同じコマンドでpushを行えるが、--ディレクトリをプロジェクトまで移動するのを忘れないように--
pushはできるだけ細かく行い、コメント文は簡潔に([パッケージ](https://github.com/fujiitomoko/ProjectMember2022Document/edit/main/Lecture/Lecture1.md#パッケージ)・[クラス](https://github.com/fujiitomoko/ProjectMember2022Document/edit/main/Lecture/Lecture1.md#クラス)・[メソッド](https://github.com/fujiitomoko/ProjectMember2022Document/edit/main/Lecture/Lecture1.md#メソッド)を作ったときなど)



### クラスの作成

- 左側のメニューのsrc > lecture01を 右クリックする
- New > Java Class を選択する
- Nameには "Main" と記入しOKを押す（ファイルを追加するか聞かれた場合には追加する）

今後クラス作成をするときは、各lectureXXパッケージ内に作成すること

![image](https://user-images.githubusercontent.com/85465441/197342085-f66a8e15-0e1c-4740-9587-8f7ab9c17a33.png)

## 何もしないプログラム

- Mainクラスの {} の中にカーソルを合わせる
- `psvm` とタイプしTabキーを押す
  - 生成されたコード部分
  ```
  public static void main (String[] args){
	  //本来ならここに処理を書く
	  //スラッシュを2つ打つと、コメント文として認識される。
	  //コードの可読性の向上につながるので、書く癖をつけよう
	  //行を選択して「ctrl+/ (command+/)」で選択行をコメント文に変更できる(複数行可)
  }
  ```
  をmainメソッドと呼ぶ。

- コード入力スペース上で右クリックをする
- Run ‘Main.main()’ をクリック

画面下部に `Process finished with exit code 0` と表示されることを確認する


## gitの操作方法
- 以下のリンクからgitの操作について学習してください。

[gitの操作方法 基本編](https://github.com/Sgfrd24-35/Prmn2024Fall/blob/main/git/Documents/git%E3%81%AE%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E6%93%8D%E4%BD%9C.pdf)


[gitの操作方法 練習編(ローカルリポジトリ)](https://github.com/Sgfrd24-35/Prmn2024Fall/blob/main/git/Documents/git%E3%81%AE%E6%93%8D%E4%BD%9C%E6%96%B9%E6%B3%95%20%E7%B7%B4%E7%BF%92%E7%B7%A8(%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA).pdf)


[gitの操作方法 練習編(リモートリポジトリ)](https://github.com/Sgfrd24-35/Prmn2024Fall/blob/main/git/Documents/git%E3%81%AE%E6%93%8D%E4%BD%9C%E6%96%B9%E6%B3%95%20%E7%B7%B4%E7%BF%92%E7%B7%A8(%E3%83%AA%E3%83%A2%E3%83%BC%E3%83%88%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA).pdf)



gitのパートはここまでになります。お疲れさまでした！

[目次へ](../README.md)

