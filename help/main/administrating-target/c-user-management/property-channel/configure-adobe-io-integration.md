---
keywords: 統合;役割;ユーザー権限;admin console
description: Adobe Targetで必要なロールを持つすべてのワークスペースに対するアクセス権を既存のAdobe I/O統合に付与する方法を説明します。
title: Adobe I/Oにワークスペースへのアクセスを許可し、役割を割り当てる方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 61%

---

# ワークスペースに対する Adobe I/O 統合のアクセス権の付与と役割の割り当て

[!UICONTROL Enterprise Permissions] を使用すると、[!DNL Target] 顧客は単一の組織を使用できますが、異なるチームやワークフローのワークスペースに分割できます。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/main/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

[!UICONTROL Enterprise Permissions] の機能により、チーム間での最適化プログラムの効果的なスケーリングが容易になります。 この機能は [!DNL Target] UI でのみ使用できましたが、Admin API には、2019 年初めまでは対応するサポートがありませんでした。[!DNL Target] 2019 年 2 月リリースで、アドビは、組織で作成したすべてのワークスペースに対して統合アカウントを使用できるように Admin API を更新しました。そのため、以前は管理 API はデフォルトワークスペースのみに制限されていましたが、2019 年 2 月の更新では、[!UICONTROL Approver] しいアクセス権を持つすべてのワークスペースへのアクセスが許可されました。

2019 年 9 月 [!DNL Target] 日のリリースでは、[!DNL Target] [!UICONTROL Enterprise Permissions] はお客様に次のアクセス制御を提供します。

* 統合を適用できるワークスペースを選択できます。
* Adobe I/Oの統合（[!UICONTROL Approver]、[!UICONTROL Editor]、[!UICONTROL Observer]）に役割を適用できます。

この更新では、次の使用例をサポートします。

* リソースの作成または編集権限のない、レポート目的で [!UICONTROL Observer] ロールを持つすべてのワークスペースへのAdobe I/O統合アクセスを許可します。
* 中央のチームがわずかなワークスペースにのみ API 主導の変更を加えることができるように、適切な役割を持つ、限定されたワークスペースに対して Adobe I/O 統合のアクセス権を付与する。
* チームが API を調査し、それに応じて役割を選択する準備ができたときはいつでも、ワークスペースを所有する各チームに、その独自の統合を持つことを許可する。
* 上記のシナリオの任意の組み合わせ。

**必要なアクション**：現在、すべてのワークスペースのリソース（アクティビティ、オーディエンス、オファーおよびレポート）の CRUD 操作に API を活用しているお客様は、その使用例ごとに、目的の役割を持つすべてのワークスペースに対して既存の Adobe I/O 統合のアクセス権を付与する必要があります。これを行うには、[!DNL Target] で各 [!UICONTROL Product Profile] [!DNL Adobe Admin Console] を選択し、「[!UICONTROL Integration]」タブで統合を追加します。 9 月のリリース以前は、[!UICONTROL Approver] ドロップダウンリストでの選択に関係なく、すべての統合が [!UICONTROL Product Role] アクセスを使用して動作していました。 現在は、目的の役割を選択できます。

>[!NOTE]
>
>このアクションが実行されないと、[!DNL Target] 2019 年 9 月リリースの後、このアクセス制御がアクティブ化され、デフォルトワークスペース（現在設定されている場合）のみに対するアクセス権が観測されます。あらかじめ統合を設定することに対する副作用はありません。この変更をおこなうのは、早ければ早いほど良いです。組織内のワークスペースの数に応じて、このプロセスは数回クリックするだけで、既存の統合を目的の役割を持つワークスペースに追加できます。

**ワークスペースに対する Adobe I/O 統合のアクセス権を付与し、役割を割り当てるには**

1. **[Adobe Admin Console](https://adminconsole.adobe.com)** を開きます。

1. 「**[!UICONTROL Products]**」タブをクリックしてから、目的の製品名を選択します。

   ![Adobe Admin Console で製品を選択](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 目的のワークスペース（製品プロファイル）を選択します。

   ![製品プロファイルを選択](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. 「**[!UICONTROL Integrations]**」タブをクリックします。

   ![「統合」タブ](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. （条件付き）新しい統合を追加するには、「**[!UICONTROL Add Integration]**」をクリックし、目的の統合を選択して「**[!UICONTROL Save]**」をクリックします。

1. **[!UICONTROL Product Role]** ドロップダウンリストから、そのワークスペースに必要な役割を選択します。

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | 監視者の役割と同様です（アクティビティを表示できますが、作成または編集はできません）。ただし、発行者の役割には、アクティビティをアクティブ化する追加の権限があります。 |
