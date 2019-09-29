---
description: Adobe I/O統合に目的の役割を持つすべてのワークスペースへのアクセス権を付与する方法に関する情報です。
keywords: 統合；ロール；ユーザー権限；管理コンソール
seo-description: 既存のAdobe I/O統合に対して、Adobe targetで目的の役割を持つすべてのワークスペースへのアクセス権を付与する方法に関する情報です
seo-title: Adobe I/O統合にワークスペースへのアクセス権を付与し、Adobe targetでロールを割り当てる
solution: 'Target '
subtopic: 導入
title: Adobe I/O統合にワークスペースへのアクセス権を付与し、ロールを割り当てる
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) Grant Adobe I/O integrations access to workspaces and assign roles

[!UICONTROL Enterprise権限を使用すると][!DNL Target] 、顧客は1つの組織を使用できますが、異なるチームやワークフロー用のワークスペースに分割できます。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

エンタープラ [!UICONTROL イズ権限機能は] 、チーム間で最適化プログラムを効果的に拡大/縮小するのを容易にします。 この機能はUIで使用できましたが、2019 [!DNL Target] 年の初めまでは、Admin APIに対応するサポートがありませんでした。 2019年2月のリリ [!DNL Target] ースでは、アドビが管理APIを更新し、統合アカウントを使用して組織で作成されたすべてのワークスペースにアクセスできるようになりました。 以前は、管理APIはデフォルトのワークスペースに制限されていましたが、2019年2月の更新では承認者アクセス権を持つすべてのワークスペースに対するアク [!UICONTROL セス権] が付与されました。

2019年9月のリリースでは、 [!DNL Target][!DNL Target] Enterprise Permissionsによって  、お客様に次のアクセス制御を提供します。

* 統合を適用できるワークスペースを選択できます
* Adobe I/O統合に次の役割を適用できます。承認 [!UICONTROL 者]、編 [!UICONTROL 集者]、監視 [!UICONTROL 者]。

この更新では、次の使用例がサポートされます。

* リソースを作成または編集する権限を持たないレポート作成用に、 [!UICONTROL Observer] （監視者）ロールを持つすべてのワークスペースにAdobe I/O統合アクセス権を付与します。
* Adobe I/O統合に適切な役割を持つ選択したワークスペースへのアクセス権を付与し、中央チームがAPIに基づく変更を行えるのは少数のワークスペースのみにします。
* APIを調査する準備が整った時点で、ワークスペースを所有する各チームに独自の統合を許可し、それに応じてロールを選択します。
* 上記のシナリオを組み合わせます。

**必要なアクション**:現在、すべてのワークスペースでリソース（アクティビティ、オーディエンス、オファーおよびレポート）に対するCRUD操作のAPIを利用しているお客様は、使用事例に従って、すべてのワークスペースに対して、既存のAdobe I/O統合アクセス権を付与する必要があります。 これを行うには、で各製品プロフ [!DNL Target] ァ [!UICONTROL イルを選択し] 、「統 [!DNL Adobe Admin Console] 合」タブで統合を追加 [!UICONTROL します] 。 9月のリリースより前は、「製品の役割」ドロップダウンリストで選択した [!UICONTROL 内容に関係なく、すべての] 統合が承認者  のアクセスを使用して操作されていました。 これで、目的のロールを選択できます。

>[!NOTE]
>
>この操作を実行しない場合、2019年9月のリリース以降、アクセス制御がアクティブになり、現在の設定がデフォルトのワークスペースのみである場合は、そのアクセス権が確認されます。 [!DNL Target] 事前に統合を設定しても、悪影響はありません。 この変更を早く行うほうが良い。 組織内のワークスペースの数に応じて、このプロセスでは、目的のロールを持つワークスペースに既存の統合を追加するのに数回のクリックしかかかりません。

**Adobe I/O統合にワークスペースへのアクセス権を付与し、ロールを割り当てるには：**

1. Adobe Admin Console **[を開きます](https://adminconsole.adobe.com)**。

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![Adobe Admin Consoleで製品を選択](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 目的のワークスペース（製品プロファイル）を選択します。

   ![製品プロファイルの選択](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![「統合」タブ](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. （条件付き）新しい統合を追加するには、「統合を追加 **[!UICONTROL 」をクリックし]**、目的の統合を選択して「保存」をクリック **[!UICONTROL します]**。

1. 「製品の役割 **[!UICONTROL 」ドロップダウンリスト]** で、そのワークスペースに対して目的の役割を選択します。

   * [!UICONTROL 承認者]
   * [!UICONTROL 編集者]
   * [!UICONTROL 監視者]
   ![製品プロファイルロールの選択](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
