---
keywords: アクティビティ;アクティビティ;アクティビティタイプ;アクティビティの編集;編集;ドラフト
description: ドラフトフォームでのアクティビティの保存など、Adobe Targetで既存のアクティビティを編集する様々な方法について説明します。
title: アクティビティを編集したり、ドラフトとして保存したりするにはどうすればよいですか？
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 52%

---

# アクティビティを編集またはドラフトとして保存

ドラフトフォームでのアクティビティの保存など、[!DNL Adobe Target] で既存のアクティビティを編集する様々な方法に関する情報です。

Target では、UI 内の様々な場所で既存のアクティビティを編集できます。編集方法によって手順は変わります。

## アクティビティページでホバーボタンを使用してアクティビティを編集します {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. **[!UICONTROL Activities]** ページで、編集するアクティビティの上にマウスポインターを置き、「**[!UICONTROL Edit]**」アイコンをクリックします。

   ![編集アイコン](/help/main/c-activities/assets/hover_edit.png)

   Target を使用すると、Visual Experience Composer （VEC）でアクティビティが開き、[!UICONTROL Experiences] のページが表示されます（3 ステップのガイド付きワークフローの最初の手順）。

1. [VEC オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を使用して、目的に応じてアクティビティを編集します。

1. 分割ボタンを使用して、次の手順に進むか、アクティビティを保存します。

   ![分割ボタン](/help/main/c-activities/assets/edit_split_button_2.png)

   * **次へ：** 3 ステップのワークフローで別のページを編集するには、「**[!UICONTROL Next]**」をクリックして目的のステップに進みます。 例えば、上の図では、「」をクリックすると、[!UICONTROL Targeting] の手順 [!UICONTROL Next] 表示されます。
   * **保存して閉じる：** 現在のステップで必要な変更を行い、分割ボタンのドロップダウンをクリックしてから、「**[!UICONTROL Save and Close]**」を選択して変更を保存し、アクティビティの [!UICONTROL Overview] ページを表示します。
   * **保存：** ステップで必要な変更を加え、分割ボタンのドロップダウンをクリックしてから、「**[!UICONTROL Save]**」を選択して変更を保存します。そのステップでは、引き続き変更を加えることができます。 保存が完了するまで待ってから次の変更作業に移ってください。保存が完了すると VEC が再読み込みされ、変更内容が反映されます。

## アクティビティページで名前をクリックしてアクティビティを開き、アクティビティを編集する {#section_176180DAD17E40CEA441903F39E0AA1C}

1. ワークフローの手順を追う必要をなくすには、アクティビティ ページから目的のアクティビティをクリックして開き、「**[!UICONTROL Edit Activity]**」ドロップダウンリストからオプションを選択します。

   ![アクティビティを編集ドロップダウン](/help/main/c-activities/assets/edit_activity.png)

1. 選択できるオプションは次のとおりです。

   * **エクスペリエンスを編集：** エクス [!UICONTROL Experiences] リエンスページに直接移動します（ガイド付きワークフローの最初の手順）。 必要な変更を加えたら、上述のスプリットボタンを使用してアクティビティを保存します。

      * 「**[!UICONTROL Save & Close]**」をクリックして変更を保存し、アクティビティの概要ページを表示します。
      * 「**[!UICONTROL Save]**」をクリックして変更を保存し、その手順に進んで引き続き変更を加えることができます。 保存が完了するまで待ってから次の変更作業に移ってください。保存が完了すると VEC が再読み込みされ、変更内容が反映されます。

   * **ターゲティングを編集：** ターゲティング [!UICONTROL Targeting] ページ（ガイド付きワークフローの 2 番目の手順）に直接移動します。 必要な変更を加えたら、上述のスプリットボタンを使用してアクティビティを保存します。

      * 「**[!UICONTROL Save & Close]**」をクリックして変更を保存し、アクティビティの概要ページを表示します。
      * 「**[!UICONTROL Save]**」をクリックして変更を保存し、その手順に進んで引き続き変更を加えることができます。 保存が完了するまで待ってから次の変更作業に移ってください。保存が完了すると VEC が再読み込みされ、変更内容が反映されます。

   * **目標と設定を編集：**&#x200B;[!UICONTROL Goals & Settings] ページ（ガイド付きワークフローの最後の手順）に直接移動します。 必要な変更を加えたら、上述のスプリットボタンを使用してアクティビティを保存します。

      * 「**[!UICONTROL Save & Close]**」をクリックして変更を保存し、アクティビティの概要ページを表示します。
      * 「**[!UICONTROL Save]**」をクリックして変更を保存し、その手順に進んで引き続き変更を加えることができます。 保存が完了するまで待ってから次の変更作業に移ってください。保存が完了すると VEC が再読み込みされ、変更内容が反映されます。

## Recommendations Classic で作成された従来のアクティビティの操作 {#classic}

[!UICONTROL Activities] リストには、[!DNL Recommendations Classic] を含む様々なソースで作成されたアクティビティが表示されます。 [!DNL Recommendations Classic] で作成した従来のアクティビティを使用する場合、次のアクションを使用できます。

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

[!DNL Recommendations] アクティビティを直接編集することはできません。アクティビティを編集する場合、[!DNL Target Premium] を使用してアクティビティのコピーを作成してから、新しく作成したアクティビティを保存する必要があります。この新しく作成したアクティビティは、必要に応じて編集できます。

## ドラフトフォームでのアクティビティの保存 {#section_968CD7A63027432EBD8FAE3A0F7404C3}

まだ保存されていない新しいアクティビティを作成しているときや、以前にドラフトとして保存されたアクティビティを編集しているときは、スプリットボタンに「ドラフトを保存」オプションが表示されます。

設定を開始したものの、まだ実行する準備が整っていないアクティビティは、ドラフトとして保存できます。

1. 新しいアクティビティを作成するか、ドラフト形式の既存のアクティビティを編集します。
1. スプリットボタンから目的のオプションを選択します。

   ![ドラフトとして保存](/help/main/c-activities/assets/save_draft.png)

   * **次へ：** 3 ステップのワークフローで別のページを編集するには、「**[!UICONTROL Next]**」をクリックして目的のステップに進みます。
   * **ドラフトを保存して閉じる：** 現在のステップで必要な変更を行い、分割ボタンのドロップダウンをクリックします。次に、「**[!UICONTROL Save Draft and Close]**」を選択して変更を保存し、アクティビティの [!UICONTROL Overview] ページを表示します。
   * **ドラフトを保存：** ステップで必要な変更を加え、分割ボタンのドロップダウンをクリックして「**[!UICONTROL Save Draft]**」を選択すると、変更が保存され、そのステップから移動できなくなります。

## ワークスペースを使用している際にアクティビティをコピー／編集する {#section_45A92E1DD3934523B07E71EF90C4F8B6}

ワークスペースを使用すると、組織は特定のユーザーのセットを特定のプロパティのセットに割り当てることができます。多くの点で、ワークスペースは [!DNL Adobe Analytics] のレポートスイートに似ています。

>[!NOTE]
>
>ワークスペースは、[!DNL Target Premium] ソリューションの一部として利用できるプロパティと権限機能に含まれています。[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では利用できません。

多国籍組織に属している場合、欧州向け Web ページ、プロパティまたはサイトのワークスペースと、米国向け Web ページ、プロパティまたはサイトの別のワークスペースがあるかもしれません。複数ブランドを取り扱う組織に属している場合、ブランドごとに別のワークスペースがあるかもしれません。

ワークスペースとエンタープライズユーザー権限機能について詳しくは、[ エンタープライズユーザー権限 ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838) を参照してください。

環境内で Enterprise ユーザーの権限が有効になっている場合は、同一または別のワークスペースにアクティビティをコピーできます。現時点では、アクティビティを別のワークスペースに移すことはできません。アクティビティを別のワークスペースにコピーするには、[!UICONTROL Activities] のページで、コピーするアクティビティの上にマウスポインターを置いて [!UICONTROL Copy] アイコンをクリックし、ドロップダウンリストから目的のワークスペースを選択します。

ワークスペースでコピー／編集機能を使用する際の重要なポイントは次のとおりです。

* 同一のワークスペース内でアクティビティをコピーするときは、新たにコピーされるアクティビティの作成フローの最初のステップが編集モードで開きます。
* アクティビティを別のワークスペースにコピーするときは、アクティビティの作成フローが開かずにコピーされます。アクティビティが正常にコピーされたら、そのことを示すメッセージが表示されます。このメッセージには、その新しいアクティビティを開くリンクも含まれています。

環境内で Enterprise ユーザー権限が有効になっていない場合は、コピーの前に、すべてのアクティビティが編集モードで開きます。

## ベストプラクティス

* ベストプラクティスとして、最初にアクティビティを作成した際と同じアクティビティ（UI またはAPI）を使用して、メソッドを更新してみてください。

  [!DNL Target] UI を使用して作成されたアクティビティは、[!DNL Target] UI から更新する必要があります。 API を使用して作成されたアクティビティは、API から更新する必要があります。例えば、最初に API を使用してアクティビティを作成した後、後で [!DNL Target] UI を使用してアクティビティを編集した場合、すべての変更が更新されるわけではありません。 すべての変更はバックエンドに保存され、別の API 呼び出しを行うことで更新できます。


