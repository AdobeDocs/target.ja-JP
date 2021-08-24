---
keywords: 実装;at.js;JavaScript ライブラリ
description: Adobe Experience Platform Launchを使用する、またはタグマネージャーを使用せずに、Adobe [!DNL Target] at.js JavaScriptライブラリをデプロイする方法について説明します。
title: at.jsのデプロイ方法を教えてください。
feature: サーバー側の実装
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: 82629fb4c543220796fc99d9c034ebb725e1a645
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 6%

---

# at.js のデプロイ方法

[!DNL Adobe Experience Platform]内のタグを使用する、またはタグマネージャーを使用せずに、[!DNL Adobe Target] JavaScriptライブラリat.jsをデプロイする方法に関する情報です。

次の方法を使用して at.js をデプロイできます。

* **[ [!DNL Target]  [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**&#x200B;でタグを使用して実装する：のタグ [!DNL Adobe Experience Platform] は、の次世代タグ管理機能で [!DNL Adobe]す。タグを使用すると、顧客体験の実現に必要な分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] は、のデータ収集テクノロジーのスイートとしてリブランドされま [!DNL Adobe Experience Platform]した。その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。 用語の変更点の統合的な参照については、次の[ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)を参照してください。

* **[タグマネージャーを使用しないTargetの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**:タグマネージャーを使用せずにTargetを実装できます（例：のタグ） [!DNL Adobe Experience Platform]。
* **サードパーティのタグマネージャーを使用したTargetの実装**: [タグ [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) は、Targetを実装する推奨される方法です。ただし、Tealium、Ensighten、Googleタグなどのサードパーティのタグマネージャーを使用してTargetを実装することもできます。Launchを使用する利点のリストについては、 [!DNL Adobe Target] 拡張機能](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304)を使用してat.jsを実装するメリットを参照してください。[

   ただし、タグマネージャーを使用せずに[!DNL Target]を実装する方法がわかっている場合は、サイトコードでat.jsをハードコーディングする代わりに、サードパーティのタグマネージャーを使用して簡単に実装できます。

   サードパーティのタグマネージャーと共に[!DNL Target]を実装する際に役立つ、次の2つの関連トピックを紹介します。

   * [実装する前に](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [タグマネージャーを使用せずに [!DNL Target] を実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   詳しくは、サードパーティのタグマネージャーのドキュメントを確認してください。

シングルページアプリ(SPA)を使用する場合に[!DNL Target]を実装するには、[シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)を参照してください。
