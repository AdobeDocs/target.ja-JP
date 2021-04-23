---
keywords: 実装；実装；実装；Adobe起動；起動；レース；リダイレクト；エクスペリエンスplatform launch
description: Adobe [!DNL Target]を実装するのに推奨される方法である、Adobe Experience Platform Launchを使用したAdobe [!DNL Target] at.jsライブラリの実装方法を学びます。
title: Adobeの起動を使用して [!DNL Target] を実装する方法を教えてください。
feature: サーバー側での実装
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 75%

---

# Adobeの起動を使用して[!DNL Target]を実装

Adobe Experience Platform Launchは、Adobeの次世代タグ管理プラットフォームで、Adobe Targetを導入するのに好ましい方法です。 Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

## Adobe起動{#topic_5234DDAEB0834333BD6BA1B05892FC25}を使用して[!DNL Target]を実装

Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

Launch の詳細な情報を取得できる様々なソースを次の表に示します。

| リソース | 詳細 |
|--- |--- |
| [Adobe Target拡張機能のチュートリアルを使用したターゲットの実装](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | このチュートリアルでは、Launch を使用して Web サイトで Adobe Target を実装する手順を詳しく説明します。at.js JavaScript ライブラリの追加、グローバル mbox の発行、パラメーターの追加、他のソリューションとの統合といったトピックが含まれます。この記事は、Adobe Launch の実装方法やその他の Adobe Experience Cloud ソリューションの実装方法を示す長尺のチュートリアルの一部になっています。 |
| [Adobe Launch ドキュメント](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html) | 適切な顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグのデプロイおよび管理に関する情報です。 |
| [Adobe Target拡張機能ドキュメント](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Launch を使用した Target の実装に関する情報です。 |

## [!DNL Target] Launch extension {#section_48B3F938B6F8491DAF798E0DB54EF304}を使用してat.jsを実装する利点

次のメリットは、Adobe Launch を使用して at.js を実装する場合にのみ適用されます。そのため、DTM または at.js の手動実装ではなく Adobe Launch を使用することを強くお勧めします。

* **Analytics と Target の競合状態の解消：** Analytics の呼び出しは Target の呼び出しより先に実行される可能性があるので、Target の呼び出しは Analytics の呼び出しには結合されません。これにより、不正なデータが発生するおそれがあります。0.6.0 以降を使用すると、Target Launch 拡張機能では、Target の呼び出しが（成功するにせよ失敗するにせよ）完了するまで Analytics のビーコン呼び出しが待機します。これで、お客様が経験した可能性のあるデータ不整合の問題が解決されます。
* **不正なリダイレクトオファー処理の防止：**&#x200B;ページに Target と Analytics の両方があり、Target によってリダイレクトオファーが実行される場合、（ユーザーが別の URL にリダイレクトされているので）Analytics トラッカーが誤ってリクエストを発行する状況に陥る可能性があります。Target および Analytics を Launch を使用して実装する場合、この問題は発生しません。Launch を使用すると、Target は Analytics に Analytics ビーコンリクエストを中止するように指示します。
