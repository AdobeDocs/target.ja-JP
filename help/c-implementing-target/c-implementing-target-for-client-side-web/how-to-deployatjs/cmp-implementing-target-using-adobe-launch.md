---
description: Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。
keywords: 実装;実装する;導入;Adobe Launch;Launch;競合;リダイレクト
seo-description: Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。
seo-title: Adobe Launch を使用した Target の実装
title: Adobe Launch を使用した Target の実装
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 56bfceba22df830933aa005bf7faf24d4d6c09ba

---


# Adobe Launch を使用した Target の実装{#implement-target-using-adobe-launch}

Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

## Adobe Launch を使用した Target の実装 {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

Launch の詳細な情報を取得できる様々なソースを次の表に示します。

| リソース | 詳細 |
|--- |--- |
| [Adobe Target Extensionチュートリアルを使用したTargetの実装](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | このチュートリアルでは、Launch を使用して Web サイトで Adobe Target を実装する手順を詳しく説明します。at.js JavaScript ライブラリの追加、グローバル mbox の発行、パラメーターの追加、他のソリューションとの統合といったトピックが含まれます。この記事は、Adobe Launch の実装方法やその他の Adobe Experience Cloud ソリューションの実装方法を示す長尺のチュートリアルの一部になっています。 |
| [Adobe Launch ドキュメント](https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html) | 適切な顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグのデプロイおよび管理に関する情報。 |
| [Adobe Target Extensionドキュメント](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Launch を使用した Target の実装に関する情報。 |

## Target Launch 拡張機能を使用して at.js を実装するメリット {#section_48B3F938B6F8491DAF798E0DB54EF304}

次のメリットは、Adobe Launch を使用して at.js を実装する場合にのみ適用されます。そのため、DTM または at.js の手動実装ではなく Adobe Launch を使用することを強くお勧めします。

* **AnalyticsとTarget競合条件の解決:** Analytics呼び出しはTarget呼び出しの前に実行されることがあるので、Target呼び出しはAnalytics呼び出しに繋ぎ合わされません。これは不正なデータにつながる可能性があります。0.6.0から、Target起動拡張機能により、Targetの呼び出しが完了するまでAnalyticsビーコンの呼び出しが待機し、成功したかどうかが確認されます。これで、お客様が経験した可能性のあるデータ不整合の問題が解決されます。
* **リダイレクトオファーの処理の誤りを防止:** ページ上にTargetとAnalyticsがある場合、Targetによってリダイレクトオファーが実行された場合、Analyticsトラッカーがリクエストを実行したときにリクエストが実行される可能性があります（ユーザーが別のURLにリダイレクトされるので）。TargetとAnalyticsを起動して実装する場合、この問題は発生しません。「開始」を使用すると、AnalyticsはAnalyticsビーコンリクエストを中止するようAnalyticsに指示します。
