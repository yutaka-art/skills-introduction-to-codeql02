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
  <<< 著者向けメモ: ステップ 1 >>>
  コースには 3〜5 ステップを設定しましょう。
  最初のステップは簡単なものにするのがおすすめです！
  詳細説明には docs.github.com へのリンクを活用しましょう。
  新しいタブで開くようにユーザーに促してください。
-->

## ようこそ

_「CodeQL 入門」へようこそ！ :wave:_

このコースでは、[CodeQL](https://codeql.github.com/) を活用した GitHub のコードスキャン機能を使って、セキュリティ脆弱性につながる一般的なコーディングパターンを特定する方法を学びます。  
実際にご自身のリポジトリでコードスキャンを有効にし、脆弱性の特定・修正・予防を体験していただきます。

コードスキャンは [GitHub Advanced Security (GHAS)](https://docs.github.com/ja/get-started/learning-about-github/about-github-advanced-security) の一部です。Advanced Security のすべての機能は、オープンソースのパブリックリポジトリに対しては 100% 無料で利用できます。

- **対象者**：開発者、セキュリティエンジニア、OSSメンテナー
- **学べること**：CodeQL によるコードスキャンの有効化方法と、SQLインジェクションの検出方法を学びます
- **作成するもの**：本番コードに新たな脆弱性が混入するのを防ぐ、安全なソフトウェア開発パイプライン
- **前提知識**：このコースでは、Pull Request、GitHub Actions、ソースコードなどの基本的な GitHub の概念に加えて、SAST（静的アプリケーションセキュリティテスト）の基礎的な知識が求められます。ただし難しい部分は丁寧に説明しますのでご安心ください 🙂
- **所要時間**：全4ステップ、30分以内で完了できます

## コースの始め方

[![start-course](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=yutaka-art&template_name=introduction-to-codeql&owner=%40me&name=skills-introduction-to-codeql&description=GitHub+Skills:+Introduction+to+CodeQL&visibility=public)

1. **「start-course」** を右クリックして、新しいタブでリンクを開いてください。
2. 新しいタブでは、多くの項目が自動で入力されます。
   - オーナーにはご自身の個人アカウント、またはホストしたい組織を選択してください。
   - プライベートリポジトリでは [Actions の実行分数](https://docs.github.com/ja/billing/managing-billing-for-github-actions/about-billing-for-github-actions)が消費されるため、パブリックリポジトリをおすすめします。
   - フォーム下部にある **「Create repository」** ボタンをクリックしてください。
3. リポジトリが作成されたら、約20秒待ってからページを更新し、新しいリポジトリの README に記載された手順に従ってください。

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
