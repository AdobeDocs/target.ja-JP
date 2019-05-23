---
description: Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。
keywords: 実装;実装する;導入;Adobe Launch;Launch;競合;リダイレクト
seo-description: Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。
seo-title: Adobe Launch を使用した Target の実装
title: Adobe Launch を使用した Target の実装
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 19834da75f163d6357bc9b986a23f0bc1fea6d8e

---


# Adobe Launch を使用した Target の実装{#implement-target-using-adobe-launch}

Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

## Adobe Launch を使用した Target の実装 {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

Launch の詳細な情報を取得できる様々なソースを次の表に示します。

| リソース | 詳細 |
|--- |--- |
| [Adobe Target Extensionチュートリアルを使用したTargetの実装](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | このチュートリアルでは、Launch を使用して Web サイトで Adobe Target を実装する手順を詳しく説明します。at.js JavaScript ライブラリの追加、グローバル mbox の発行、パラメーターの追加、他のソリューションとの統合といったトピックが含まれます。この記事は、Adobe Launch の実装方法やその他の Adobe Experience Cloud ソリューションの実装方法を示す長尺のチュートリアルの一部になっています。 |
| [Adobe Launch ドキュメント](https://docs.adobelaunch.com/getting-started) | 適切な顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグのデプロイおよび管理に関する情報。 |
| [Adobe Target Extensionドキュメント](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension) | Launch を使用した Target の実装に関する情報。 |

## Target Launch 拡張機能を使用して at.js を実装するメリット {#section_48B3F938B6F8491DAF798E0DB54EF304}

次のメリットは、Adobe Launch を使用して at.js を実装する場合にのみ適用されます。そのため、DTM または at.js の手動実装ではなく Adobe Launch を使用することを強くお勧めします。

* **Target の非同期デプロイが可能：**詳しくは、「[Adobe Target 拡張機能のドキュメント](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension)」（）の「非同期デプロイが可能な Adobe Target 拡張機能」を参照してください。
* **Analytics と Target の競合状態の解消：** Analytics の呼び出しは Target の呼び出しより先に実行される可能性があるので、Target の呼び出しは Analytics の呼び出しには結合されません。この結果、不正なデータが発生するおそれがあります。Launch 0.6.0 以降を使用すると、Target Launch 拡張機能では、Target の呼び出しが（成功するにせよ失敗するにせよ）完了するまで Analytics のビーコン呼び出しが待機するようになります。これで、お客様が経験した可能性のあるデータ不整合の問題が解決されます。
* **不正なリダイレクトオファー処理の防止**ページに Target と Analytics の両方があり、Target によってリダイレクトオファーが実行される場合、Analytics トラッカーが誤ってリクエストを発行する状況に陥る可能性があります。これは、ユーザーが別の URL にリダイレクトされようとしているからです。Launch を通じて Target と Analytics を実装する場合は、このような問題は発生しません。Target が Launch を使用して、Analytics ビーコンリクエストを中止するように Analytics に指示するからです。

