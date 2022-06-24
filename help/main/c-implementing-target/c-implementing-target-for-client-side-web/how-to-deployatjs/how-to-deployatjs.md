---
keywords: 実装;at.js;JavaScript ライブラリ
description: Adobe [!DNL Target] Adobe Experience Platformのタグを使用する、またはタグマネージャーを使用しない、at.js JavaScript ライブラリ。
title: at.js のデプロイ方法を教えてください。
feature: Implement Server-side
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 29%

---

# at.js のデプロイ方法

のデプロイ方法に関する情報 [!DNL Adobe Target] JavaScript ライブラリ、at.js、タグを使用 [!DNL Adobe Experience Platform] またはタグマネージャーがない場合は、

次の方法を使用して at.js をデプロイできます。

* **[実装方法 [!DNL Target] タグの使用 [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}**:タグ [!DNL Adobe Experience Platform] は、 [!DNL Adobe]. タグは、適切な顧客体験の実現に必要な分析、マーケティングおよび広告タグをデプロイおよび管理するためのシンプルな手段を提供します。

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] は、[!DNL Adobe Experience Platform] のデータ収集テクノロジーのスイートとしてリブランドされました。その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。用語の変更に関する参照の一覧については、次の[ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=ja)を参照してください。

* **[タグマネージャーを使用しない Target の実装](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}**:タグマネージャーを使用せずに Target を実装できます ( 例： [!DNL Adobe Experience Platform]) をクリックします。
* **サードパーティのタグマネージャーを使用した Target の実装**: [タグ [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} is the preferred method to implement Target; however, you can also implement Target using a third-party tag manager, including Tealium, Ensighten, and Google Tag. For a list of benefits of using Launch, see [Advantages of implementing at.js using the [!DNL Adobe Target] 拡張](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank}。

   ただし、 [!DNL Target] タグマネージャーがないと、サイトコード内で at.js をハードコーディングする代わりに、サードパーティのタグマネージャーを使用して簡単に実装できます。

   以下に、の実装に役立つ、2 つの関連トピックを示します [!DNL Target] サードパーティのタグマネージャーを使用する場合：

   * [実装する前に](https://developer.adobe.com/target/before-implement/)
   * [ [!DNL Target] タグマネージャーを使用しない の実装](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)

   詳しくは、サードパーティのタグマネージャーのドキュメントを参照してください。

実装するには [!DNL Target] シングルページアプリ (SPA) を使用する場合、 [シングルページアプリケーションの実装](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/){target=_blank}。
