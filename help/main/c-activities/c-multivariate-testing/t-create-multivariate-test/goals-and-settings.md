---
keywords: アクティビティ設定；目標と設定；多変量分析；mvt
description: の [!UICONTROL Goals & Settings] ページを使用して、 [!DNL Adobe Target]  （MVT[!UICONTROL Multivariate Test] アクティビティの目標に関する情報を指定する方法を説明します。
title: '[!UICONTROL Multivariate Test] （MVT）アクティビティで目標と設定を指定するにはどうすればよいですか？'
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 38%

---

# 目標と設定（[!UICONTROL Multivariate Test]）

[!UICONTROL Goals & Settings] の [!DNL Adobe Target] ページでは、[!UICONTROL Multivariate Test] （MVT）アクティビティの目標に関する情報を入力します。

次のセクションを使用できます。

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

各セクションで使用できる設定は、レポートソースとして [!DNL Target] と [!DNL Analytics] のどちらを使用するかによって異なります。

## アクティビティの設定 {#section_DCBDC354261F420EBD4B43EA34947BAC}

以下の設定を使用できます。

### 目的

目的を入力します（オプション）。目的には、ユーザーやチームメンバーがキャンペーンを特定するのに役立つ任意の情報を指定できます。

### 優先度

の [!DNL Target] UI とオプションは、設定によっ [!UICONTROL Priority] 異なります。 従来の設定である [!UICONTROL Low]、[!UICONTROL Medium]、[!UICONTROL High] を使用するか、0～999 の細かい優先度を有効にすることができます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

[!UICONTROL Administration] > [!UICONTROL Reporting] （デフォルト）でこのオプションが有効になっていない場合は、優先度を [!UICONTROL Low]、[!UICONTROL Medium]、[!UICONTROL High] のいずれかに指定します。

詳細な優先度を有効にするには、[!UICONTROL Administration]/[!UICONTROL Reporting] をクリックし、「[!UICONTROL Enable Fine-Grained Priorities]」オプションを「オン」の位置に切り替えます。

このオプションが有効な場合は、0～999 の値を指定します。

* 0 = 低
* 999 = 高

以前のバージョンの [!DNL Target] で作成されたアクティビティの場合、[!UICONTROL Low] の優先度は 0 に変換され、[!UICONTROL Medium] の優先度は 5 に変換され、[!UICONTROL High] の優先度は 10 に変換されます。 これらの値は必要に応じて調整できます。

>[!NOTE]
>
>優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。

### 期間

アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。時間の選択では、24 時間制を使用し、00:00 は午前 0 時になります。 タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## レポート設定 {#section_13119392051044FBA6387D9B3B1C43CF}

以下の設定を使用できます。

### レポートソース

どのソリューション データを収集するかを指定します。

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

