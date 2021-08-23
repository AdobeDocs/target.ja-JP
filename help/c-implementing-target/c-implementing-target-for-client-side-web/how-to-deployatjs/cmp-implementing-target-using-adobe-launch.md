---
keywords: 実装；実装；実装；Adobe Launch;Launch；競合；リダイレクト；エクスペリエンスplatform launch;platform launch
description: Adobe Experience Platform Launch(Adobe [!DNL Target]を実装する推奨される方法)を使用してAdobe [!DNL Target] at.jsライブラリを実装する方法について説明します。
title: AdobeLaunchを使用して [!DNL Target] を実装する方法を教えてください。
feature: サーバー側の実装
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: fd7d3900f9e5d1a6c3d13fd2452de8528f8fd248
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 5%

---

# [!DNL Adobe Platform Launch]を使用して[!DNL Target]を実装します。

[!DNL Adobe Experience Platform Launch] は、の次世代タグ管理プラットフォームで [!DNL Adobe] あり、を実装するのに推奨される方法で [!DNL Adobe Target]す。[!DNL Platform Launch] は、顧客体験の実現に必要な分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

## [!DNL Platform Launch]を使用して[!DNL Target]を実装します。 {#topic_5234DDAEB0834333BD6BA1B05892FC25}

次の表に、[!DNL Platform Launch]に関する詳細情報を取得できる様々なソースを示します。

| リソース | 詳細 |
|--- |--- |
| [ [!DNL Target] 『  [!UICONTROL Adobe Target Extensionを使用した実装』チュートリアル]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | このチュートリアルでは、[!DNL Platform Launch]を使用してWebサイトに[!DNL Target]を実装する手順を順を追って説明します。 at.js JavaScript ライブラリの追加、グローバル mbox の発行、パラメーターの追加、他のソリューションとの統合といったトピックが含まれます。この記事は、[!DNL Platform Launch]や他の[!DNL Adobe Experience Cloud]ソリューションの実装方法を示す、より大きなチュートリアルの一部です。 |
| [Adobe Experience Platformのタグのクイックスタートガイド](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | 顧客体験の実現に必要な分析、マーケティングおよび広告のタグのデプロイと管理に関する情報です。 |
| [ [!DNL Target] AdobeExtensionドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | [!DNL Platform Launch]を使用した[!DNL Target]の実装に関する情報です。 |

## [!DNL Target] [!DNL Platform Launch]拡張機能を使用してat.jsを実装するメリット {#section_48B3F938B6F8491DAF798E0DB54EF304}

次の利点は、[!DNL Platform Launch]を使用してat.jsを実装する場合にのみ当てはまります。 このため、[!DNL Adobe]では、at.jsの手動実装ではなく[!DNL Platform Launch]を使用することを強くお勧めします。

* **解 [!DNL Adobe Analytics] 決と [!DNL Target] 競合状態：** 呼び出し [!DNL Analytics] は呼び出しの前に実行される可能性があるので、呼び出 [!DNL Target] しは呼び出 [!DNL Target] しに結び付けられ [!DNL Analytics] ません。このシーケンス化は、誤ったデータを引き起こす可能性があります。 0.6.0以降、[!DNL Platform Launch]拡張機能は、[!DNL Target]の呼び出しが正常に完了するかどうかにかかわらず、[!DNL Analytics]のビーコン呼び出しが待機するようにします。 [!DNL Platform Launch]を使用すると、お客様が手動で実装する際に経験するデータの不整合を解決できます。
* **誤ったリダイレクトオファーの処理を防ぎます。** ページに [!DNL Target] とがあ [!DNL Analytics] り、によって実行されたリダイレクトオファーがある場合 [!DNL Target]は、(ユーザーが別のURLにリダイレクトされるの [!DNL Analytics] で)トラッカーが要求を実行しないという状況が発生する可能性があります。[!DNL Target]と[!DNL Analytics]を[!DNL Platform Launch]経由で実装した場合、この問題は発生しません。 [!DNL Platform Launch]を使用すると、[!DNL Target]は[!DNL Analytics]に[!DNL Analytics]ビーコンリクエストを中止するように指示します。
