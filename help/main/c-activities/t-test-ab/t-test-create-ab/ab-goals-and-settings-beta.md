---
keywords: アクティビティ設定;A/B 目標と設定;レポート設定;目標指標;成功指標;従属成功指標;詳細設定;主な目標;追加の指標;目的;優先度;期間;レポートソリューション;目標;レポートのためのオーディエンス;指標を増分する前にどの成功指標に達するべきか;この目的指標にユーザーが達した後はどうなるか;メモ
description: '[!UICONTROL Goals and Settings] ページを使用して A/B アクティビティの目標を定義する方法を説明します。'
title: A [!DNL Target] A/B アクティビティで目標と設定を指定するにはどうすればよいですか？
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: aeafb4d8-a486-46cf-8871-4c220bc3674e
source-git-commit: d5bd3b0d7cdf6eb06175a6365da6b8173f76800f
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 30%

---

# 目標と設定

[!DNL Adobe Target] の [!UICONTROL Goals & Settings] ページでは、アクティビティの目標に関する情報を指定します。

使用できる設定は、レポートソースとして Target と [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) のどちらを使用するかによって異なります。

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

[!UICONTROL Goals & Settings] ページの「[!UICONTROL Activity Settings]」セクションでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Objective] | 目的を入力します（オプション）。目的は、ユーザーとチームメンバーがアクティビティを特定するのに役立つ任意の情報です。 |
| [!UICONTROL Priority] | の [!DNL Target] UI とオプションは、設定によっ [!UICONTROL Priority] 異なります。 従来の設定である [!UICONTROL Low]、[!UICONTROL Medium]、[!UICONTROL High] を使用するか、0～999 の細かい優先度を有効にすることができます。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>このオプションが [!UICONTROL Administration] （デフォルト）で有効になっていない場合は、優先度を [!UICONTROL Low]、[!UICONTROL Medium]、[!UICONTROL High] のいずれかに指定します。<P>[ 詳細な優先度 ](/help/main/administrating-target/reporting.md) を有効にするには、[!UICONTROL Administration]/[!UICONTROL Reporting] をクリックし、「[!UICONTROL Enable Fine-Grained Priorities]」オプションを「オン」の位置に切り替えます。 <P>このオプションが有効な場合は、0 = [!UICONTROL Low] および 999 = [!UICONTROL High] の値を 0 ～ 999 の範囲で指定します。 <P>以前のバージョンの [!DNL Target] で作成されたアクティビティの場合、[!UICONTROL Low] の優先度は 0、[!UICONTROL Medium]、[!UICONTROL High] は 10 に変換されます。 これらの値は必要に応じて調整できます。<P>注：詳細な優先順位を使用した後でこのオプションを無効にする前に、すべての優先順位を 0、5、10 に戻す必要があります。 |
| [!UICONTROL Duration] | アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。 |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

