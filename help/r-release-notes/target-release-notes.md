---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: f6efc1e921535abdd11501979d6f44e84e443a1f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 55%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 10 月 12 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## [!DNL Target Standard/Premium] 21.10.2（2021 年 10 月 14 日）

[!DNL Target] [!UICONTROL Audiences] を [!DNL Adobe Experience Platform Web SDK] と共に使用する際の機能強化：

* [!DNL Target] UI の様々な場所に、オーディエンスがソースで削除され、[!DNL Target] アクティビティで使用できなくなったことを示す警告アイコン、ポッバーおよびメッセージを追加しました。

   次の図は、アイコン、ポッパー、メッセージが表示される場所の一部を示しています。

   *  Activitylist ページ

      ![アクティビティリストページのソースメッセージで削除されたオーディエンス](assets/deleted-at-source-audiences-list.png)

   * アクティビティ [!UICONTROL  概要 ] ページ：

      ![概要ページのソースメッセージで削除されたオーディエンス](assets/deleted-at-source-overview.png)

   *  アクティビティ作成ワークフローのエクスペリエンスステップ：

      ![オーディエンスが Experiences ページのソースメッセージで削除  された](assets/deleted-at-source-experiences.png)

   *  アクティビティ作成ワークフローのターゲティングステップ：

      ![オーディエンスがターゲティングページのソースメッセージで削除  された](assets/deleted-at-source-targeting.png)

   * [!UICONTROL アクティビテ] ィ作成ワークフローの目標と設定ステップ：

      ![目標と設定ページのソースメッセージでオーディエ [!UICONTROL ンスが削除さ] れた](assets/deleted-at-source-goals-settings.png)

   * オーディエンスの絞り込み（アクティビティ作成ワークフローの [!UICONTROL  ターゲティング ] ステップで、オーディエンス ] を置き換える）:[!UICONTROL 

* オーディエンスを結合機能を使用しようとしたときに、いずれかのオーディエンスがソースで削除された場合、[!UICONTROL  保存 ] は無効になります。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
