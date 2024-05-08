---
keywords: アクティビティ設定;エクスペリエンスのターゲット設定目標と設定;xt目標と設定;エクスペリエンスのターゲット設定;レポート設定;目標指標;成功指標;従属成功指標;詳細設定;プライマリ目標;追加の指標;目的;優先度;期間;レポートソリューション;目標;レポートのオーディエンス;この指標を増分する前に達成する必要のある成功指標はどれですか;ユーザーがこの目標指標に達した後、どうなりますか;注意
description: の使用方法を学ぶ [!UICONTROL Goals & Settings] のページ [!DNL Adobe Target] の目標に関する情報を指定するには [!UICONTROL Experience Targeting] （XT）アクティビティ。
title: 指定方法 [!UICONTROL Goals & Settings] の場合 [!UICONTROL Experience Targeting] アクティビティ？
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 39%

---

# の目標と設定 [!UICONTROL Experience Targeting] （XT） アクティビティ

この [!UICONTROL Goals & Settings] ページでは、テストの目標に関する情報を入力します。

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

使用できる設定は、を使用するかどうかによって異なります [!DNL Target] または [!DNL Analytics] をレポートソースとして使用します。

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

以下の設定を使用できます。

### [!UICONTROL Objective]

目的を入力します（オプション）。目的には、ユーザーやチームメンバーがキャンペーンを特定するのに役立つ任意の情報を指定できます。

### [!UICONTROL Priority]

設定に応じて、 [!DNL Target] の UI とオプション [!UICONTROL Priority] 変化する。 の従来の設定を使用できます [!UICONTROL Low], [!UICONTROL Medium]、または [!UICONTROL High]または、0～999 の細かい優先度を有効にすることもできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。1 つの場所に複数のアクティビティが割り当てられている場合、最も優先度が高いアクティビティが表示されます。

このオプションが有効になっていない場合 [!UICONTROL Administration] （デフォルト）。優先度を指定します。 [!UICONTROL Low], [!UICONTROL Medium]、または [!UICONTROL High].

詳細な優先度を有効にするには、をクリックします **[!UICONTROL Administration]** > **[!UICONTROL Reporting]**&#x200B;を切り替えます [!UICONTROL Enable Fine-Grained Priorities] 「オン」の位置へのオプション。

このオプションが有効な場合は、0～999 の値を指定します。

* 0 = 低
* 999 = 高

の以前のバージョンで作成されたアクティビティの場合 [!DNL Target], [!UICONTROL Low] 優先度は 0 に変換されます。 [!UICONTROL Medium] は 5 に変換されます。 [!UICONTROL High] は 10 に変換されます。 これらの値は必要に応じて調整できます。

>[!NOTE]
>
>優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。

### [!UICONTROL Duration]

アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。同様に、アクティビティは、非アクティブ化されたときに終了することも、アクティビティが終了する日時を設定することもできます。 タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

以下の設定を使用できます。

### [!UICONTROL Reporting Source]

どのソリューション データを収集するかを指定します。

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

でレポートソリューションが指定されている場合 [アカウント設定](/help/main/administrating-target/reporting.md)：指定したソリューションが使用され、この設定は表示されません。

アクティビティがライブになった後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。

