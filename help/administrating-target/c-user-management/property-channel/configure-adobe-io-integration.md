---
description: 既存のAdobe I/O統合を許可することに関する情報は、目的のロールを持つすべてのワークスペースにアクセスできます。
keywords: 統合;役割;ユーザー権限;admin console
seo-description: 既存のAdobe I/O統合を許可することに関する情報は、Adobe Targetで目的のロールを持つすべてのワークスペースにアクセスできます
seo-title: Adobe I/O統合のワークスペースへのアクセス権の付与、およびAdobe Targetでのロールの割り当て
solution: 'Target '
subtopic: 導入
title: Adobe I/O統合のワークスペースへのアクセス権の付与およびロールの割り当て
translation-type: tm+mt
source-git-commit: b88460fbd90168ddc19cbae1939b47ac69a854a8

---


# ![Premium](/help/assets/premium.png) : Adobe I/O統合のワークスペースへのアクセス権の付与およびロールの割り当て

[!UICONTROL エンタープライズ権限] を使用すると [!DNL Target] 、顧客は単一の組織を使用できますが、異なるチームやワークフローのワークスペースに分割することができます。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

[!UICONTROL エンタープライズ権限] 機能により、チーム間で最適化プログラムを効率的に拡大・縮小できます。Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier in 2019. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* 統合を適用できるワークスペースを選択できます
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

このアップデートでは、次の使用例をサポートしています。

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Adobe I/Oの統合に適切な役割を持つワークスペースを選択することにより、チームは、少数のワークスペースでのAPIによる変更の実施を中央チームに許可します。
* チームがAPIを参照できるように準備されていて、それに応じてロールを選択するたびに、ワークスペース所有者ごとに独自の統合を許可する。
* 上記のいずれかのシナリオをミックスして一致させます。

**必要なアクション**:現在、すべてのワークスペースのリソース（アクティビティ、オーディエンス、オファーおよびレポート）に対するAPIを利用している顧客の場合、すべてのワークスペースにおけるリソース（アクティビティ、オーディエンス、オファーおよびレポート）は、使用事例に従って、すべてのワークスペースへのアクセス権を付与する必要があります。You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of choice made from the [!UICONTROL Product Role] drop-down list. これで、目的の役割を選択できます。

This action should be performed before **September 4, 2019** to not face any disruption on your end. If this action is not performed, after the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. 上記のガイドラインに従って、統合の設定に悪影響を及ぼすことはありません。この変更を早くすると、改善につながります。組織内のワークスペースの数によっては、これを設定するのに小さい時間が必要です。このプロセスでは、既存の統合をワークスペースに追加して、目的のロールを持つワークスペースに追加するだけで済みます。

**Adobe I/O統合にワークスペースへのアクセス権を付与し、ロールを割り当てるには:**

1. Open the **[!DNL[Adobe Admin Console](https://adminconsole.adobe.com)]**.

1. **[!UICONTROL 「製品]** 」タブをクリックし、目的の製品の名前を選択します。

   ![Adobe Admin Consoleで製品を選択](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 目的のワークスペース（製品プロファイル）を選択します。

   ![製品プロファイルの選択](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. **[!UICONTROL 「統合]** 」タブをクリックします。

   ![「統合」タブ](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. **[!UICONTROL 製品の役割]** ドロップダウンリストから、そのワークスペースに対して目的のロールを選択します。

   *[!UICONTROL Approver]
*[!UICONTROL Editor]
*[!UICONTROL Observer]

   ![製品プロファイルの役割の選択](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)