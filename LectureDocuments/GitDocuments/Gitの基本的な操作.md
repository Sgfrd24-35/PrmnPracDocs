# gitの基本的な操作

## 目次
1. Git と Git Hub について
2. Git と Git Hub のインストール方法について
   1. Git 導入方法について
3. Git 操作について
   1. Git 操作の流れについて
   2. ローカルでの操作について
   3. リモートでの操作について
   4. ブランチの操作について
4. 参考資料

# 1. Git と Git Hub について

複数人でプロジェクトを管理するにあたり、便利なものがあります。
それが、Git と Git Hub です。
これらは、プロジェクトを時系列的に木構造でプロジェクトを管理できるようにします。
詳しくは、次以降で述べます。

## **Git** とは？
**Git**（ギット）は、分散型バージョン管理システムです。

### **特徴**
- **バージョン管理**  
  ソースコードやファイルの変更履歴を記録し、いつでも過去のバージョンに戻せる仕組みです。
- **分散型**  
  リポジトリ（コードや変更履歴を保存する場所）を複数のコンピュータに分散して管理できます。
- **ローカル操作**  
  ネットワークに接続しなくても、ローカルでほとんどの操作が可能です。
- **軽量**  
  差分管理が効率的に行われ、変更履歴のデータサイズが小さく保たれます。

### **よく使うGitの用語**
- **リポジトリ**：ファイルとその変更履歴を保存する場所。
- **コミット（commit）**：変更内容をリポジトリに保存する操作。
- **ブランチ（branch）**：メインの開発から分岐して作業する独立した領域。
- **マージ（merge）**：ブランチで行った変更を統合する操作。
- **プッシュ（push）**：ローカルの変更をリモートリポジトリに送る操作。
- **プル（pull）**：リモートリポジトリの変更をローカルに取り込む操作。
- **クローン（clone）**：リモートリポジトリをローカルにコピーする操作。

## **GitHub** とは？
**GitHub**（ギットハブ）は、Gitリポジトリをホスティング（保存・共有）するためのWebサービスです。

### **特徴**
- **リモートリポジトリのホスト**  
  Gitで管理しているプロジェクトをインターネット上で保存し、共有できます。
- **コラボレーション**  
  チームでの共同開発が容易になります。変更の提案やレビューを行う機能があります。
- **公開・非公開リポジトリ**  
  プロジェクトを公開してオープンソース化したり、非公開で開発することもできます。
- **Pull Request（プルリクエスト）**  
  変更内容を提案して、他の開発者にレビューしてもらう仕組みです。
- **Issue（イシュー）**  
  タスクやバグ、要望などを管理する機能です。
- **CI/CD機能**  
  GitHub Actionsを使って、コードのテストやデプロイの自動化を設定できます。


## **Git と Git Hub を使用する簡単な流れ**  
1. **Git**を使ってローカルでファイルの変更履歴を管理。  
2. **GitHub**にリモートリポジトリを作成して、変更内容をプッシュ。  
3. チームメンバーはリモートリポジトリから変更をプルし、共同で開発。


Gitはバージョン管理のためのシステムであり、GitHubはそれを共有・管理するためのオンラインプラットフォームです。
両方を組み合わせることで、効率的なソフトウェア開発が可能になります！


# 2. Git と Git Hub のインストール方法

## Git Hub の準備

