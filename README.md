ステップ 1: 自分の情報をGitに設定しよう（最初の一回だけ！）
Gitを使う前に、誰が変更を加えたかを識別するために、あなたの名前とメールアドレスを設定します。これは一度設定すればOKです。

Bash

# 自分の名前を設定します。例: "Taro Yamada"
git config --global user.name "あなたの名前"

# 自分のメールアドレスを設定します。GitHubに登録しているメールアドレスが望ましいです。
git config --global user.email "あなたのメールアドレス@example.com"
【実行例】

Bash

git config --global user.name "Yui Tanaka"
git config --global user.email "yui.tanaka@example.com"
ステップ 2: プロジェクトのコードを自分のパソコンにコピーしよう（クローン）
共有されたGitHubのリポジトリ（コードが置かれている場所）を、あなたのパソコンにダウンロードします。

まず、プロジェクトを置きたいフォルダに移動しましょう。例えば、デスクトップにProjectsというフォルダを作りたいなら、以下のコマンドで移動します。

Bash

# 例: デスクトップにProjectsフォルダがある場合（ない場合は次のステップで作成）
cd ~/Desktop/Projects
もし、まだProjectsフォルダがなければ、作ってから移動できます。

Bash

# Projectsフォルダを作成
mkdir Projects

# 作成したProjectsフォルダに移動
cd Projects
移動したら、以下のコマンドでリポジトリをクローンします。

Bash

# 【重要！】このURLは私（PHP担当）が作成したリポジトリのURLです
git clone https://github.com/Comfort0217/FC-develop.git
【コマンドを実行した後】
クローンが完了すると、FC-developという新しいフォルダが、今いるディレクトリの中に作成されます。

ステップ 3: プロジェクトフォルダに移動しよう
クローンしたプロジェクトのフォルダ（FC-develop）の中に移動します。

Bash

cd FC-develop
【確認】
今、あなたはFC-developというフォルダの中にいます。今後、このフォルダの中で作業を行います。

ステップ 4: 新しい作業用のブランチを作成しよう（自分の作業部屋）
みんなで一緒に作業する時に、他の人の作業とごちゃごちゃにならないように、自分の作業専用の「ブランチ」という場所（作業部屋のようなもの）を作ります。

Bash

# 'develop'ブランチに切り替えます。これはチームのメインの作業ブランチです。
git checkout develop

# 自分の作業用のブランチを作成し、そこに切り替えます。
# 例: 'feature/web-ui-setup' の部分は、あなたの分かりやすい名前に変更してください。
# 例えば 'yui-frontend-setup' のようにしてもOKです。
git checkout -b feature/web-ui-setup
【確認】
コマンド実行後、ターミナルにSwitched to a new branch 'feature/web-ui-setup'のようなメッセージが表示されれば成功です。これであなたの作業部屋に移動しました。

ステップ 5: 最初の変更を加えてみよう（ファイルの作成とコミット）
試しに、簡単なHTMLファイルを作って、その変更をGitに記録してみましょう。

VS Code でプロジェクトを開く:
ターミナル（Git Bash/ターミナル）を開いたまま、以下のコマンドでVS Codeを開きます。

Bash

code .
（code . は、現在のディレクトリをVS Codeで開くコマンドです。VS Codeがインストールされていて、PATHが通っている必要があります。）

新しいファイルを作成:
VS Codeの左側のエクスプローラーで、FC-developフォルダの中にindex.htmlという新しいファイルを作成します。

簡単なHTMLコードを記述:
index.htmlに以下の内容を貼り付けて保存します。

HTML

<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ファンクラブサイト（テスト）</title>
</head>
<body>
    <h1>ようこそ！ファンクラブサイトへ</h1>
    <p>これは私の最初のGitコミットです！</p>
</body>
</html>
変更をGitに記録する準備（ステージング）:
ターミナルに戻り、Gitに変更を記録する準備ができたことを伝えます。

Bash

# 現在のフォルダの全ての変更を記録対象にする（今回の場合はindex.html）
git add .
変更を記録する（コミット）:
変更内容に短いコメント（コミットメッセージ）を付けて、Gitに正式に記録します。

Bash

# コミットメッセージは、何を変更したか簡潔に書きます
git commit -m "feat: 初めてのHTMLファイルを作成"
【確認】
[feature/web-ui-setup XXXXXXX] feat: 初めてのHTMLファイルを作成のようなメッセージが表示されれば成功です。あなたのパソコンのGitに変更が記録されました。

ステップ 6: 変更をGitHubにアップロードしよう（プッシュ）
自分のパソコンに記録した変更を、GitHubのリポジトリ（インターネット上の共有場所）にアップロードします。

Bash

# 自分のブランチの変更をGitHubにアップロードする
git push origin feature/web-ui-setup
【初回プッシュ時の注意】
git pushを初めて実行する際、--set-upstream origin feature/web-ui-setup のようなコマンドを実行するよう指示されることがあります。その場合は、指示されたコマンドをそのままコピー＆ペーストして実行してください。これは、あなたのローカルのブランチとGitHub上のブランチを紐付けるための設定です。

【確認】
プッシュが完了したら、GitHubのリポジトリページ（https://github.com/Comfort0217/FC-develop）を開き、feature/web-ui-setupブランチがあるか、そしてindex.htmlが追加されているかを確認してみましょう！

これで、基本的なGitのワークフロー（クローン → ブランチ作成 → 変更 → コミット → プッシュ）を体験できました。