[!UICONTROL Goals & Settings] ページの「[!UICONTROL Reporting Settings]」セクションでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Reporting Source] | どのソリューション データを収集するかを指定します。<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>[ アカウント設定 ](/help/main/administrating-target/reporting.md) でレポートソースが指定されている場合、指定されたソースが使用され、この設定は表示されません。<P>アクティビティがライブになった後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。<P>**Adobe Analytics**: レポートソリューションの違いとそれぞれの利点について詳しくは、[Target のレポート用SourceとしてのAdobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) を参照してください。 [!DNL Target] のレポートソースとして [!DNL Analytics] を選択する場合は、アクティビティデータを受け取る [!DNL Analytics] レポートスイート [!DNL Target] 選択します。<P>レポートソースを指定するには、アカウントが関連付けられている [!DNL Analytics] の会社のいずれかを選択してから、アクティビティに適したレポートスイートを選択します。 [!DNL Adobe Target] に接続するようにプロビジョニングされているレポートスイートのみを選択できます。 目的のレポートスイートが表示されない場合は、まずログアウトして [!DNL Adobe Experience Cloud] にログインし直し、もう一度試してください。 それでもリストにレポートスイートが表示されない場合は、カスタマーケアへのお問い合わせ。<P><P>**Adobe Customer Journey Analytics**: [!DNL Adobe Customer Journey Analytics] と [!DNL Target] の統合の詳細については、[[!DNL Target]  レポート イン  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) を参照してください。<P>[!DNL Customer Journey Analytics] の [!DNL Target] レポートは、手動トラフィック分割を使用した A/B アクティビティでサポートされています。 [!UICONTROL Auto-Target] および [!UICONTROL Auto-Allocate] の A/B アクティビティは、[!DNL Customer Journey Analytics] で [!DNL Target] レポートを使用できません。 |
| [!UICONTROL Goal Metric] | 目標達成の基準となる、訪問者の行動を選択します。例えば、[!UICONTROL Conversion] の指標を選択してから、成功を達成するタイミングを決定するパラメーターを設定します。 指標の設定について詳しくは、[指標の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)を参照してください。<P>メモ：レポートソリューションが [!DNL Analytics] に設定されている場合、使用できる目標指標は [!UICONTROL Conversion] のみです。 指標 [!DNL Analytics] 目標として選択することはできません。 成功指標を選択したら、セレクターが表示されます。このセレクターを使用して、成功指標の具体的な内容を選択します。<P>有効になっている場合は、「[!UICONTROL Estimated Value of the Conversion]」フィールド（[!UICONTROL Page Score] 指標では使用できません）には他の指標の値ではなく、目標に関する値が示されます。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。すべての売上高指標（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales] および [!UICONTROL Orders]）について、予測には [!UICONTROL Revenue per Visitor] が使用されます。 データタイプは通貨です。<P>アクティビティの目標を達成した後も、その訪問者が優先度の高いアクティビティの対象となっている場合を除き、その訪問者には引き続きアクティビティコンテンツが表示されます。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。これは、[!DNL Target Classic] のデフォルトの動作（アクティビティが再度表示された場合に訪問者を新規としてカウントする）とは異なります。 |
| [!UICONTROL Additional Metrics] | 追加の成功指標を作成します。 この設定は、レポートソリューションが [!DNL Analytics] に設定されている場合は使用できません。 この場合、[!DNL Analytics] レポートスイート用に定義された指標が適用されます。 |
| [!UICONTROL Audiences for Reporting] | デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。レポートオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。 この設定は、レポートソリューションとして [!DNL Analytics] を選択した場合は使用できません。 [!DNL Analytics] レポートスイート用に定義されたオーディエンスが適用されます。 |

## 詳細設定 {#section_E2FE441AFB324E498793ABB025ED9974}

[!UICONTROL Goals & Settings] ページの「[!UICONTROL Advanced Settings]」セクションでは、詳細オプションを設定できます。

詳細設定を指定するには、「[!UICONTROL My Primary Goal]」セクションの **[!UICONTROL More]** アイコン ![ 詳細アイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、「**[!UICONTROL Advanced Settings]**」をクリックします。

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。詳細設定オプションは使用できません。

以下のオプションがあります。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | このオプションを使用すると、以前に別の成功指標に到達したユーザーのみを成功指標に到達するものとしてカウントできます。 例えば、アクティビティのコンバージョンが、訪問者がオファーをクリックした場合、または、コンバージョンする前に特定のページに到達する場合にのみ有効になることがあります。 複数の指標への依存関係を設定できるほか、カウントを増やすために指標に到達する必要があるかどうかを柔軟に選択できます。 両方（または複数）の成功指標を定義してから、成功指標を別の成功指標に依存させます。 [!UICONTROL Add Dependency] オプションを使用すると、別の成功指標に到達した場合または到達していない場合に、成功指標を増分できます。 依存関係を追加する手順は次のとおりです。<ul><li>指標を追加したら、「[!UICONTROL Advanced Settings]」をクリックします。</li><li>[!UICONTROL Add Dependency] のオプションをクリックします。</li><li>目的の指標を左のペインから右のペインにドラッグ&amp;ドロップし、「[!UICONTROL Reached]」をクリックして [!UICONTROL Reached] と [!UICONTROL  Not Reached] の設定を切り替えます。</li><li>追加した依存関係は後で編集または削除できます。</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。<ul><li>カウントの増分方法を指定するには、「**[!UICONTROL Increment Count & Keep User in Activity]**」を選択します。</li><li>「**[!UICONTROL Increment Count, Release User & Allow Reentry]**」を選択し、ユーザーがアクティビティに再度入った場合に表示されるエクスペリエンスを指定します。</li><li>**[!UICONTROL Increment Count, Release User & Bar from Reentry]** を選択して、アクティビティのコンテンツの代わりにユーザーに表示する内容を指定します。</li></ul> |
| [!UICONTROL How will the count be incremented?] | カウントの増加方法について、以下の 3 つのオプションがあります。<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## その他のメタデータ {#section_2E8917BEFB954480A4206B9E9E917F80}

[!UICONTROL Goals & Settings] ページの [!UICONTROL Other Metadata] セクションでは、自分自身や他のチームメンバーが手元に置いておくと便利な、アクティビティに関する情報を指定できます。 ノート ペインはサイズ変更が可能です。|
