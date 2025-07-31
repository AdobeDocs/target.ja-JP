---
keywords: アクティビティ；アクティビティ；アクティビティタイプ；アクティビティの編集；編集；コピー
description: 既存のアクティビティを編集する様々な方法について説明します。
title: アクティビティを編集するには
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: 53bac4b1e778fb760a37e7287e0d8dbbe3a56b47
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 22%

---

# アクティビティの編集

[!DNL Adobe Target] の既存のアクティビティを編集する方法について説明します。 この記事では、[!DNL Target] インターフェイスで使用できる、アクティビティを変更するための様々な方法について説明します。 エクスペリエンスの更新、ターゲティングルールの調整、目標の設定などを行う場合でも、アクティブ化の前に変更 [!DNL Target] 安全に保存されます。

[!DNL Target] には、既存のアクティビティを編集できる UI の様々な場所が用意されています。 プロセスは、選択する方法によって異なります。

## アクティビティページでホバーアイコンを使用してアクティビティを編集 [!UICONTROL More Actions] ます {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. **[!UICONTROL Activities]** のページで、編集するアクティビティの横にある **[!UICONTROL More Actions]** アイコン ![ その他のアクションアイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックし、「[!UICONTROL **編集**]」をクリックします。

   アクティビティが [!DNL Target] （VEC）に開 [!UICONTROL Visual Experience Composer] れ、[!UICONTROL Experiences] のページが表示されます（3 ステップのガイド付きワークフローの最初のステップ）。

