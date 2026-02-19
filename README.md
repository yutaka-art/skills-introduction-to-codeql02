<header>

<!--
  <<< 著者向けメモ: コースヘッダー >>>
  コースの作成方法については <https://skills.github.com/quickstart> を参照してください。
  1280×640 の画像、文の形式でのコース名、簡潔な説明文（斜体）を含めてください。
  リポジトリの設定では：テンプレートリポジトリを有効化し、1280×640 のソーシャル画像を追加し、マージ後は自動でブランチを削除する設定にしてください。
  「About」の隣に説明とタグを追加し、リリース、パッケージ、環境は無効にしてください。
  オープンソースライセンスを追加してください（GitHubではMITライセンスが使用されます）。
-->

# CodeQL を有効にしてソースコードのセキュリティを確保しよう

_アプリケーションのソースコードのセキュリティを確保することは、現代のソフトウェア開発において重要なステップです。この GitHub Skills コースでは、GitHub のコードスキャン機能を使用して、セキュリティ上の問題のあるコーディングパターンを特定・解決・予防する方法を学びます。_

</header>

<!--
  <<< Author notes: Step 1 >>>
  コースには3～5ステップを選んでください。
  最初のステップは簡単なものにしましょう！
  詳細説明は docs.github.com へのリンクを貼ってください。
  ステップごとに新しいタブで開くことを推奨してください！
  TBD-step-1-notes.
-->

## ステップ 1: CodeQL を有効化しよう

👋 こんにちは！GitHub Skills コース「コードスキャンを有効化しよう」へようこそ！

さっそく始めましょう！

この最初のステップでは、CodeQL について学び、ソースコードを安全に保つ方法を体験します。

**GitHub コードスキャンとは**: _[コードスキャン](https://docs.github.com/ja/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning)_ は、開発チームがセキュリティテストツールをソフトウェア開発プロセスに統合できる機能です。これは GitHub Actions を使って実現されます。コードスキャンでは、SAST、コンテナ、インフラストラクチャ as Code のセキュリティツールなど、さまざまなツールを統合できます。

**CodeQL とは**: _[CodeQL](https://docs.github.com/ja/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning-with-codeql)_ は、SQLインジェクションやクロスサイトスクリプティング、コードインジェクションなどのセキュリティ上の弱点を特定する静的解析テストツールです。

### :keyboard: アクティビティ: CodeQL でコードスキャンを有効化しよう

まず、リポジトリで CodeQL を使ったコードスキャンを有効化します。

1. 新しいブラウザタブを開き、このタブで手順を読みながら、もう一方のタブで作業を進めてください。
2. 作成したリポジトリの上部にある **Settings（設定）** タブに移動します。
3. 左側の **Security（セキュリティ）** セクションから **Code security and analysis（コードセキュリティと分析）** を選択します。
4. **Code scanning（コードスキャン）** というセクションまでスクロールします。このコースでは CodeQL 分析に注目します。
5. **Set up（セットアップ）** ドロップダウンメニューをクリックし、**Default（デフォルト）** を選択します。
![enable-code-scanning-default.png](/images/enable-code-scanning-default.png)

モーダルの設定オプションを見てみましょう：

  - **Languages to analyze（解析する言語）:** CodeQL でスキャンする言語です。今回は `Python` をスキャンします。
  - **Query suites（クエリスイート）:** CodeQL の[クエリ](https://docs.github.com/ja/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning-with-codeql#about-codeql-queries)は「スイート」と呼ばれるバンドルで提供されます。このセクションで使用するクエリスイートを選択できます。今回は **Default** のままにします。詳細は「[CodeQL クエリについて](https://docs.github.com/ja/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning-with-codeql#about-codeql-queries)」をご覧ください。
  - **Events（イベント）:** いつ CodeQL がスキャンを実行するかを指定します。今回は `main` ブランチへのプルリクエスト時にスキャンされます。

![codeql-default-configuration-box.png](/images/codeql-default-configuration-box.png)

6. **Enable CodeQL（CodeQL を有効化）** をクリックします。
7. 約20秒待ってから、このページ（手順を読んでいるページ）をリフレッシュしてください。[GitHub Actions](https://docs.github.com/ja/actions) が自動的に次のステップへ進みます。

<footer>

<!--
  <<< 著者向けメモ: フッター >>>
  サポートリンク、GitHubステータス、行動規範、ライセンスなどを追加してください。
-->

---

サポートが必要な場合：[ディスカッション掲示板に投稿する](https://github.com/orgs/skills/discussions/categories/introduction-to-codeql)  
GitHubの稼働状況：[ステータスページを見る](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [行動規範](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MITライセンス](https://gh.io/mit)

</footer>
