---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
title: 現在のリリースに含まれる新機能
feature: リリースノート
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b623b7ac3793aa340f0d3072e7453bd988b733ac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。 

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトに起こりうる問題を回避するため、新しい [!DNL Adobe Experience Platform Web SDK] の最新バージョンまたは at.js JavaScript ライブラリの最新バージョンに移行してください。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## at.js 2.6.0（2021年7月17日）

* at.js設定`secureOnly`が`true`に設定された場合は常に、セキュア属性がcookieに追加されました。
* `triggerView()`を使用する際にレスポンストークンを使用できるようになりました。
* `CONTENT_RENDERING_NO_OFFERS`イベントに関連する問題を修正しました。 現在は、[!DNL Target]からコンテンツが返されない場合は常にこのイベントが正しくトリガーされます。
* [!DNL Anlytics for Target] (A4T)クリック指標の詳細は、リクエストを使用する際に正しく返さ `prefetch` れます。
* UUID生成は、`Math.random()`を使用しなくなりましたが、`window.crypto`を使用します。
* `sessionId` cookieの有効期限は、すべてのネットワーク呼び出しで正しく拡張されます。
* [!UICONTROL 単一ページアプリケーション](SPA)ビューキャッシュの初期化が正しく処理され、`viewsEnable`設定に従うようになりました。

## [!DNL Target Standard/Premium] 21.6.1（2021年6月31日）

このリリースには、次の新機能および機能強化が含まれています。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

| 機能 | 詳細 |
| --- | --- |
| Analytics for Target（A4T） | [!DNL Analytics]をレポートソースとして使用する(A4T)アクティビティから、[!UICONTROL レポート]ページの「[!UICONTROL Analytics]で表示」リンクをクリックすると、[!DNL Analysis Workspace]が開きます。 以前は、リンクは[!DNL Analytics]レポートを開いていました。 （TGT-36959） |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | [!DNL Recommendations] 人気度アルゴリズムに次の機能強化が適用されます。<ul><li>[!DNL Target]が行動データソースの場合、すべての人気（最も多く閲覧された/トップセラー）アルゴリズムに対して、6時間の新しい「ルックバックウィンドウ」（データ範囲）オプションを使用できます。 （このルックバックウィンドウは、[!DNL Adobe Analytics] が行動データソースの場合は&#x200B;*使用できません*。）</li><li>選択すると、次のアルゴリズムは、（12時間ごとではなく）約3時間ごとに実行されます。<ul><li>最も頻繁に閲覧された</li><li>最も多く購入された</li><li>カテゴリ別で最も多く閲覧された</li><li>カテゴリ別で最も多く購入された</li><li>カスタム属性別で最も多く閲覧された（groupBy 機能を使用）</li><li>カスタム属性別で最も多く購入された（groupBy 機能を使用）</li></ul></ul>リリース日をお知らせします。 （上位 1086 項目） |

## Python SDK 1.0.0（2021年6月16日（PT））

デバイス上の判定機能を備えた新しい [!DNL Adobe Target] Python SDK が利用可能になりました。今回の最新の追加により、サーバー側 SDK の [!DNL Target] スイートが強化されます。これらの SDK は、選択した言語で [!DNL Target] と統合し、価値を生み出すまでの時間を短縮するのに役立ちます。サーバー側の統合は、市場がファーストパーティのデータが価値のある cookie のない世界に移行していることから、人気のある選択肢になりつつあります。Target SDK は、市場で最も人気のあるプログラミング言語（Python、Java、JavaScript、C#/.Net）で利用できます。

詳しくは、[Adobe Target SDK ガイド](https://adobetarget-sdks.gitbook.io/docs/)の [Python SDK ドキュメント](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/python-sdk)を参照してください。

## ![Adobe Experience Platform Web SDK バッジ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK]バージョン 2.5.0（2021 年 6 月 1 日（PT））

このリリースの [!DNL Platform Web SDK] には、次のサポートが含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Analytics for Target]（A4T）でのリダイレクトのサポート | [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md) を使用する場合、Platform Web SDK で [!DNL Target] リダイレクトがサポートされるようになりました。<br>詳しくは、[Analytics for [!DNL Target] の実装](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)を参照してください。 |

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、「[ドキュメントの変更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe 優先製品のアップデート | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
