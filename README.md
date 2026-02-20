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
  <<< Author notes: Step 2 >>>
  前のステップを認識してこのステップを始めてください。
  用語を定義し、docs.github.com へのリンクを貼ってください。
  TBD-step-2-notes.
-->

## ステップ 2: CodeQL アラートの確認とトリアージ

_素晴らしい！CodeQL が動作しました！ :tada:_

この演習では、CodeQL スキャン結果の確認、アラートのトリアージ、アラートを追跡するための GitHub Issue の作成を行います。

**GitHub Actions とは**: GitHub Actions は GitHub 内の自動化・CI/CD プラットフォームです。コードスキャンによるセキュリティスキャンの実行や管理に利用します。GitHub Actions はビルド、テスト、デプロイのパイプラインを自動化できる継続的インテグレーション／継続的デリバリー（CI/CD）プラットフォームです。詳細は「[GitHub Actions について](https://docs.github.com/ja/actions/learn-github-actions/understanding-github-actions)」をご覧ください。

**CWE とは**: Common Weakness Enumeration（CWE）は、ハードウェアやソフトウェアの弱点・脆弱性を分類するためのカテゴリシステムです。アプリケーションのソースコードにおけるセキュリティ問題を記述・分類する方法と考えてください。CWE の詳細は Wikipedia の「[Common Weakness Enumeration](https://ja.wikipedia.org/wiki/Common_Weakness_Enumeration)」をご覧ください。

### :keyboard: アクティビティ 1: CodeQL スキャンのステータスを確認しよう

このアクティビティでは、GitHub Actions で CodeQL スキャンのステータスを確認します。  
1. 新しいリポジトリで、上部ナビゲーションバーから **Actions** を選択して Actions ページに移動します。CodeQL Action の実行がまだ進行中の場合、黄色いスピナーが表示されます。通常、完了まで約4分かかります。
2. **CodeQL Setup** をクリックして実行を選択します。

![codeql-setup](/images/codeql-setup.png)

Actions の実行内ではさらに多くの情報が確認できます。CodeQL のログ、所要時間、ステータス、生成されたアーティファクトなどを自由に確認してみてください。

スキャンが完了すると、実行の横に緑色のチェックが表示されます。  
  
### :keyboard: アクティビティ 2: すべての CodeQL アラートを確認しよう

このアクティビティでは、リポジトリの Security ページで CodeQL の検出結果を確認します。Security ページには、すべてのセキュリティ関連情報が表示されます。

1. リポジトリ上部のナビゲーションバーから **Security** タブに移動します。  
2. 左側の「Vulnerability alerts」見出しの下にある **Code scanning** を選択します。

この画面には、CodeQL がこのリポジトリのコードベースで特定したすべての脆弱性が表示されます。さまざまなフィルターや検索機能も試してみてください。多くの検出結果がある場合に非常に役立ちます！


### :keyboard: アクティビティ 3: アラートを確認しよう

このアクティビティでは、アラートの UI を確認します。脆弱性のデータフローを確認し、どのコード部分に影響があるかを特定し、アラートの詳細情報を取得します。

**アラートステータス:** このセクションでは、現在のアラートステータス（オープンまたはクローズ）、スキャンでアラートが検出されたブランチ、アラートのタイムスタンプが表示されます。
  
![alert-status](/images/alert-status.png)

**場所情報:** このセクションでは、どのコード部分が脆弱かを示します。  
  
![location-information](/images/location-information.png)

**パス:** 「Show paths」をクリックすると、アラートのデータフローに関する追加情報が表示されます。モーダルでは、ユーザー入力（「ソース」と呼びます）がアプリケーション内をどのように流れ、最終的にどこで利用されるか（「シンク」と呼びます）が可視化されます。これにより、アプリケーション内のデータの流れが分かります。
  
**推奨事項:** このセクションでは、ツール（この場合は CodeQL）、ルールID、脆弱性を検出した CodeQL クエリの表示（**View source** で確認可能）、および修正のための推奨事項が表示されます。**Show more** をクリックすると、推奨事項の全文が表示されます。

![recommendations](/images/recommendations.png)

**監査証跡:** 監査証跡にはアラートの履歴が表示されます。ユーザーがアラートをクローズしたり、コードで修正した場合のステータスが記録されます。

![audit-trail](/images/audit-trail.png)

**アラートのトリアージ:** アラート右上のボタンでトリアージや新しい Issue の作成ができます。まだ何もしないでください。これらのボタンについては後ほど説明します。😄

**追加情報:** 右側のパネルには、タグ、CWE 情報、アラートの重大度などが表示されます。
  ![additional-information.png](/images/additiona-information.png)


### :keyboard: アクティビティ 4: アラートを却下しよう

アラート画面の構成に慣れたところで、アラートをクローズする手順を体験しましょう。

1. 同じアラート画面で **Dismiss alert** をクリックし、却下理由を選択して簡単なメモを入力します。
2. **Dismiss alert** をクリックします。
3. これでアラートの状態が「Dismissed（却下）」に変わります。アラート下部の監査証跡で変更履歴を確認できます。
4. **Security** > **Code scanning alerts** に戻ると、アラートが1件だけリストされているのが分かります。
5. **1 Closed** をクリックすると、クローズされたアラート一覧が表示され、先ほど却下したアラートを確認できます。
   ![one-closed-alert.png](/images/one-closed-alert.png)

7. （オプション）アラートを再度開き、**Reopen alert** を選択することでアラートを再オープンすることもできます。

### :keyboard: アクティビティ 5: アラートの GitHub Issue を作成しよう

最後のステップでは、脆弱性の解決作業を追跡するための GitHub Issue の作成方法を紹介します。Issue はセキュリティ問題に関するコラボレーションの場を提供し、担当者やチームに割り当てることができます。
  
1. CodeQL のスキャンで検出されたオープンなアラートのいずれかを開きます。
2. アラート右上の緑色の **Create issue** ボタンをクリックします。ボタンが表示されない場合は、アラートがオープン状態か確認してください。
3. 新しい Issue フォームに必要な詳細を入力します。  
4. **Submit new issue** をクリックします。
5. Issue を確認するには、リポジトリ上部の **Issues** をクリックします。
6. 約20秒待ってから、このページ（手順を読んでいるページ）をリフレッシュしてください。[GitHub Actions](https://docs.github.com/ja/actions) が自動的に次のステップへ進みます。

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
