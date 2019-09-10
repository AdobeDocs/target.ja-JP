---
description: Adobe I/O統合を許可することに関する情報は、目的のロールを持つすべてのワークスペースにアクセスできます。
keywords: 統合;役割;ユーザー権限;admin console
seo-description: 既存のAdobe I/O統合を許可することに関する情報は、Adobe Targetで目的のロールを持つすべてのワークスペースにアクセスできます
seo-title: Adobe I/O統合のワークスペースへのアクセス権の付与、およびAdobe Targetでのロールの割り当て
solution: 'Target '
subtopic: 導入
title: Adobe I/O統合のワークスペースへのアクセス権の付与およびロールの割り当て
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![Premium](/help/assets/premium.png) : Adobe I/O統合のワークスペースへのアクセス権の付与およびロールの割り当て

[!UICONTROL エンタープライズ権限] を使用すると [!DNL Target] 、顧客は単一の組織を使用できますが、異なるチームやワークフローのワークスペースに分割することができます。

>[!NOTE]
>
>プロパティと権限の機能は [Target Premium](/help/c-intro/intro.md#premium) ソリューションの一部です。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

[!UICONTROL エンタープライズ権限] 機能により、チーム間で最適化プログラムを効率的に拡大・縮小できます。この機能は [!DNL Target] UIで使用できましたが、管理APIは2019年の以前のサポートに対応していません。2019 [!DNL Target] 年2月のリリースでは、アドビは管理者APIを更新して、統合アカウントを使用して組織で作成されたすべてのワークスペースにアクセスできるようにしました。したがって、管理者APIはデフォルトのワークスペースのみに制限されていましたが、2019年2月アップデートで [!UICONTROL は承認者] アクセスを持つすべてのワークスペースへのアクセス権が付与されました。

2019 [!DNL Target] 年9月のリリースで [!DNL Target][!UICONTROL は、Enterprise権限] により次のアクセス制御をお客様に提供します。

* 統合を適用できるワークスペースを選択できます
* Adobe I/O統合にロールを適用できます。 [!UICONTROL 承認者]、 [!UICONTROL エディター]または [!UICONTROL 監視者]。

このアップデートでは、次の使用例をサポートしています。

* Adobe I/Oの統合アクセスに、リソースを作成または編集する権利を持たない、レポート目的の [!UICONTROL すべて] のワークスペースへの統合アクセス権を付与します。
* Adobe I/Oの統合に適切な役割を持つワークスペースを選択することにより、チームは、少数のワークスペースでのAPIによる変更の実施を中央チームに許可します。
* チームがAPIを参照できるように準備されていて、それに応じてロールを選択するたびに、ワークスペース所有者ごとに独自の統合を許可する。
* 上記のいずれかのシナリオをミックスして一致させます。

**必要なアクション**:現在、すべてのワークスペースのリソース（アクティビティ、オーディエンス、オファーおよびレポート）に対するAPIを利用している顧客の場合、すべてのワークスペースにおけるリソース（アクティビティ、オーディエンス、オファーおよびレポート）は、使用事例に従って、すべてのワークスペースへのアクセス権を付与する必要があります。そのためには、「統合」タブで [!DNL Target][!UICONTROL 各製品プロファイル] を選択 [!DNL Adobe Admin Console] し、統合を [!UICONTROL 追加します。]9月のリリースより前に、製品の役割ドロップダウンリストからの選択にかかわらず [!UICONTROL 、承認者] のアクセスを使用して操作した [!UICONTROL すべての統合] が実行されます。これで、目的の役割を選択できます。

>[!NOTE]
>
>このアクションが実行されない場合は [!DNL Target] 、2019年9月リリース以降、アクセスコントロールがアクティブになり、現在設定されている場合にのみデフォルトのワークスペースへのアクセス権が表示されます。統合の設定に悪影響はありません。この変更を早くすると、改善につながります。組織内のワークスペースの数によっては、このプロセスでは、既存の統合を目的のロールを持つワークスペースに追加するためのクリック数が数回しかかかりません。

**Adobe I/O統合にワークスペースへのアクセス権を付与し、ロールを割り当てるには:**

1. **[Adobe Admin Consoleを開き](https://adminconsole.adobe.com)**&#x200B;ます。

1. **[!UICONTROL 「製品]** 」タブをクリックし、目的の製品の名前を選択します。

   ![Adobe Admin Consoleで製品を選択](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 目的のワークスペース（製品プロファイル）を選択します。

   ![製品プロファイルの選択](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. **[!UICONTROL 「統合]** 」タブをクリックします。

   ![「統合」タブ](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. （条件付き）新しい統合を追加するには、「統合 **[!UICONTROL を追加»をクリック??し、目的の統合を選択して、??«保存??]******

1. **[!UICONTROL 製品の役割]** ドロップダウンリストから、そのワークスペースに対して目的のロールを選択します。

   * [!UICONTROL 承認者]
   * [!UICONTROL 編集者]
   * [!UICONTROL 監視者]
   ![製品プロファイルの役割の選択](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