1. [VEC オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を使用して、目的に応じてアクティビティを編集します。

1. **[!UICONTROL Next]** をクリックして次の手順に進み、必要な編集を行います。

1. **目標と設定** ページには、次のオプションがあります。

   * **[!UICONTROL Save & Close]:** 「**[!UICONTROL Save and Close]**」をクリックして変更を保存し、アクティビティの [!UICONTROL Overview] ページを表示します。
   * **保存：** **[!UICONTROL More Actions]** のアイコン（![ その他のアクション アイコン ](/help/main/assets/icons/MoreSmallListVert.svg)）をクリックしてから「**[!UICONTROL Save]**」を選択すると、変更が保存され、VEC に残って引き続き変更を行うことができます。 保存が完了するまで待ってから次の変更作業に移ってください。保存が完了すると VEC が再読み込みされ、変更内容が反映されます。

## [!UICONTROL Activities] ページで名前をクリックして、アクティビティを編集します {#section_176180DAD17E40CEA441903F39E0AA1C}

1. ワークフローを 1 手順ずつ実行する必要をなくすには、目的のアクティビティを [!UICONTROL Activities] のページからクリックして開き、「**[!UICONTROL Edit Activity]**」ドロップダウンリストからオプションを選択して、目的のオプションを選択します。

   * **エクスペリエンスを編集：** エクスペリ [!UICONTROL Experiences] ンスのページ（3 ステップのガイド付きワークフローの最初のステップ）に直接移動します。
   * **ターゲティングを編集**:[!UICONTROL Targeting] ページ（3 ステップのガイドによるワークフローの 2 番目の手順）に直接移動します。
   * **[!UICONTROL Goals & Settings]**: [!UICONTROL Goals & Settings] ページに直接移動します（3 ステップのガイドによるワークフローの 3 ステップ目）。

1. 必要な変更を加え、アクティビティを保存します。

   * **[!UICONTROL Save & Close]:** 「**[!UICONTROL Save and Close]**」をクリックして変更を保存し、アクティビティの [!UICONTROL Overview] ページを表示します。
   * **保存：** **[!UICONTROL More Actions]** のアイコン（![ その他のアクション アイコン ](/help/main/assets/icons/MoreSmallListVert.svg)）をクリックしてから「**[!UICONTROL Save]**」を選択すると、変更が保存され、VEC に残って引き続き変更を行うことができます。 保存が完了するまで待ってから次の変更作業に移ってください。保存が完了すると VEC が再読み込みされ、変更内容が反映されます。

## ワークスペースを使用する際のアクティビティのコピー/編集 {#section_45A92E1DD3934523B07E71EF90C4F8B6}

ワークスペースを使用すると、組織は特定のユーザーのセットを特定のプロパティのセットに割り当てることができます。多くの点で、ワークスペースは [!DNL Adobe Analytics] のレポートスイートに似ています。

>[!NOTE]
>
>ワークスペースは、[!UICONTROL Properties and Permissions] ソリューションの一部として使用できる [!DNL Target Premium] 機能の一部です。 [!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

多国籍組織に属している場合、欧州向け Web ページ、プロパティまたはサイトのワークスペースと、米国向け Web ページ、プロパティまたはサイトの別のワークスペースがあるかもしれません。複数ブランドを取り扱う組織に属している場合、ブランドごとに別のワークスペースがあるかもしれません。

ワークスペースとエンタープライズユーザー権限機能について詳しくは、[ エンタープライズユーザー権限 ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838) を参照してください。

お使いの環境で [!UICONTROL Enterprise User Permissions] を有効にしている場合、アクティビティを同じワークスペースまたは別のワークスペースにコピーできます。 現時点では、アクティビティを別のワークスペースに移すことはできません。アクティビティを別のワークスペースにコピーするには、[!UICONTROL Activities] のページで、コピーするアクティビティの横にある **[!UICONTROL More Actions]** のアイコン（![ その他のアクション アイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックし、「[!UICONTROL **コピー**]」をクリックします。

ワークスペースでコピー／編集機能を使用する際の重要なポイントは次のとおりです。

* 同じワークスペース内またはデフォルトワークスペースからデフォルト以外のワークスペースにアクティビティをコピーすると、アクティビティウィザードが自動的に開きます。 ワークスペース間のコピーでは、アクティビティプロパティの更新のみが必要になる場合があります。
* アクティビティをデフォルト以外のワークスペースから別のワークスペース（デフォルトか非デフォルトかに関わらず）にコピーすると、アクティビティ ウィザードが開き、設定を完了するために手動の入力が必要になります。
   * **[!UICONTROL Properties]**: プロパティは、ワークスペース間で異なる場合があります。 この状況により、次の警告がトリガーされる場合があります。

      * [!UICONTROL Form-Based Experience Composer] では、警告はユーザーインターフェイス内に直接表示されるので、すぐに確認できます。

        ![ フォームベースのワークスペースの警告 ](/help/main/c-activities/assets/form-based-warning.png)

      * VEC では、[!UICONTROL Configure] > [!UICONTROL Properties] をクリックすると、警告が表示されます。

        ![vec-warning](/help/main/c-activities/assets/vec-warning.png)

        この問題を解決するには、[!UICONTROL Add/Remove] をクリックして、対象のワークスペースで使用可能なプロパティのみが選択対象として表示されるようにします。

   * **オーディエンスとオファー**：アクティビティを新しいワークスペースにコピーすると、関連するすべてのオーディエンスとオファーが、元のワークスペースから `Entity Name Copy <Date>` の形式で複製されます。

     動作の詳細：

      * コピーしたオーディエンスとオファーは、アクティビティを保存して再び開くまで、[!UICONTROL Audiences] ーディエンスと [!UICONTROL Offers] リストに表示されません。
      * これらのエンティティは、コピー後すぐに編集することはできません。 ユーザーには、最初の編集セッション中に、これらの項目に関する空のコンテンツが VEC に表示される場合があります。
      * 顧客は、必要に応じて、コピーしたオーディエンスやオファーを宛先ワークスペースの他のユーザーに置き換えることができます。

     このプロセスにより、カスタマイズの柔軟性を維持しながら、ワークスペース間のアクティビティの複製がよりスムーズになります。

     アクティビティをコピーする際、現在のワークスペースまたはデフォルトワークスペースのいずれにも保存されていない結合オーディエンス、非ターゲットオーディエンスおよびオファーは、手動で置き換える必要があります。

     これらの結合されたオーディエンス、非ターゲットオーディエンスおよびオファーを手動で置き換えると、コピーされたアクティビティでは、有効でアクセス可能なエンティティのみが使用され、編集や配信中のエラーが回避されます。

     ![ 警告メッセージ ](/help/main/c-activities/assets/copy.png)

>[!NOTE]
>
>環境で [!UICONTROL Enterprise User Permissions] 機能が有効になっていない場合、コピーする前にすべてのアクティビティが編集モードで開きます。

## ドラフトフォームでのアクティビティの保存 {#section_968CD7A63027432EBD8FAE3A0F7404C3}

[!UICONTROL Save as Draft] 機能は使用できなくなりました。 詳しくは、*[!UICONTROL Status]* アクティビティリストへのフィルターの適用 [ の ](/help/main/c-activities/activities.md#filters) を参照してください。

## [!DNL Recommendations Classic] で作成された従来のアクティビティの操作 {#classic}

[!UICONTROL Activities] リストには、[!DNL Recommendations Classic] を含む様々なソースで作成されたアクティビティが表示されます。 [!DNL Recommendations Classic] で作成した従来のアクティビティを使用する場合、次のアクションを使用できます。

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

[!DNL Recommendations] アクティビティを直接編集することはできません。アクティビティを編集する場合、[!DNL Target Premium] を使用してアクティビティのコピーを作成してから、新しく作成したアクティビティを保存する必要があります。この新しく作成したアクティビティは、必要に応じて編集できます。