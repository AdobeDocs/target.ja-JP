---
keywords: 実装；実装；実装；Adobe起動；起動；レース；リダイレクト；エクスペリエンスplatform launch;platform launch
description: Adobe [!DNL Target]を実装するのに推奨される方法である、Adobe Experience Platform Launchを使用したAdobe [!DNL Target] at.jsライブラリの実装方法を学びます。
title: Adobeの起動を使用して [!DNL Target] を実装する方法を教えてください。
feature: サーバー側での実装
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a69737f49a52cde703627f91d4b97609c1796ee6
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 6%

---

# [!DNL Adobe Platform Launch]を使用して[!DNL Target]を実装

[!DNL Adobe Experience Platform Launch] は、の次世代のタグ管理プラットフォームで [!DNL Adobe] す。これらのプラットフォームを使用して導入することをお勧め [!DNL Adobe Target]します。[!DNL Platform Launch] は、関連する顧客エクスペリエンスを強化するために必要なanalytics、マーケティングおよび広告タグを、顧客が簡単に導入および管理できるようにします。

## [!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25}を使用して[!DNL Target]を実装

次の表に、[!DNL Platform Launch]に関する詳細を得るための様々な情報源をリストします。

| リソース | 詳細 |
|--- |--- |
| [ [!DNL Target] Adobe Target拡張機能の使用チュートリアルの [!UICONTROL 実装]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | このチュートリアルでは、[!DNL Platform Launch]を使ってWebサイトに[!DNL Target]を導入する手順を順を追って説明します。 at.js JavaScript ライブラリの追加、グローバル mbox の発行、パラメーターの追加、他のソリューションとの統合といったトピックが含まれます。この記事は、[!DNL Platform Launch]や他の[!DNL Adobe Experience Cloud]ソリューションの実装方法を示す、より大規模なチュートリアルの一部です。 |
| [[!DNL Adobe Platform Launch] ドキュメント](https://experienceleague.adobe.com/docs/launch/using/get-started/quick-start.html#get-started) | 関連する顧客体験を強化するために必要な、Analytics、マーケティングおよび広告タグのデプロイと管理に関する情報です。 |
| [ [!DNL Target] AdobeExtensionドキュメント](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | [!DNL Platform Launch]を使用した[!DNL Target]の実装に関する情報です。 |

## [!DNL Target] [!DNL Platform Launch]拡張子{#section_48B3F938B6F8491DAF798E0DB54EF304}を使用してat.jsを実装する利点

次の利点は、at.jsを[!DNL Platform Launch]を使用して実装する場合にのみ当てはまります。 このため、[!DNL Adobe]は、at.jsの手動実装ではなく、[!DNL Platform Launch]を使用することを強くお勧めします。

* **解決 [!DNL Adobe Analytics] と [!DNL Target] 競合条件：** 呼び出しが呼び出される前に呼び出しが発生する可能性があるので、 [!DNL Analytics] 呼び出しは [!DNL Target]  [!DNL Target]  [!DNL Analytics] 呼び出しに関連付けられません。この優先順位付けは、誤ったデータを引き起こす可能性があります。 0.6.0以降、[!DNL Platform Launch]拡張子は、[!DNL Analytics]ビーコン呼び出しが[!DNL Target]呼び出しが正常に完了するかどうかを待つようにします。 [!DNL Platform Launch]を使用すると、手動で導入する際にユーザーが経験できるデータの矛盾を解決できます。
* **誤ったリダイレクトオファーの処理を防ぎ** ます。既にページ [!DNL Target] 上 [!DNL Analytics] にあ [!DNL Target] [!DNL Analytics] り、によってリダイレクトオファーが実行されている場合は、トラッカーが要求を実行すべきでないとき（ユーザーが別のURLにリダイレクトされているため）に発生する状況が考えられます。[!DNL Target]と[!DNL Analytics]を[!DNL Platform Launch]経由で実装すると、この問題は発生しません。 [!DNL Platform Launch]を使用して[!DNL Target]は、[!DNL Analytics]に対して[!DNL Analytics]ビーコンリクエストの中止を指示します。
