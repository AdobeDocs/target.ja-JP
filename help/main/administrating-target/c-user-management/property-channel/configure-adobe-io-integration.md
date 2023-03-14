---
keywords: 統合;役割;ユーザー権限;admin console
description: Adobe Targetで目的の役割を持つすべてのAdobe I/Oに対して、既存のワークスペース統合へのアクセス権を付与する方法を説明します。
title: ワークスペースに対するAdobe I/Oアクセス権を付与し、役割を割り当てる方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 87%

---

# ワークスペースに対する Adobe I/O 統合のアクセス権の付与と役割の割り当て

[!UICONTROL エンタープライズ権限]を使用すると、[!DNL Target] のお客様は、単一の組織を使用できますが、その様々なチームやワークフロー用にワークスペースに分割できます。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/main/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

[!UICONTROL エンタープライズ権限]機能は、チームをまたいだ最適化プログラムの効果的な拡大を促進します。この機能は [!DNL Target] UI でのみ使用できましたが、Admin API には、2019 年初めまでは対応するサポートがありませんでした。[!DNL Target] 2019 年 2 月リリースで、アドビは、組織で作成したすべてのワークスペースに対して統合アカウントを使用できるように Admin API を更新しました。そのため、初期では、Admin API はデフォルトワークスペースのみに制限されていましたが、2019 年 2 月の更新で、[!UICONTROL 承認者]アクセス権を持つすべてのワークスペースに対してアクセス権が付与されました。

を使用 [!DNL Target] 2019 年 9 月リリース、 [!DNL Target] [!UICONTROL Enterprise 権限] は、お客様に対して次のアクセス制御を提供します。

* 統合を適用できるワークスペースを選択できます。
* Adobe I/O 統合（[!UICONTROL 承認者]、[!UICONTROL 編集者]または[!UICONTROL 監視者]）に役割を適用できます。

この更新では、次の使用例をサポートします。

* リソースの作成または編集権限なしでのレポート用に、[!UICONTROL 監視者]の役割を持つすべてのワークスペースに対して Adobe I/O 統合のアクセス権を付与する。
* 中央のチームがわずかなワークスペースにのみ API 主導の変更を加えることができるように、適切な役割を持つ、限定されたワークスペースに対して Adobe I/O 統合のアクセス権を付与する。
* チームが API を調査し、それに応じて役割を選択する準備ができたときはいつでも、ワークスペースを所有する各チームに、その独自の統合を持つことを許可する。
* 上記のシナリオの任意の組み合わせ。

**必要なアクション**：現在、すべてのワークスペースのリソース（アクティビティ、オーディエンス、オファーおよびレポート）の CRUD 操作に API を活用しているお客様は、その使用例ごとに、目的の役割を持つすべてのワークスペースに対して既存の Adobe I/O 統合のアクセス権を付与する必要があります。それには、[!DNL Adobe Admin Console] で各 [!DNL Target] [!UICONTROL 製品プロファイル]を選択し、「[!UICONTROL 統合]」タブで統合を追加します。9 月リリースより前は、[!UICONTROL 製品の役割]ドロップダウンリストでおこなった選択にかかわらず、すべての統合は[!UICONTROL 承認者]アクセス権を使用して操作していました。現在は、目的の役割を選択できます。

>[!NOTE]
>
>このアクションが実行されないと、[!DNL Target] 2019 年 9 月リリースの後、このアクセス制御がアクティブ化され、デフォルトワークスペース（現在設定されている場合）のみに対するアクセス権が観測されます。あらかじめ統合を設定することに対する副作用はありません。この変更をおこなうのは、早ければ早いほど良いです。組織内のワークスペースの数に応じて、このプロセスでは、目的の役割を持つワークスペースに既存の統合を追加するのに数クリックしかかかりません。

**ワークスペースに対する Adobe I/O 統合のアクセス権を付与し、役割を割り当てるには**

1. を開きます。 **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. 「**[!UICONTROL 製品]**」タブをクリックしてから、目的の製品の名前を選択します。

   ![Adobe Admin Console で製品を選択](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 目的のワークスペース（製品プロファイル）を選択します。

   ![製品プロファイルを選択](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. 「**[!UICONTROL 統合]**」タブをクリックします。

   ![「統合」タブ](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. （条件付き）新しい統合を追加するには、「**[!UICONTROL 統合を追加]**」をクリックし、目的の統合を選択して、「**[!UICONTROL 保存]**」をクリックします。

1. **[!UICONTROL 製品の役割]**&#x200B;ドロップダウンリストから、そのワークスペース用の目的の役割を選択します。

   | 役割 | 説明 |
   |--- |--- |
   | 承認者 | アクティビティの作成、編集、アクティブ化、停止ができます。 |
   | 編集者 | アクティビティの作成および編集（アクティブでない場合に限る）はできますが、アクティビティの開始を承認することはできません。 |
   | 監視者 | アクティビティを表示できますが、作成または編集はできません。 |
   | 発行者 | 監視者の役割と同様です（アクティビティを表示できますが、作成または編集はできません）。ただし、発行者の役割には、アクティビティをアクティブ化する追加の権限があります。 |