**[!DNL Adobe Analytics]**：を参照 [[!DNL Adobe Analytics] のレポートソースとしての [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) レポートソリューションの違いとそれぞれの利点について説明します。

選択時 [!DNL Analytics] のレポートソースとしての [!DNL Target] （A4T）の場合は、 [!DNL Analytics] 受信するレポートスイート [!DNL Target] アクティビティデータ。 これを行うには、まず [!DNL Analytics] アカウントが関連付けられている会社を選択し、アクティビティに適したレポートスイートを選択します。 に接続するようにプロビジョニングされているレポートスイートのみ [!DNL Target] を選択できます。 目的のレポートスイートが表示されない場合は、まずログアウトして、に再度ログインしてみてください [!DNL Adobe Experience Cloud] を再度実行してください。 それでもリストにレポートスイートが表示されない場合は、に連絡してください [カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] （A4T）結果を正しくレポートするには、トラッキングサーバーが必要です。 デフォルトのトラッキングサーバーはに表示されます。 [!UICONTROL Tracking Server] フィールド。 複数のトラッキングサーバーを使用する場合、このフィールドに正しいトラッキングサーバーを含めてください。 参照： [Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) を参照してください。

**[!DNL Adobe Customer Journey Analytics]**：を参照 [[!DNL Target] でのレポート [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) 間の統合について詳しくは、 [!DNL Adobe Customer Journey Analytics] および [!DNL Target].

### [!UICONTROL Goal Metric]

目標達成の基準となる、訪問者の行動を選択します。例えば、 [!UICONTROL Conversion] 次に、成功を達成するタイミングを決定するパラメーターを設定します。

指標の設定について詳しくは、[指標の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB)を参照してください。

>[!NOTE]
>
>レポートソリューションがに設定されている場合 [!DNL Analytics]使用できる目標指標はのみです。 [!UICONTROL Conversion]. [!DNL Analytics] 指標は目標として選択できません。

成功指標を選択したら、セレクターが表示されます。このセレクターを使用して、成功指標の具体的な内容を選択します。

有効な場合、 [!UICONTROL Estimated Value of the Conversion] フィールド （では使用できません） [!UICONTROL Page Score] （指標）は、他の指標の値ではなく、目標の値を提供します。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。すべての売上高指標（[!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales]、および [!UICONTROL Orders]）に設定する必要があります。 [!UICONTROL Revenue per Visitor]. データタイプは通貨です。

アクティビティの目標を達成した後も、その訪問者が優先度の高いアクティビティの対象となっている場合を除き、その訪問者には引き続きアクティビティコンテンツが表示されます。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。この動作は、のデフォルト動作とは異なります [!DNL Target Classic]。テストが再び表示された場合、訪問者は新規としてカウントされます。

### [!UICONTROL Additional Metrics]

追加の成功指標を作成します。

この設定は、レポートソリューションがに設定されている場合は使用できません [!DNL Analytics]. この場合、指標は、 [!DNL Analytics] レポートスイートが適用されます。

### [!UICONTROL Audiences for Reporting]

デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。レポート対象のオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。

この設定は、次のいずれかを選択した場合は利用できません。 [!DNL Analytics] をレポートソリューションとして使用します。 に対して定義されたオーディエンス [!DNL Analytics] レポートスイートが適用されます。

## [!UICONTROL Other Meta Data]

自分自身または他のチーム メンバーに役立つ、アクティビティに関する情報を入力します。 この [!UICONTROL Notes] ペインはサイズ変更可能です。

## [!UICONTROL Advanced Settings] {#section_E2FE441AFB324E498793ABB025ED9974}

詳細設定は、次の場合に使用できます [!UICONTROL Experience Targeting] 目標指標。

![詳細設定](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>[!DNL Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。この [!UICONTROL Advanced Settings] オプションは使用できません。

以下の設定を使用できます。

### [!UICONTROL Which success metric must be reached before incrementing this metric?]

異なる成功指標に以前に到達した訪問者のみを成功指標にカウントする場合は、このオプションを使用します。 例えば、テストコンバージョンが、訪問者がコンバージョン前にオファーをクリックした場合や特定のページに到達した場合にのみ有効になることがあります。

複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。

成功指標の依存関係を設定する前に、両方（または複数）の成功指標を定義する必要があります。

この [!UICONTROL Add Dependency] オプションを使用すると、別の成功指標に達したか達していない場合に、成功指標を増分できます。

依存関係を追加する手順は次のとおりです。

1. 指標を追加したら、 **[!UICONTROL Advanced Settings]**.
2. クリック **[!UICONTROL Add Dependency]**:

   ![依存関係を追加リンク](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. 目的の指標を左のペインから右のペインにドラッグ&amp;ドロップし、 **[!UICONTROL Reached]** 設定を切り替えるには [!UICONTROL Reached] および [!UICONTROL Not Reached].

   ![指標依存関係を追加ダイアログボックス](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

追加した依存関係は後で編集または削除できます。

### [!UICONTROL What will happen after a user encounters this goal metric?]

ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。

* を選択 [!UICONTROL Increment Count & Keep User in Activity] カウントの増分方法を指定します。
* を選択 [!UICONTROL Increment Count, Release User & Allow Reentry] アクティビティに再度入った場合に表示されるエクスペリエンスを指定します。
* を選択 [!UICONTROL Increment Count, Release User & Bar from Reentry] アクティビティのコンテンツの代わりにユーザーに表示する内容を指定します。

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## トレーニングビデオ：アクティビティの設定（3:02）

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
