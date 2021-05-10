---
keywords: at.js；実稼働以外；実稼働以外；デプロイ
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience PlatformWeb SDK(AEP Web SDK)またはat.jsの最新バージョンに移行します。
title: at.jsを実稼働以外の環境にデプロイする方法を教えてください。
feature: at.js
role: Developer
exl-id: 607b2b5b-bb2a-4443-abc0-452b421fc009
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 80%

---

# at.jsの実稼働以外の環境へのデプロイ

実稼動環境以外に at.js を安全にデプロイするためのテクノロジーに関する情報を紹介します。

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
