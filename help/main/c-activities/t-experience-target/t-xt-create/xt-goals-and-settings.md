---
keywords: アクティビティ設定;エクスペリエンスのターゲット設定目標と設定;xt目標と設定;エクスペリエンスのターゲット設定;レポート設定;目標指標;成功指標;従属成功指標;詳細設定;プライマリ目標;追加の指標;目的;優先度;期間;レポートソリューション;目標;レポートのオーディエンス;この指標を増分する前に達成する必要のある成功指標はどれですか;ユーザーがこの目標指標に達した後、どうなりますか;注意
description: ' [!DNL Adobe Target] の[!UICONTROL 目標と設定] ページを使用して、[!UICONTROL  エクスペリエンスのターゲット設定] （XT）アクティビティの目標に関する情報を指定する方法を説明します。'
title: '[!UICONTROL  エクスペリエンスのターゲット設定] アクティビティで[!UICONTROL 目標と設定]を指定するにはどうすればよいですか？'
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
TQID: https://experienceleague.adobe.com/vlpJSJ4Z6mxQI-D8UyUPEXHVWKfR54l89uoxULd2oD0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1285
ht-degree: 42%

---

# [!UICONTROL  エクスペリエンスのターゲット設定] （XT）アクティビティの目標と設定

[!UICONTROL 目標と設定] ページでは、テストの目標に関する情報を入力します。

* [!UICONTROL アクティビティの設定]
* [!UICONTROL レポート設定]
* [!UICONTROL その他のメタデータ]

使用可能な設定は、レポートソースとして[!DNL Target]または[!DNL Analytics]を使用するかどうかに応じて異なります。

## [!UICONTROL アクティビティの設定] {#section_DCBDC354261F420EBD4B43EA34947BAC}

以下の設定を使用できます。

### [!UICONTROL 目標]

目的を入力します（オプション）。 目的には、ユーザーやチームメンバーがキャンペーンを特定するのに役立つ任意の情報を指定できます。

### [!UICONTROL 優先順位]

設定に応じて、[!UICONTROL 優先度]の[!DNL Target] UIとオプションが異なります。 [!UICONTROL Low]、[!UICONTROL Medium]または[!UICONTROL High]の従来の設定を使用するか、0 ～ 999の細かい優先度を有効にできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 2つ以上のアクティビティが場所に割り当てられている場合、優先度が最も高いアクティビティが表示されます。

このオプションが[!UICONTROL 管理] （デフォルト）で有効になっていない場合は、優先度を[!UICONTROL 低]、[!UICONTROL Medium]、または[!UICONTROL 高]に指定します。

きめ細かい優先度を有効にするには、**[!UICONTROL 管理]** > **[!UICONTROL レポート]**&#x200B;をクリックし、[!UICONTROL きめ細かい優先度を有効にする] オプションを「オン」の位置に切り替えます。

このオプションが有効になっている場合は、0 ～ 999の値を指定します。

* 0 = 低
* 999 = 高

以前のバージョンの[!DNL Target]で作成されたアクティビティの場合、[!UICONTROL 低]の優先度は0に変換され、[!UICONTROL Medium]は5に変換され、[!UICONTROL 高]は10に変換されます。 これらの値は必要に応じて調整できます。

>[!NOTE]
>
>優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。

### [!UICONTROL 期間]

アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。 同様に、アクティビティが非アクティブ化されたときに終了したり、アクティビティの終了日時を設定したりできます。 時間ピッカーは24時間の時計を使用し、00:00は真夜中です。 タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。 別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## [!UICONTROL レポート設定] {#section_13119392051044FBA6387D9B3B1C43CF}

以下の設定を使用できます。

### [!UICONTROL  レポート Source]

次の場所から収集するソリューション データを指定します。

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

レポート ソリューションが[ アカウント設定](/help/main/administrating-target/reporting.md)で指定されている場合、指定されたソリューションが使用され、この設定は表示されません。

アクティビティが公開された後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。

