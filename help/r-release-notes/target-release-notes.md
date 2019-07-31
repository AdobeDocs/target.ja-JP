---
description: 最新または今後の[!DNL Adobe Target]リリースを参照してください。
keywords: リリースノート
seo-description: 最新または今後の[!DNL Adobe Target]リリースを参照してください。
seo-title: Adobe Targetリリースノート（プレリリース版）
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 48cb808283c9b2858e1bd041feb3fe8228253d6a

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019 年 7 月 31 日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## 発表

Enterprise Permissions allows [!DNL Target] customers to use a single organization, but divide it into workspaces for their different teams or workflows. これにより、チーム全体で最適化プログラムを効果的に拡大・縮小できます。Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier this year. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, Target Enterprise Permissions will provide customers with the following access controls:

* 統合を適用できるワークスペースを選択できます
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

この更新では、以下の使用例がサポートされます。

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Adobe I/Oの統合に適切な役割を持つワークスペースを選択することにより、チームは、少数のワークスペースでのAPIによる変更の実施を中央チームに許可します。
* ワークスペースを所有する各チームは、チームがAPIを参照できる準備が整っていて、それに応じてロールを選択するたびに、独自の統合を行うことを決定します。
* 上記のいずれかのシナリオをミックスして一致させます。

**必要なアクション**:現在、すべてのワークスペースのリソース（アクティビティ、オーディエンス、オファーおよびレポート）に対するAPIを利用している顧客の場合、すべてのワークスペースにおけるリソース（アクティビティ、オーディエンス、オファーおよびレポート）は、使用事例に従って、すべてのワークスペースへのアクセス権を付与する必要があります。You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, irrespective of choice made in the [!UICONTROL Product Role] drop-down list. これで、目的の役割を選択できます。

This action *must* be performed before September 4, 2019 to not face any disruption on your end. このアクションが実行されない場合、DNL Target99月リリースでは、アクセス制御がアクティブになり、現在設定されている場合にのみデフォルトのワークスペースへのアクセス権を確認できます。上記のガイドラインに従って、統合の設定に悪影響を及ぼすことはありません。この変更を早くすると、改善につながります。組織内のワークスペースの数によっては、これを設定するのに小さい時間が必要です。このプロセスでは、既存の統合をワークスペースに追加して、目的のロールを持つワークスペースに追加するだけで済みます。

## Target Standard／Premium 19.8.1（2019 年 8 月 20 日） {#tgt-19-8-1}

このメンテナンスリリースには、次の機能強化が含まれています。

* Visual Experience Composer（VEC）のリッチテキストエディター（RTE）へのセキュリティを含む、いくつかのセキュリティ修正が行われています。（TGT-35383）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
