---
keywords: アクティビティ設定;A/B 目標と設定;レポート設定;目標指標;成功指標;従属成功指標;詳細設定;主な目標;追加の指標;目的;優先度;期間;レポートソリューション;目標;レポートのためのオーディエンス;指標を増分する前にどの成功指標に達するべきか;この目的指標にユーザーが達した後はどうなるか;メモ
description: '[!UICONTROL Goals and Settings] ページを使用してA/B アクティビティ目標を定義する方法を説明します。'
title: A [!DNL Target] A/B アクティビティで目標と設定を指定するにはどうすればよいですか？
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
TQID: https://experienceleague.adobe.com/X3JDvfXDHM2rAOodEY5N9TVO-tBpz4vNDUvhOpC0XZ4
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1138
ht-degree: 31%

---

# 目標と設定

[!DNL Adobe Target]の[!UICONTROL Goals & Settings] ページでは、アクティビティの目標に関する情報を指定します。

使用可能な設定は、レポートソースとしてTargetまたは[Analyticsを使用するかどうかに応じて異なります](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

[!UICONTROL Goals & Settings] ページの[!UICONTROL Activity Settings] セクションでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Objective] | 目的を入力します（オプション）。 目的とは、組織やチームメンバーがアクティビティを特定するのに役立つ、あらゆる情報を指します。 |
| [!UICONTROL Priority] | 設定に応じて、[!UICONTROL Priority]の[!DNL Target] UIとオプションは異なります。 [!UICONTROL Low]、[!UICONTROL Medium]または[!UICONTROL High]の従来の設定を使用するか、0 ～ 999の細かい優先度を有効にできます。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>このオプションが[!UICONTROL Administration] （デフォルト）で有効になっていない場合は、優先度を指定してください：[!UICONTROL Low]、[!UICONTROL Medium]、または[!UICONTROL High]。<P>[きめ細かい優先度](/help/main/administrating-target/reporting.md)を有効にするには、[!UICONTROL Administration] > [!UICONTROL Reporting]をクリックし、[!UICONTROL Enable Fine-Grained Priorities] オプションを「オン」の位置に切り替えます。 <P>このオプションが有効になっている場合は、0 ～ 999の値を指定します。0 = [!UICONTROL Low]、999 = [!UICONTROL High]。 <P>以前のバージョンの[!DNL Target]で作成されたアクティビティの場合、[!UICONTROL Low]の優先度は0に変換され、[!UICONTROL Medium]は5に変換され、[!UICONTROL High]は10に変換されます。 これらの値は必要に応じて調整できます。<P>注意：きめ細かい優先順位を使用した後にこのオプションを無効にする前に、すべての優先順位を0、5、および10に戻す必要があります。 |
| [!UICONTROL Duration] | アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。 同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。 時間ピッカーは24時間の時計を使用し、00:00は真夜中です。 タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。 別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。 |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

