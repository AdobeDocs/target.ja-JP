---
keywords: 実装;at.js;JavaScript ライブラリ
description: Adobe Experience Platform Launchを使用するか、タグマネージャーを使用しないで、at.js JavaScriptライブラリをAdobe Targetにデプロイする方法を説明します。
title: at.jsのデプロイ方法
feature: Implement Server-side
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 49%

---


# at.js のデプロイ方法

Adobe Target JavaScript ライブラリ（at.js）のデプロイ方法（Adobe Launch を使用してデプロイする方法、タグマネージャーを使用しないでデプロイする方法、Adobe Dynamic Tag Management（DTM）を使用してデプロイする方法）について説明します。

次の方法を使用して at.js をデプロイできます。

* **[Adobe Launch を使用して Target を実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**：Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。
* **[タグマネージャーを使用せずに Target を実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**：タグマネージャー（Adobe Launch または Dynamic Tag Management）を使用せずに、Target を実装できます。
* **[Dynamic Tag Managementを使用したターゲットの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md)**:AdobeのレガシータグマネージャーであるAdobeDynamic Tag Management(DTM)を使用して、ターゲットを実装できます。Adobe Launch は、Target および at.js ライブラリを実装するための、最新の推奨される方法です。Target を新たに実装する場合は、Launch を使用してください。
* **サードパーティのタグマネージャーを使用したターゲットの実装**: [Adobe](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) の起動は、ターゲットを実装するのに推奨される方法です。ただし、Tealium、Ensighten、Googleタグなど、サードパーティのタグマネージャーを使用してターゲットを実装することもできます。Launchを使用する利点のリストについては、[ターゲット起動拡張を使用してat.jsを実装する利点](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304)を参照してください。

   ただし、タグマネージャーを使用しないでターゲットを導入する方法を知っている場合は、サイトコードでat.jsをハードコードする代わりに、サードパーティのタグマネージャーを使用して簡単に実装できます。

   サードパーティのタグマネージャーとのターゲットの導入に役立つ2つの関連トピックを示します。

   * [実装する前に](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [タグマネージャーを使用しない Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   詳しくは、サードパーティのタグマネージャーのドキュメントを必ず確認してください。

シングルページアプリ（SPA）を使用する場合に Target を実装するには、「[シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。