---
keywords: 統合;役割;ユーザー権限;admin console
description: 既存のAdobe I/O統合に、Adobe Targetで目的の役割を持つすべてのワークスペースへのアクセス権を付与する方法について説明します。
title: Adobe I/Oにワークスペースへのアクセス権を付与し、役割を割り当てるにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
TQID: https://experienceleague.adobe.com/8WUCeb4ztjDdWUEtawLYeC-4FDgn1SiGarmS1hqGNgI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: f7c7de77-382f-4f48-8b36-61a170f06d3d
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 623
ht-degree: 61%

---

# ワークスペースに対する Adobe I/O 統合のアクセス権の付与と役割の割り当て

[!UICONTROL Enterprise Permissions]では、[!DNL Target]人のお客様が単一の組織を使用できますが、それを異なるチームまたはワークフロー用のワークスペースに分割できます。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/main/c-intro/intro.md#premium) ソリューションの一部です。 [!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

[!UICONTROL Enterprise Permissions]機能は、チーム間での最適化プログラムの効果的な拡張を促進します。 この機能は [!DNL Target] UI でのみ使用できましたが、Admin API には、2019 年初めまでは対応するサポートがありませんでした。 [!DNL Target] 2019 年 2 月リリースで、アドビは、組織で作成したすべてのワークスペースに対して統合アカウントを使用できるように Admin API を更新しました。 以前は、Admin APIはデフォルトのワークスペースのみに制限されていましたが、2019年2月のアップデートにより、[!UICONTROL Approver] アクセス権を持つすべてのワークスペースへのアクセスが許可されました。

2019年9月リリースの[!DNL Target] [!UICONTROL Enterprise Permissions]では、次のアクセス制御をお客様に提供しています。[!DNL Target]

* 統合を適用できるワークスペースを選択できます。
* Adobe I/O統合にロールを適用できます：[!UICONTROL Approver]、[!UICONTROL Editor]または[!UICONTROL Observer]。

この更新では、次の使用例をサポートします。

* レポート用に[!UICONTROL Observer]の役割を持つすべてのワークスペースに対するAdobe I/O統合アクセス権を付与し、リソースを作成または編集する権限を付与しません。
* 中央のチームがわずかなワークスペースにのみ API 主導の変更を加えることができるように、適切な役割を持つ、限定されたワークスペースに対して Adobe I/O 統合のアクセス権を付与する。
* チームが API を調査し、それに応じて役割を選択する準備ができたときはいつでも、ワークスペースを所有する各チームに、その独自の統合を持つことを許可する。
* 上記のシナリオの任意の組み合わせ。

**必要なアクション**：現在、すべてのワークスペースのリソース（アクティビティ、オーディエンス、オファーおよびレポート）の CRUD 操作に API を活用しているお客様は、その使用例ごとに、目的の役割を持つすべてのワークスペースに対して既存の Adobe I/O 統合のアクセス権を付与する必要があります。 これを行うには、[!DNL Adobe Admin Console]で各[!DNL Target] [!UICONTROL Product Profile]を選択し、[!UICONTROL Integration] タブで統合を追加します。 9月のリリース以前は、[!UICONTROL Product Role] ドロップダウンリストで選択した内容に関係なく、すべての統合で[!UICONTROL Approver] アクセスが使用されていました。 現在は、目的の役割を選択できます。

>[!NOTE]
>
>このアクションが実行されないと、[!DNL Target] 2019 年 9 月リリースの後、このアクセス制御がアクティブ化され、デフォルトワークスペース（現在設定されている場合）のみに対するアクセス権が観測されます。 あらかじめ統合を設定することに対する副作用はありません。 この変更をおこなうのは、早ければ早いほど良いです。 組織内のワークスペースの数に応じて、このプロセスは、必要な役割を持つ既存の統合をワークスペースに追加するのに数回のクリックで完了します。

**ワークスペースに対する Adobe I/O 統合のアクセス権を付与し、役割を割り当てるには**

1. **[Adobe Admin Console](https://adminconsole.adobe.com)**&#x200B;を開きます。

1. 「**[!UICONTROL Products]**」タブをクリックし、目的の製品名を選択します。

   ![Adobe Admin Console で製品を選択](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 目的のワークスペース（製品プロファイル）を選択します。

   ![製品プロファイルを選択](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. 「**[!UICONTROL Integrations]**」タブをクリックします。

   ![「統合」タブ](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. （条件付き）新しい統合を追加するには、**[!UICONTROL Add Integration]**&#x200B;をクリックし、目的の統合を選択してから、**[!UICONTROL Save]**&#x200B;をクリックします。

1. **[!UICONTROL Product Role]** ドロップダウンリストから、そのワークスペースの目的の役割を選択します。

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | 監視者の役割と同様です（アクティビティを表示できますが、作成または編集はできません）。 ただし、発行者の役割には、アクティビティをアクティブ化する追加の権限があります。 |