[!UICONTROL Goals & Settings] ページの[!UICONTROL Reporting Settings] セクションでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Reporting Source] | 次の場所から収集するソリューション データを指定します。<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>[&#x200B; アカウント設定](/help/main/administrating-target/reporting.md)でレポートソースが指定されている場合、指定されたソースが使用され、この設定は表示されません。<P>アクティビティが公開された後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。<P>**Adobe Analytics**: レポートソリューションと各ソリューションの利点の違いについては、[Adobe Analytics as the Reporting Source for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md)を参照してください。 [!DNL Analytics]を[!DNL Target]のレポートソースとして選択する場合、[!DNL Analytics] レポートスイートを選択して[!DNL Target] アクティビティデータを受信します。<P>レポートソースを指定するには、まずアカウントが関連付けられている[!DNL Analytics]社の中から選択し、アクティビティに適したレポートスイートを選択します。 [!DNL Adobe Target]に接続するようにプロビジョニングされたレポートスイートのみが選択できます。 期待するレポートスイートが表示されない場合は、まずログアウトして[!DNL Adobe Experience Cloud]に再度ログインし、もう一度やり直してください。 レポートスイートがまだリストにない場合は、カスタマーケアにお問い合わせください。<P><P>**Adobe Customer Journey Analytics**: [!DNL Adobe Customer Journey Analytics]と[!DNL Target]の統合について詳しくは、 [!DNL Adobe Customer Journey Analytics][&#128279;](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)の[!DNL Target]  レポートを参照してください。<P>[!DNL Customer Journey Analytics]の[!DNL Target] レポートは、手動トラフィック分割を使用したA/B アクティビティでサポートされています。 [!UICONTROL Auto-Target]および[!UICONTROL Auto-Allocate]個のA/B アクティビティは、[!DNL Customer Journey Analytics]で[!DNL Target]件のレポートを使用できません。 |
| [!UICONTROL Goal Metric] | 目標達成の基準となる、訪問者の行動を選択します。 例えば、[!UICONTROL Conversion]指標を選択し、成功が達成されたときに決定するパラメーターを設定します。 指標の設定について詳しくは、[指標の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)を参照してください。<P>メモ：レポート ソリューションが[!DNL Analytics]に設定されている場合、使用可能な目標指標は[!UICONTROL Conversion]のみです。 目標として[!DNL Analytics]指標を選択できません。 成功指標を選択したら、セレクターが表示されます。 このセレクターを使用して、成功指標の具体的な内容を選択します。<P>有効にすると、[!UICONTROL Estimated Value of the Conversion] フィールド（[!UICONTROL Page Score]指標では使用できません）は目標の値を提供しますが、他の指標の値は提供しません。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。 このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。 すべての収益指標（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales]、および[!UICONTROL Orders]）に対して、見積もりは[!UICONTROL Revenue per Visitor]を使用します。 データタイプは通貨です。<P>アクティビティの目標に到達した後、訪問者は、その訪問者がより優先度の高いアクティビティに適格でない限り、アクティビティコンテンツを引き続き表示します。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。 これは、アクティビティが再度表示された場合に訪問者を新規としてカウントする[!DNL Target Classic]のデフォルトの動作とは異なります。 |
| [!UICONTROL Additional Metrics] | 追加の成功指標を作成します。 この設定は、レポートソリューションが[!DNL Analytics]に設定されている場合は使用できません。 この場合、[!DNL Analytics] レポートスイートに定義された指標が適用されます。 |
| [!UICONTROL Audiences for Reporting] | デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。 レポートオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。 この設定は、レポートソリューションとして[!DNL Analytics]を選択した場合は使用できません。 [!DNL Analytics] レポートスイートに定義されたオーディエンスが適用されます。 |

## 詳細設定 {#section_E2FE441AFB324E498793ABB025ED9974}

[!UICONTROL Goals & Settings] ページの[!UICONTROL Advanced Settings] セクションでは、詳細オプションを設定できます。

詳細設定を指定するには、[!UICONTROL My Primary Goal] セクションの&#x200B;**[!UICONTROL More]** アイコン （![詳細アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、**[!UICONTROL Advanced Settings]**&#x200B;をクリックします。

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。 詳細設定オプションは使用できません。

以下のオプションがあります。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | このオプションを使用すると、以前に別の成功指標に達したことがあるユーザーを、成功指標に達したユーザーとしてのみカウントできます。 例えば、アクティビティのコンバージョンは、訪問者がオファーをクリックするか、コンバージョンする前に特定のページに到達した場合にのみ有効です。 複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。 別の指標に依存させる前に、両方（または複数）の成功指標を定義します。 [!UICONTROL Add Dependency] オプションを使用すると、別の成功指標に達した場合または達しなかった場合に、成功指標を増分できます。 依存関係を追加する手順は次のとおりです。<ul><li>指標を追加したら、[!UICONTROL Advanced Settings]をクリックします。</li><li>「[!UICONTROL Add Dependency]」オプションをクリックします。</li><li>左側のペインから右側のペインに目的の指標をドラッグ&amp;ドロップし、[!UICONTROL Reached]をクリックして[!UICONTROL Reached]と[!UICONTROL &#x200B; Not Reached]の間で設定を切り替えます。</li><li>追加した依存関係は後で編集または削除できます。</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。<ul><li>**[!UICONTROL Increment Count & Keep User in Activity]**&#x200B;を選択して、カウントの増分方法を指定します。</li><li>**[!UICONTROL Increment Count, Release User & Allow Reentry]**&#x200B;を選択して、ユーザーがアクティビティを再入力した場合に表示されるエクスペリエンスを指定します。</li><li>「**[!UICONTROL Increment Count, Release User & Bar from Reentry]**」を選択して、アクティビティコンテンツではなくユーザーに表示される内容を指定します。</li></ul> |
| [!UICONTROL How will the count be incremented?] | カウントの増加方法について、以下の 3 つのオプションがあります。<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## その他のメタデータ {#section_2E8917BEFB954480A4206B9E9E917F80}

[!UICONTROL Goals & Settings] ページの[!UICONTROL Other Metadata] セクションでは、自分や他のチームメンバーのために手元に置いておくのに役立つアクティビティに関する情報を指定できます。 メモ ウィンドウのサイズを変更できます。|
