---
keywords: 実装；実装；実装；adobe launch；競合；リダイレクト；エクスペリエンスplatform launch;platform launch；タグ；adobe platform
description: ' [!DNL Adobe Experience Platform], the preferred method to implement [!DNL Target]を使用して [!DNL Adobe Target] at.jsライブラリを実装する方法を説明します。'
title: ' [!DNL Adobe Experience Platform]を使用して [!DNL Target] を実装する方法を教えてください。'
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 11%

---

# [!DNL Target] を使用した [!DNL Adobe Experience Platform] の実装

[!DNL Adobe Experience Platform]のタグは、[!DNL Adobe]の次世代タグ管理機能です。 タグを使用すると、顧客体験の実現に必要な分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] は、[!DNL Adobe Experience Platform] のデータ収集テクノロジーのスイートとしてリブランドされました。その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。用語の変更点の統合的な参照については、次の[ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)を参照してください。

次の表に、詳細を取得できる様々なソースを示します。

| リソース | 詳細 |
|--- |--- |
| [ [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | このチュートリアルでは、[!DNL Adobe Experience Platform]にタグを含むWebサイトに[!DNL Target]を実装する手順を順を追って説明します。 at.js JavaScript ライブラリの追加、グローバル mbox の発行、パラメーターの追加、他のソリューションとの統合といったトピックが含まれます。この記事は、[!DNL Adobe Experience Platform]や他の[!DNL Adobe Experience Cloud]ソリューションの実装方法を示す、より大きなチュートリアルの一部です。 |
| [クイックスタートガイド](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | 顧客体験の実現に必要な分析、マーケティングおよび広告のタグのデプロイと管理に関する情報です。 |
| [ [!DNL Target] Adobeextensionの概要](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | [!DNL Adobe Experience Platform]を使用した[!DNL Target]の実装に関する情報です。 |

## [!DNL Target]拡張機能を使用してat.jsを実装するメリット {#section_48B3F938B6F8491DAF798E0DB54EF304}

次の利点は、[!DNL Adobe Experience Platform]でタグを使用してat.jsを実装する場合にのみ当てはまります。 このため、[!DNL Adobe]では、at.jsの手動実装ではなく、[!DNL Adobe Experience Platform]でタグを使用することを強くお勧めします。

* **解 [!DNL Adobe Analytics] 決と [!DNL Target] 競合状態：** 呼び出し [!DNL Analytics] は呼び出しの前に実行される可能性があるので、呼び出 [!DNL Target] しは呼び出 [!DNL Target] しに結び付けられ [!DNL Analytics] ません。このシーケンス化は、誤ったデータを引き起こす可能性があります。 [!DNL Target]拡張機能は、 [!DNL Analytics]ビーコン呼び出しが[!DNL Target]呼び出しが正常に完了するかどうかを待つようにします。 [!DNL Adobe Experience Platform]でタグを使用すると、手動で実装する際に顧客が経験するデータの不整合を解決できます。

   >[!NOTE]
   >
   >[!UICONTROL Send Beacon]アクションを[!DNL Adobe Analytics]拡張で使用して、[!DNL Analytics]呼び出しが[!DNL Target]呼び出しを待つようにします。 カスタムコードを使用して`s.t()`または`s.tl()`を直接呼び出す場合、[!DNL Analytics]の呼び出しは、[!DNL Target]の呼び出しが完了するまで待ちません。

* **誤ったリダイレクトオファーの処理を防ぎます。** ページに [!DNL Target] とがあ [!DNL Analytics] り、によって実行されたリダイレクトオファーがある場合 [!DNL Target]は、(ユーザーが別のURLにリダイレクトされるの [!DNL Analytics] で)トラッカーが要求を実行しないという状況が発生する可能性があります。[!DNL Adobe Experience Platform]のタグを使用して[!DNL Target]と[!DNL Analytics]を実装した場合、この問題は発生しません。 [!DNL Adobe Experience Platform]でタグを使用すると、[!DNL Target]は[!DNL Analytics]に[!DNL Analytics]ビーコンリクエストを中止するよう指示します。
