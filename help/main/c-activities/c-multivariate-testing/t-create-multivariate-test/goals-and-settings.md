---
keywords: アクティビティ設定；目標と設定；多変量分析；mvt
description: の使用方法を学ぶ [!UICONTROL Goals & Settings] のページ [!DNL Adobe Target] の目標に関する情報を指定するには [!UICONTROL Multivariate Test] （MVT）アクティビティ。
title: で目標と設定を指定する方法 [!UICONTROL Multivariate Test] （MVT）アクティビティ？
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 41%

---

# 目標と設定（[!UICONTROL Multivariate Test]）

この [!UICONTROL Goals & Settings] のページ [!DNL Adobe Target] は、の目標に関する情報を入力する場所です [!UICONTROL Multivariate Test] （MVT）アクティビティ。

次のセクションを使用できます。

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

各セクションで使用できる設定は、を使用するかどうかによって異なります [!DNL Target] または [!DNL Analytics] をレポートソースとして使用します。

## アクティビティの設定 {#section_DCBDC354261F420EBD4B43EA34947BAC}

以下の設定を使用できます。

### 目的

目的を入力します（オプション）。目的には、ユーザーやチームメンバーがキャンペーンを特定するのに役立つ任意の情報を指定できます。

### 優先度

設定に応じて、 [!DNL Target] の UI とオプション [!UICONTROL Priority] 変化する。 の従来の設定を使用できます [!UICONTROL Low], [!UICONTROL Medium]、または [!UICONTROL High]または、0～999 の細かい優先度を有効にすることもできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

このオプションが有効になっていない場合 [!UICONTROL Administration] > [!UICONTROL Reporting] （デフォルト）。優先度を指定します。 [!UICONTROL Low], [!UICONTROL Medium]、または [!UICONTROL High].

詳細な優先度を有効にするには、をクリックします [!UICONTROL Administration] > [!UICONTROL Reporting]を切り替えます [!UICONTROL Enable Fine-Grained Priorities] 「オン」の位置へのオプション。

このオプションが有効な場合は、0～999 の値を指定します。

* 0 = 低
* 999 = 高

の以前のバージョンで作成されたアクティビティの場合 [!DNL Target], [!UICONTROL Low] 優先度は 0 に変換されます。 [!UICONTROL Medium] 優先度は 5 に変換されます。 [!UICONTROL High] 優先度は 10 に変換されます。 これらの値は必要に応じて調整できます。

>[!NOTE]
>
>優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。

### 期間

アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## レポート設定 {#section_13119392051044FBA6387D9B3B1C43CF}

以下の設定を使用できます。

### レポートソース

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

### 目標指標

目標達成の基準となる、訪問者の行動を選択します。例えば、 [!UICONTROL Conversion] 次に、成功を達成するタイミングを決定するパラメーターを設定します。

>[!NOTE]
>
>レポートソリューションがに設定されている場合 [!DNL Analytics]使用できる目標指標はのみです。 [!UICONTROL Conversion]. [!DNL Analytics] 指標は目標として選択できません。

成功指標を選択したら、セレクターが表示されます。このセレクターを使用して、成功指標の具体的な内容を選択します。

有効な場合、 [!UICONTROL Estimated Value of the Conversion] フィールド （ [!UICONTROL Page Score] （指標）は、他の指標の値ではなく、目標の値を提供します。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。すべての売上高指標（[!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales]、および [!UICONTROL Orders]）に設定する必要があります。 [!UICONTROL Revenue per Visitor]. データタイプは通貨です。

アクティビティの目標を達成した後も、その訪問者が優先度の高いアクティビティの対象となっている場合を除き、その訪問者には引き続きアクティビティコンテンツが表示されます。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。この動作は、のデフォルト動作とは異なります [!DNL Target Classic]。テストが再び表示された場合、訪問者を新規訪問者としてカウントします。

### 追加の指標

追加の成功指標を作成します。

この設定は、レポートソリューションがに設定されている場合は使用できません [!DNL Analytics]. この場合、指標は、 [!DNL Analytics] レポートスイートが適用されます。

### レポート対象のオーディエンス

デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。レポート対象のオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。

### 詳細設定 {#section_E2FE441AFB324E498793ABB025ED9974}

詳細設定は、次の場合に使用できます [!UICONTROL Multivariate Test] 目標指標。

![詳細設定メニュー](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。詳細設定オプションは使用できません。

#### この指標を増分する前に達成する必要がある成功指標はどれですか？

このオプションを使用すると、以前に別の成功指標に到達したユーザーのみを成功指標に到達するものとしてカウントできます。 例えば、テストコンバージョンが、訪問者がオファーをクリックした場合、または、コンバージョンする前に特定のページに到達する場合にのみ有効になることがあります。

複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。

両方（または複数）の成功指標を定義してから、成功指標を別の成功指標に依存させます。

この [!UICONTROL Add Dependency] オプションを使用すると、別の成功指標に達したか達していない場合に、成功指標を増分できます。

依存関係を追加する手順は次のとおりです。

1. 指標を追加したら、 **[!UICONTROL Advanced Settings]**.
2. 「」をクリックします **[!UICONTROL Add Dependency]** オプション：

   ![依存関係を追加](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. 目的の指標を左のペインから右のペインにドラッグ&amp;ドロップし、 **[!UICONTROL Reached]** 設定を「到達」と「未到達」に切り替えることができます。

   ![依存関係に達する](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

追加した依存関係は後で編集または削除できます。

### ユーザーがこの目標指標に達した後、どうなりますか？

ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。

* [!UICONTROL Select Increment Count & Keep User in Activity] カウントの増分方法を指定します。
* [!UICONTROL Select Increment Count, Release User & Allow Reentry] アクティビティに再度入った場合に表示されるエクスペリエンスを指定します。
* [!UICONTROL Select Increment Count, Release User & Bar from Reentry] アクティビティのコンテンツの代わりにユーザーに表示する内容を指定します。

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## その他のメタデータ {#section_2E8917BEFB954480A4206B9E9E917F80}

以下の設定を使用できます。

### メモ

自分自身または他のチーム メンバーに役立つ、アクティビティに関する情報を入力します。 この [!UICONTROL Notes] ペインはサイズ変更可能です。

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### アクティビティ設定（3:02）

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### 多変量分析テストの作成（9:25）

このビデオでは、を使用して多変量分析テストを作成する方法を説明します [!DNL Target] 3 ステップのガイドによるワークフロー 目標と設定に関する説明は 7:00 から始まります。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/17395)
