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
  <<< Author notes: Step 4 >>>
  前のステップを認識してこのステップを始めてください。
  用語を定義し、docs.github.com へのリンクを貼ってください。
  TBD-step-4-notes.
-->

## ステップ 4: プルリクエストで脆弱性を防ごう

_ステップ3「セキュリティ脆弱性の修正」お疲れさまでした！:partying_face:_

ここまでよく頑張りました。あと少しで完了です！最後のステップでは、CodeQL とプルリクエストの連携を試します。このステップでは、`routes.py` ファイルに再び脆弱性を加え、SQLインジェクション脆弱性のアラートを発生させます。これは最初に見たのと同じ問題です。

このステップの目的は、開発者が新しい脆弱性を発見したときにどのような体験をするかを理解することです。

このステップで行うこと:
- `routes.py` ファイルを編集する
- SQL文を危険なものに書き換える
- その変更をコミットし、不正なコードを main ブランチにマージする
- プルリクエスト内でアラートを体験する

さっそく始めましょう 👍

**プルリクエストとは**: プルリクエストは、ユーザーがリポジトリに提案する変更であり、リポジトリのコラボレーターによって承認または却下されます。これにより、複数人が同じコードに同時に取り組むことができます。詳細は GitHub Skills コース「[Introduction to GitHub](https://github.com/skills/introduction-to-github)」や GitHub ドキュメントの「[プルリクエストについて](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)」をご覧ください。

**ブランチとは**: ブランチはリポジトリの並行バージョンです。デフォルトでは main という名前のブランチが1つあり、これが基準となります。追加のブランチを作成することで、main ブランチをコピーし、メインプロジェクトに影響を与えずに安全に変更を加えることができます。詳細は「[ブランチについて](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches#)」をご覧ください。

### :keyboard: アクティビティ 1: `routes.py` を編集し新しいプルリクエストを作成しよう

最初のアクティビティでは、以前と同じ危険な SQL 文を `routes.py` ファイルに追加します。ファイルを更新したら、新しいブランチにコミットし、プルリクエストを作成します。

  1. リポジトリの **Code** タブをクリックします。
  2. `server` フォルダを選択します。
  3. `routes.py` ファイルを選択します。
  4. 右側の **Edit** ボタンをクリックします。

![edit-button.png](/images/edit-button.png)
  
  5. 16行目の SQL 文を選択し、次の内容に置き換えます: `"SELECT * FROM books WHERE name LIKE '%" + name + "%'"`。
  6. 右上の **Commit changes...** をクリックします。「Propose changes」ウィンドウが表示されます。
  7. 今回は **Create a new branch** のラジオボタンを選択します。ブランチ名はデフォルトのままでも変更しても構いません。
  8. **Propose changes** をクリックします。これで新しいプルリクエストが作成されます。
  9. 「Open a pull request」ウィンドウで **Create pull request** をクリックします。
  

### :keyboard: アクティビティ 2: プルリクエストを確認しよう

ここまでで、`routes.py` ファイルに脆弱なコードを追加し、その変更を新しいブランチにコミットし、main ブランチへのプルリクエストを作成しました。これは、開発者が新しい脆弱なコードをリポジトリに導入する際の一般的な手順です。

次に、プルリクエストでどのような体験になるか見てみましょう。

1. 前のアクティビティでプルリクエストを作成しました。作成後は自動的にプルリクエストページに移動します。プルリクエストの下部に「Code scanning/CodeQL」というチェックが表示されます。これは、プルリクエストで導入されたコードを CodeQL がスキャンしていることを示します。

![pr-panel](/images/pr-panel.png)

2. チェックが完了すると、CodeQL から新しいセキュリティ脆弱性（ユーザー入力から構築された SQL クエリ）がある旨のコメントがプルリクエストに表示されます。これが SQL インジェクション脆弱性です。
  
  <img width="1180" alt="image" src="https://github.com/leftrightleft/enable-code-scanning/assets/4910518/378bd766-ef61-4619-ab3c-bf2c8d9618d7">

3. **Show paths** をクリックしてデータフローパスを確認しましょう。
  
4. 必要に応じてコメントを追加し、GitHub ハンドル（例: `@username`）で友人をタグ付けできます。これにより、コメントしたことや問題解決の協力依頼が通知されます。😄

実際の現場であれば、開発者は自分のブランチで SQL 文を修正します。修正が完了すると、脆弱性は自動的にクローズされます。

プルリクエストでのコードスキャン連携について詳しく知りたい場合は、「[プルリクエストでのコードスキャンアラートのトリアージ](https://docs.github.com/ja/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/triaging-code-scanning-alerts-in-pull-requests)」をご覧ください。

5. 約20秒待ってから、このページ（手順を読んでいるページ）をリフレッシュしてください。[GitHub Actions](https://docs.github.com/ja/actions) が自動的に次のステップへ進みます。

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
