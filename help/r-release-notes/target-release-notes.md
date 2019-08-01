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
source-git-commit: e1174aacc5610878c8671e88fbd20d51fedffe6c

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

**2019年7月1日**

[!UICONTROL エンタープライズ権限] を使用すると [!DNL Target] 、顧客は単一の組織を使用できますが、異なるチームやワークフローのワークスペースに分割することができます。[!UICONTROL エンタープライズ権限] 機能により、チーム間で最適化プログラムを効率的に拡大・縮小できます。Although this feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until the [!DNL Target] February 2019 release. アドビは管理者APIを更新して、統合アカウントを使用して組織で作成されたすべてのワークスペースにアクセスできるようにしました。So, while earlier, Admin APIs were restricted to the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* 統合を適用できるワークスペースを選択できます
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

**Action Required**:現在、すべてのワークスペースのリソース（アクティビティ、オーディエンス、オファーおよびレポート）に対するAPIを利用している顧客は、目的のロールを持つすべてのワークスペースへの既存のAdobe I/O統合アクセス権を付与する必要があります。Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of the role selected from the [!UICONTROL Product Role] drop-down list. 今後のリリースで、目的の役割を選択できるようになりました。

This action should be performed during the month of **August 2019**. After the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. 統合の役割を事前に設定することに悪影響はありません。

For step-by-step instructions and more information, see [Grant Adobe I/O integrations access to workspaces and assign roles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard／Premium 19.8.1（2019 年 8 月 20 日） {#tgt-19-8-1}

このメンテナンスリリースには、次の機能強化が含まれています。

* Visual Experience Composer（VEC）のリッチテキストエディター（RTE）へのセキュリティを含む、いくつかのセキュリティ修正が行われています。（TGT-35383）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
