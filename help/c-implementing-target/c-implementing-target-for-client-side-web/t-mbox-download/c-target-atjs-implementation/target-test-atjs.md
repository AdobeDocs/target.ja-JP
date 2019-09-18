---
description: 実稼動環境以外に at.js を安全にデプロイする方法に関する情報を紹介します。
seo-description: 実稼動環境以外に at.js を安全にデプロイする方法に関する情報を紹介します。
seo-title: at.js の実稼動環境以外へのデプロイ
title: at.js の実稼動環境以外へのデプロイ
uuid: 7f1adc43-35b4-442c-bb06-feab60604a87
translation-type: tm+mt
source-git-commit: 2aa63623b4d2ca38ec96c51402ee483a918dd3ae

---


# Deploy at.js to a non-production environment{#deploy-at-js-to-a-non-production-environment}

実稼動環境以外に at.js を安全にデプロイするためのテクノロジーに関する情報を紹介します。

## DTM ステージングへのデプロイ

DTM を使用する場合、Adobe Target ツール設定に簡単に at.js を保存できます。

ライブラリを保存すると、DTM Switch ツールを使用して、実稼動用コードに対してテストできます。また、これにより、アドビのコンサルタントがユーザーをサポートしやすくなります。

詳しくは、Dynamic Tag Management を使用した Adobe Target の実装のベストプラクティス&#x200B;**&#x200B;ガイドの[オプション 3：DTM でホストされた Target JavaScript ライブラリによる Target の手動での実装](https://docs.adobe.com/content/help/en/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html)を参照してください。

## Chrome 拡張機能「Requestly」を使用した別のファイルへのマッピング

>[!NOTE]
>
>以下の情報に加えて、Google Chrome 用 [Adobe Target VEC ヘルパーブラウザー拡張機能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用できます。

[Requestly](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) は、無料の Chrome 拡張機能です。リクエストを代替 URL にリダイレクトできます。

at.js をある URL にデプロイしたら、Requestly を使用して現在の mbox.js ファイルの URL を新しい at.js の URL にマッピングします。その結果、Web サイトが mbox.js を読み込もうとすると、代わりに at.js が読み込まれます。この方法により、アドビからのサポートの提供も容易になります。

## 開発、ステージングまたは QA 環境へのデプロイ

コードベースで mbox.js をホストし、コード環境を簡単に更新できる場合、at.js をより下位の環境の 1 つにデプロイします。

アドビからより確実なサポートを受けるために、アドビがアクセスできる環境にファイルをデプロイします。

## Charles や Fiddler を使用したローカルファイルへのマッピング

[Charles Web Debugging Proxy](https://www.charlesproxy.com/) は、Mac および Windows で利用可能なアプリケーションで、Map Local 機能を使用して実稼動 mbox.js ファイルを at.js のローカルコピーにマッピングするのに使用できます。Mac および Windows 用の無料の体験版をダウンロードできます。

[Fiddler](https://www.telerik.com/fiddler) は、同様のツールで、Windows 用の無料ダウンロード版として利用可能です。

## 別のタグ管理環境へのデプロイ

別のタグマネージャーを使用している場合、実稼動トラフィックに影響を与えることなく、安全に at.js をデプロイする方法があるはずです。