[&#x200B; アカウント設定 &#x200B;](/help/main/administrating-target/reporting.md) でレポートソリューションが指定されている場合、指定されたソリューションが使用され、この設定は表示されません。

アクティビティがライブになった後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。

**[!DNL Adobe Analytics]**: レポートソリューションの違いとそれぞれの利点について詳しくは [[!DNL Adobe Analytics]  のレポートソースとしての）  [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) を参照してください。

[!DNL Analytics] （A4T）のレポートソースとして [!DNL Target] を選択する場合は、アクティビティデータを受け取る [!DNL Analytics] レポートスイート [!DNL Target] 選択します。 これを行うには、まずアカウントが関連付けられている [!DNL Analytics] の会社のいずれかを選択し、次に、アクティビティに適したレポートスイートを選択します。 [!DNL Target] に接続するようにプロビジョニングされているレポートスイートのみを選択できます。 目的のレポートスイートが表示されない場合は、まずログアウトして [!DNL Adobe Experience Cloud] にログインし直し、もう一度試してください。 それでもリストにレポートスイートが表示されない場合は、[&#x200B; カスタマーケア &#x200B;](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) にお問い合わせください。

[!DNL Analytics for Target] （A4T）では、結果を正しく報告するためのトラッキングサーバーが必要です。 デフォルトのトラッキングサーバーが「[!UICONTROL Tracking Server]」フィールドに表示されます。 複数のトラッキングサーバーを使用する場合、このフィールドに正しいトラッキングサーバーを含めてください。 詳しくは [Analytics トラッキングサーバーの使用 &#x200B;](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) を参照してください。

**[!DNL Adobe Customer Journey Analytics]**: [[!DNL Target]  と  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) の統合について詳しくは、[!DNL Adobe Customer Journey Analytics] でのレポート [!DNL Target] を参照してください。

### 目標指標

目標達成の基準となる、訪問者の行動を選択します。例えば、[!UICONTROL Conversion] の指標を選択してから、成功を達成するタイミングを決定するパラメーターを設定します。

>[!NOTE]
>
>レポートソリューションが [!DNL Analytics] に設定されている場合、使用できる目標指標は [!UICONTROL Conversion] のみです。 指標 [!DNL Analytics] 目標として選択することはできません。

成功指標を選択したら、セレクターが表示されます。このセレクターを使用して、成功指標の具体的な内容を選択します。

有効になっている場合は、「[!UICONTROL Estimated Value of the Conversion]」フィールド（[!UICONTROL Page Score] 指標では使用できません）には他の指標の値ではなく、目標に関する値が示されます。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。すべての売上高指標（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales] および [!UICONTROL Orders]）について、予測には [!UICONTROL Revenue per Visitor] が使用されます。 データタイプは通貨です。

アクティビティの目標を達成した後も、その訪問者が優先度の高いアクティビティの対象となっている場合を除き、その訪問者には引き続きアクティビティコンテンツが表示されます。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。この動作は、[!DNL Target Classic] のデフォルトの動作とは異なります。デフォルトでは、テストが再度表示された場合は訪問者が新規としてカウントされます。

### 追加の指標

追加の成功指標を作成します。

この設定は、レポートソリューションが [!DNL Analytics] に設定されている場合は使用できません。 この場合、[!DNL Analytics] レポートスイート用に定義された指標が適用されます。

### レポート対象のオーディエンス

デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。レポート対象のオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。

### 詳細設定 {#section_E2FE441AFB324E498793ABB025ED9974}

[!UICONTROL Multivariate Test] の目標指標に対して詳細設定を使用できます。

![詳細設定メニュー](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。詳細設定オプションは使用できません。

#### この指標を増分する前に達成する必要がある成功指標はどれですか？

このオプションを使用すると、以前に別の成功指標に到達したユーザーのみを成功指標に到達するものとしてカウントできます。 例えば、テストコンバージョンが、訪問者がオファーをクリックした場合、または、コンバージョンする前に特定のページに到達する場合にのみ有効になることがあります。

複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。

両方（または複数）の成功指標を定義してから、成功指標を別の成功指標に依存させます。

[!UICONTROL Add Dependency] オプションを使用すると、別の成功指標に到達した場合または到達していない場合に、成功指標を増分できます。

依存関係を追加する手順は次のとおりです。

1. 指標を追加したら、「**[!UICONTROL Advanced Settings]**」をクリックします。
2. **[!UICONTROL Add Dependency]** のオプションをクリックします。

   ![依存関係を追加](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. 目的の指標を左側のペインから右側のペインにドラッグ&amp;ドロップし、「**[!UICONTROL Reached]**」をクリックして、「到達」と「未到達」の設定を切り替えます。

   ![依存関係に達する](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

追加した依存関係は後で編集または削除できます。

### ユーザーがこの目標指標に達した後、どうなりますか？

ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。

* カウ [!UICONTROL Select Increment Count & Keep User in Activity] トの増分方法を指定します。
* アクティビティに再エントリした場合にユーザーに表示されるエクスペリエンスを指定で [!UICONTROL Select Increment Count, Release User & Allow Reentry] ます。
* アクティビティコンテンツの代わりにユーザーに表示する内容を指定で [!UICONTROL Select Increment Count, Release User & Bar from Reentry] ます。

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## その他のメタデータ {#section_2E8917BEFB954480A4206B9E9E917F80}

以下の設定を使用できます。

### メモ

自分自身または他のチーム メンバーに役立つ、アクティビティに関する情報を入力します。 [!UICONTROL Notes] ペインはサイズ変更可能です。

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### アクティビティの設定（3:02）

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### 多変量分析テストの作成（9:25）

このビデオでは、[!DNL Target] の 3 ステップのガイド付きワークフローを使用して多変量分析テストを作成する方法を説明します。 目標と設定については 7:00 から説明します。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/29957?captions=jpn)
