---
keywords: 実装;at.js;JavaScript ライブラリ
description: Adobe [!DNL Target] Adobe Experience Platformのタグを使用する、またはタグマネージャーを使用しない、at.js JavaScript ライブラリ。
title: at.js のデプロイ方法を教えてください。
feature: Implement Server-side
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 35%

---

# at.js のデプロイ方法

のデプロイ方法に関する情報 [!DNL Adobe Target] JavaScript ライブラリ、at.js、タグを使用 [!DNL Adobe Experience Platform] またはタグマネージャーがない場合は、

次の方法を使用して at.js をデプロイできます。

* **[実装方法 [!DNL Target] タグの使用 [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**:タグ [!DNL Adobe Experience Platform] は、 [!DNL Adobe]. タグは、適切な顧客体験の実現に必要な分析、マーケティングおよび広告タグをデプロイおよび管理するためのシンプルな手段を提供します。

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] は、[!DNL Adobe Experience Platform] のデータ収集テクノロジーのスイートとしてリブランドされました。その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。用語の変更に関する参照の一覧については、次の[ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=ja)を参照してください。

* **[タグマネージャーを使用しない Target の実装](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**:タグマネージャーを使用せずに Target を実装できます ( 例： [!DNL Adobe Experience Platform]) をクリックします。
* **サードパーティのタグマネージャーを使用した Target の実装**: [タグ [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) is the preferred method to implement Target; however, you can also implement Target using a third-party tag manager, including Tealium, Ensighten, and Google Tag. For a list of benefits of using Launch, see [Advantages of implementing at.js using the [!DNL Adobe Target] 拡張](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   ただし、 [!DNL Target] タグマネージャーがないと、サイトコード内で at.js をハードコーディングする代わりに、サードパーティのタグマネージャーを使用して簡単に実装できます。

   以下に、の実装に役立つ、2 つの関連トピックを示します [!DNL Target] サードパーティのタグマネージャーを使用する場合：

   * [実装する前に](/help/main/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [実装方法 [!DNL Target] タグマネージャーなし](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   詳しくは、サードパーティのタグマネージャーのドキュメントを参照してください。

実装するには [!DNL Target] シングルページアプリ (SPA) を使用する場合、 [シングルページアプリケーションの実装](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).