1. GitHubのサインアップ
[こちら](https://github.co.jp/) のページからサインアップしてください。
登録したemailとusernameはこれからずっと使うことになるので、慎重に登録してください。
（後から変更できます。忘れないようにしましょう。）
usernameはハンドルネームで別にいいと思います。


2. Git Hub へのサインイン
[こちら](https://github.com/)にアクセスし、"New"というボタンを押します。
![image](../../LectureImages/GitImages/git_hub_new_repo_1_image.png)

3. リポジトリの作成
Repository nameに「PrmnPrac20XX」とだけ書いて、ボタン「Create repository」を押してください。
（Repository nameは任意です。年度に合わせて、XXの部分を変えてください。また、設定いろいろ知っている方は自由に設定をいじってください。）
![image](../../LectureImages/GitImages/git_hub_new_repo_2_image.png)


以下のようなページに遷移するでしょうか。
![image](../../LectureImages/GitImages/git_hub_new_repo_3_image.png)

「…or create a new repository on the command line」にある Git コマンドをこの後打っていくことになります。  
今はこのまま置いときましょう。

## Git の準備

以下は、[こちら](https://scrapbox.io/Prmn2023/Git%E5%B0%8E%E5%85%A5) の記事を参考に再編したものです。
必要であれば、適宜参考にしてください。

1. Git インストールに必要な環境構築

Windowsの方は[こちら](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=ja-jp&gl=jp&icid=CNavAppsWindowsApps) の Microsoft Store のページから ** Windows Terminal ** をインストールしてください。
Windows Terminal のタブ上には「+」と「v」があります。「v」を押して使いたいTermianlを選択しましょう。

Macの方はこちら[Progateの記事](https://bit.ly/42wU6Ke) を参考にしていただければと思いますが、Terminal は標準でインストールされているようです。

プロメン活動にはあまり関係ない、その他の環境構築に関しては、以下の Qiita 記事がかなり参考になると思います。
- [Windowsの方](https://qiita.com/Bana7/items/0441324bb490ff657c38#windows-terminal)
- [Macの方](https://qiita.com/Bana7/items/cc0340fb4c322fe408ed)

2. Git のインストール

[WindowsにGitをインストールする手順(2023年05月更新)](https://www.curict.com/item/60/60bfe0e.html) を中心に進めます。

   1. [記事](https://www.curict.com/item/60/60bfe0e.html) に従って [Git for Windows](https://gitforwindows.org/) をダウンロードしてください。ここは省略します。

   2.  ダウンロードしたexeを実行してください。
   3.  ライセンス確認
   そのままGO！
   [https://scrapbox.io/files/64633888bfd1ae001bce5ea5.png]
   4. インストール先を選択
   デフォルトのまま。
   [https://scrapbox.io/files/646338bb837321001ba42210.png]
   5. インストールコンポーネントの選択
   一番物議をかもした箇所です。
   [https://scrapbox.io/files/646338eff925f9001c036513.png]
   ＜おそらくデフォルトとは変わった場所＞
   -  [* <Additonal icons> ]( [* <On the Desktop>]) はデフォルトではチェック入っていなかったと思いますが、デスクトップにGitのショートカットとアイコンを追加したい方はチェック入れてください。（使いやすさを考えると、入れたほうがいい？）
   -  [* <Windows Explorer integration>] はチェック非推奨とします。使いどころがよく分かっていない。
   -  [* <(NEW!) Add a Git Bash Profile to Windows Terminal>]  は、Windows Terminal をインストールした方は入れていただいてもいいと思います。使いやすくなるはずです。
   6. スタートメニューへの登録
   デフォルトのまま。
   [https://scrapbox.io/files/64633b4dd7f6a8001bd3c001.png]
   7. エディタの設定
   デフォルトのまま。
   [https://scrapbox.io/files/64633ba1c0476d001b955243.png]
   - Visual Studio Code（[こちら https://bit.ly/456rZDX]の記事など参考になります）を使っている方であっても、デフォルトのままでいいと思います。
   8. 新規リポジトリのデフォルトブランチ名の設定
   デフォルトのまま。
   [https://scrapbox.io/files/64633c375324e9001b217a27.png]
   9. 環境変数の設定
   デフォルトのまま。
   [https://scrapbox.io/files/64633c67c107c8001ca71189.png]
   10. SSLライブラリの選択
   デフォルトのまま。
   [https://scrapbox.io/files/64633cc57f35a5001bed5554.png]
   11. HTTPSライブラリの選択
   デフォルトのまま。
   [https://scrapbox.io/files/64633d100309ad001c1e52a8.png]
   12. 改行コードの取り扱いを選択
   迷いどころだが、デフォルトのまま。
   [https://scrapbox.io/files/64633d5b837321001ba4a123.png]
   13. Git Bashで利用するターミナルを選択
   結構迷いどころ。Windowsなので下を選択してみた（問題なく使えています）が、デフォルト通り上を選択したほうがいい気もする。
   [https://scrapbox.io/files/64633e115324e9001b21a214.png]
   14. git pullの設定
   デフォルトのまま。
   [https://scrapbox.io/files/64633ecb68ccea001bde6226.png]
   15. 認証情報ヘルパーの設定
   デフォルトのまま。
   [https://scrapbox.io/files/64633f59de5fd5001b29200f.png]
   16. 追加オプションの設定
   デフォルトのまま。
   [https://scrapbox.io/files/64633fe2f35673001c4dbe27.png]
   17. 試験運用中のオプションの設定
   デフォルトのまま。
   [https://scrapbox.io/files/64633ffd1c863f001b7c8d84.png]
   18. インストールの実行
   では、実行しましょう！
   [https://scrapbox.io/files/64634020ce20c7001b7c2fdc.png]
   - インストールコンポーネントの選択画面([Gitインストール#64633721e3c99c0000af191f])で[* <Additonal icons>] にチェックを入れた方は、以下のようなGitBashアイコンがデスクトップ上に表示されたのではないでしょうか。
   [https://scrapbox.io/files/646340be98b211001b8b616d.png]


3.  ここまできたら、動作確認してみましょう！
    1.  以下のコマンドを GitBash や Terminal で入力して、Gitのインストールを確認してください。
    ```
    git --version
    ```
    2. ユーザー名とメールアドレスを設定する必要があります。
    ```
    git config --global user.name GitHubに登録したユーザー名
    ```
    ```
    git config --global user.email GitHubに登録したメールアドレス
    ```
4. トークン認証について
   トークン認証は以下のような場合に行います。
   適宜、必要であれば行ってください。
   必要なさそうであれば、飛ばしてください。
   - HTTPS認証の代替手段として（パスワード廃止後の推奨手段）。
   - CI/CDパイプラインやスクリプトでの自動操作。
   - SSHが使えない環境でのリモートアクセス。
   - APIを利用してリモートリポジトリを操作する場合。
   - 限定的な権限を与えるためのセキュリティ対策。
   [こちら](https://docs.github.com/ja/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) のGitHub公式ページを参考に、トークンを発行してください。
   ** トークンは一度しか表示されない ** ようなので、十分に注意してください。
   [こちら](https://scrapbox.io/Prmn2023/Git%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E8%AA%8D%E8%A8%BC) の記事にトークン認証について、書いてあるので、参考にしてください。
   また、[こちら](https://scrapbox.io/Prmn2023/Git%E5%B0%8E%E5%85%A5) にも書いて場所があるので、必要であれば参考にしてください。
   

# 3. Git 操作について

## Git 操作の流れについて

- git操作で使うもの
    
    リモートリポジトリ・・・サーバにあるリポジトリ、チーム開発なら複数人で共有する
    
    ローカルリポジトリ・・・自分のリポジトリ、基本的に自分しか触らない
    
    ワークツリー・・・gitで管理するファイルを操作・編集する場所
    

- gitの操作の流れ

![Untitled](../../LectureImages/GitImages/git_operation_flow_image.png)  

上記のフローをgit用語(コマンド)と一緒に理解しよう！

## ローカルでの操作について

初めに、ローカルリポジトリ作成には2つの方法がある。

- 1つ目は、すでに使いたいgitリポジトリが存在する場合。以下のコマンドを使う。

    例）https://github.com/xxxxxxxxxx/xxxxxxxxx.git から clone する場合
    ```
    $ git clone https://github.com/xxxxxxxxxx/xxxxxxxxx.git
    ```

- 2つ目は、gitリポジトリを新規作成する場合。以下のコマンドを使う。

    ```
    $ git init
    ```

これらによって、.gitという隠しフォルダができる。

※ 1つ目の方法の方が、初心者には扱いやすいです。

詳しい操作は、以下の画像でまとめてあります。

![Untitled](../../LectureImages/GitImages/git_local_repo_image.png)  

```
$ git reset
```

コミット対象から除外

```
$ git checkout
```

コミット済みのものを除いた時の、1番最新のコミットした時のワークツリーの状態を取得

<補足>

```
$ git status
```

ローカルの変更の状態を確認できる

## リモートでの操作について

リモートリポジトリとローカルリポジトリとの間で行う操作は、以下にまとめてあります。

```
$ git push
```

リモートリポジトリからローカルリポジトリに操作の情報を送る

```
$ git fetch
```

リモートリポジトリからローカルリポジトリに変更を反映

```
$ git merge
```

ローカルリポジトリからワークツリーに変更を反映

```
$ git pull
```

リモートリポジトリからワークツリーに一気に変更を反映

![Untitled](../../LectureImages/GitImages/git_remote_repo_image.png)  

## ブランチの操作について

これまでは、ローカルとリモートの基本操作について、説明してきました。
さて、Git管理では、プロジェクトを木構造で管理すると最初に説明しました。
ここでは、Git で木構造で管理する方法について説明します。

まずは、これまでの操作を一つにまとめたものを以下に示します。

![Untitled](../../LectureImages/GitImages/git_both_repos_image.png)  

これを見ると、木構造が何か全くわからないかと思います。
これは、木構造において、各枝における操作に注目してきたからです。


ブランチは、リポジトリ内にコミット(歴史の記録)が溜まっていく中で、時系列的にかつ鎖状に連なっていきます。
そのため、ある場所から枝（ブランチ）を生やしてあげることで、枝分かれを可能にします。
また、ブランチはどの地点からでも作成できます。

つまり、それぞれのブランチの中で並行して開発を進めることで、複数人による同時開発を行うことができます。

### ブランチの作成・ブランチの切り替え

ブランチの作成には、以下のコマンドを使います。

例）hogehogeブランチを作成する場合
```
$ git branch hogehoge
```

![Untitled](../../LectureImages/GitImages/git_branch_image.png)  

作業中のブランチを「**HEAD**」と呼びます。

適宜**HEAD**の位置を変えて操作します。

例）hogehoge2ブランチに作業しているブランチを切り替える場合
```
▶️ git checkout hogehoge2
```

### ブランチの結合

複数作ったブランチは時が来たら統合してあげましょう！

統合方法は、以下の２つがあります。
- マージ
- リベース 

今回は、マージ の方をマスターしよう！

git rebase もやってみたいという人は、ここでは触れないので自分で調べてみてください。

![Untitled](../../LectureImages/GitImages/git_merage_image.png)  

**注意**  
同じ箇所の編集同士をマージしようとしてもgitではどちらが正しいかを判断できないため、**コンフリクト**が起きます。  
コンフリクトした場合は、人の判断で編集を残します。  
コンフリクトしていない箇所は、自動的にマージされます。  

そういえば、「checkout」が2回出てきたと思います。  
１つ目は、コミット済みのものをローカルリポジトリから、ワークツリーに取り込む時。  
２つ目は、ブランチの切り替えの時です。  
このままでは、「checkout」の役割が多いため、役割分担をしたものを以下に示します。  

どちらを使っても大丈夫です。開発チームに通じる方を使いましょう。  

![Untitled](../../LectureImages/GitImages/git_checkout_image.png)  


# 4. 参考資料
• [JJUGナイトセミナー「今だから聞きたいGit/GitHub入門」](https://www.youtube.com/watch?v=XRDCyAHffHE)