**[!DNL Adobe Analytics]**: レポートソリューションと各ソリューションの利点の違いについて詳しくは、 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)のレポートソースとして[[!DNL Adobe Analytics] を参照してください。

[!DNL Analytics]を[!DNL Target] （A4T）のレポートソースとして選択する場合、[!DNL Analytics] レポートスイートを選択して[!DNL Target] アクティビティデータを受信します。 これを行うには、最初にアカウントが関連付けられている[!DNL Analytics]社の中から選択し、次にアクティビティに適したレポートスイートを選択します。 [!DNL Target]に接続するようにプロビジョニングされたレポートスイートのみが選択できます。 期待するレポートスイートが表示されない場合は、まずログアウトして[!DNL Adobe Experience Cloud]に再度ログインし、もう一度やり直してください。 レポートスイートがまだリストにない場合は、[ カスタマーケア ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

[!DNL Analytics for Target] （A4T）は、結果を正しく報告するためにトラッキングサーバーを必要とします。 デフォルトのトラッキングサーバーが「[!UICONTROL  トラッキングサーバー]」フィールドに表示されます。 複数のトラッキングサーバーを使用する場合は、このフィールドに正しいトラッキングサーバーを含めてください。 詳しくは、[Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)を参照してください。

**[!DNL Adobe Customer Journey Analytics]**: [!DNL Adobe Customer Journey Analytics]と[!DNL Target]の統合について詳しくは、 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)の[[!DNL Target]  レポートを参照してください。

### [!UICONTROL 目標指標]

目標達成の基準となる、訪問者の行動を選択します。 例えば、[!UICONTROL  コンバージョン ]指標を選択し、成功が達成されたときに決定するパラメーターを設定します。

指標の設定について詳しくは、[指標の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB)を参照してください。

>[!NOTE]
>
>レポート ソリューションが[!DNL Analytics]に設定されている場合、使用可能な目標指標は[!UICONTROL  コンバージョン ]のみです。 目標として[!DNL Analytics]指標を選択できません。

成功指標を選択したら、セレクターが表示されます。 このセレクターを使用して、成功指標の具体的な内容を選択します。

有効にした場合、「[!UICONTROL  コンバージョンの見積もり値]」フィールド（[!UICONTROL  ページスコア ]指標では使用できません）は、目標の値を提供しますが、他の指標の値は提供しません。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。 このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。 すべての収益指標（[!UICONTROL 訪問者あたりの売上高]、[!UICONTROL 平均注文額]、[!UICONTROL 総売上高]、および[!UICONTROL 注文数]）に対して、見積もりは[!UICONTROL 訪問者あたりの売上高]を使用します。 データタイプは通貨です。

アクティビティの目標に到達した後、訪問者は、その訪問者がより優先度の高いアクティビティに適格でない限り、アクティビティコンテンツを引き続き表示します。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。 この動作は、[!DNL Target Classic]のデフォルトの動作とは異なり、テストが再度表示された場合に訪問者を新規としてカウントします。

### [!UICONTROL 追加指標]

追加の成功指標を作成します。

この設定は、レポートソリューションが[!DNL Analytics]に設定されている場合は使用できません。 この場合、[!DNL Analytics] レポートスイートに定義された指標が適用されます。

### [!UICONTROL  レポート用オーディエンス ]

デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。 レポート対象のオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。

この設定は、レポートソリューションとして[!DNL Analytics]を選択した場合は使用できません。 [!DNL Analytics] レポートスイートに定義されたオーディエンスが適用されます。

## [!UICONTROL その他のMeta データ ]

自身や他のチームメンバーにとって役立つ、自身のアクティビティに関する情報を入力します。 [!UICONTROL  メモ ] ペインはサイズ変更可能です。

## [!UICONTROL 詳細設定] {#section_E2FE441AFB324E498793ABB025ED9974}

詳細設定は、[!UICONTROL  エクスペリエンスのターゲット設定]目標の指標で使用できます。

![詳細設定](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>[!DNL Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。 [!UICONTROL 詳細設定] オプションは使用できません。

以下の設定を使用できます。

### [!UICONTROL この指標を増分する前に到達する必要がある成功指標はどれですか？]

このオプションを使用すると、以前に別の成功指標に達した訪問者を、成功指標に達した訪問者としてのみカウントできます。 例えば、テストコンバージョンは、訪問者がコンバージョンする前にオファーをクリックしたり、特定のページに到達したりする場合にのみ有効です。

複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。

成功指標の依存関係を設定する前に、両方（または複数）の成功指標を定義する必要があります。

「[!UICONTROL 依存関係を追加]」オプションを利用すると、ある成功指標に到達した場合、または到達しなかった場合に別の成功指標を増分するよう設定できます。

依存関係を追加する手順は次のとおりです。

1. 指標を追加したら、「**[!UICONTROL 詳細設定]**」をクリックします。
2. 「**[!UICONTROL 依存関係を追加]**」をクリックします。

   ![依存関係を追加リンク](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. 目的の指標を左側のパネルから右側のパネルにドラッグ＆ドロップしてから、「**[!UICONTROL 到達]**」をクリックし、「[!UICONTROL 到達]」と「[!UICONTROL 未到達]」を切り替えて設定します。

   ![指標依存関係を追加ダイアログボックス](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

追加した依存関係は後で編集または削除できます。

### [!UICONTROL  ユーザーがこの目標指標に遭遇した後はどうなりますか？]

ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。

* 「[!UICONTROL カウントを増分、アクティビティでユーザーを保持]」を選択して、カウントの増分方法を指定します。
* 「[!UICONTROL カウントを増分、ユーザーをリリース、再入場を許可]」を選択して、ユーザーがアクティビティに再度入ったときに表示されるエクスペリエンスを指定します。
* 「[!UICONTROL 増分カウント、リエントリからユーザーとバーを解放]」を選択して、アクティビティコンテンツの代わりにユーザーに表示される内容を指定します。

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## トレーニングビデオ：アクティビティ設定（3:02）

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
