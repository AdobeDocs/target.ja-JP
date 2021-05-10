---
keywords: 実装;at.js;JavaScript ライブラリ
description: Adobe Experience Platform Launchを使用する、またはタグマネージャーを使用せずに、Adobe [!DNL Target] at.js JavaScriptライブラリをデプロイする方法を説明します。
title: at.jsのデプロイ方法
feature: サーバー側での実装
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 32%

---

# at.js のデプロイ方法

Adobe Experience Platform Launchを使用する、またはタグマネージャーを使用せずに、Adobe TargetJavaScriptライブラリat.jsをデプロイする方法に関する情報です。

次の方法を使用して at.js をデプロイできます。

* **[ [!DNL Target]  を使用して を実装 [!DNL Platform Launch]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**：Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。
* **[タグマネージャーを使用しないターゲットの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**:タグマネージャー([!DNL Platform Launch])を使用せずにターゲットを実装できます。
* **サードパーティのタグマネージャーを使用したターゲットの実装**: [Adobe](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) の起動は、ターゲットを実装するのに推奨される方法です。ただし、Tealium、Ensighten、Googleタグなど、サードパーティのタグマネージャーを使用してターゲットを実装することもできます。Launchを使用する利点のリストについては、[ターゲット起動拡張を使用してat.jsを実装する利点](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304)を参照してください。

   ただし、タグマネージャーを使用せずに[!DNL Target]を導入する方法を知っていれば、サイトコードでat.jsをハードコードする代わりに、サードパーティのタグマネージャーを使用して簡単に導入できます。

   サードパーティのタグマネージャーとのターゲットの導入に役立つ2つの関連トピックを示します。

   * [実装する前に](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [タグマネージャーを使用しない Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   詳しくは、サードパーティのタグマネージャーのドキュメントを必ず確認してください。

シングルページアプリ（SPA）を使用する場合に Target を実装するには、「[シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。
