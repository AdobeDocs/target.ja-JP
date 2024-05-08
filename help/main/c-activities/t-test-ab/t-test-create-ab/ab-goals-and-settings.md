---
keywords: アクティビティ設定;A/B 目標と設定;レポート設定;目標指標;成功指標;従属成功指標;詳細設定;主な目標;追加の指標;目的;優先度;期間;レポートソリューション;目標;レポートのためのオーディエンス;指標を増分する前にどの成功指標に達するべきか;この目的指標にユーザーが達した後はどうなるか;メモ
description: の使用方法を学ぶ [!UICONTROL Goals and Settings] a/B アクティビティの目標に関する情報を指定するページ。
title: で目標と設定を指定する方法 [!DNL Target] A/B アクティビティ？
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: b5f508d283390c859085d4ee52c582312085addc
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 35%

---

# 目標と設定

この [!UICONTROL Goals & Settings] のページ [!DNL Adobe Target] は、アクティビティの目標に関する情報を指定する場所です。

使用できる設定は、Target または [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) をレポートソースとして使用します。

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

この [!UICONTROL Activity Settings] の節 [!UICONTROL Goals & Settings] ページでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Objective] | 目的を入力します（オプション）。目的は、ユーザーとチームメンバーがアクティビティを特定するのに役立つ任意の情報です。 |
| [!UICONTROL Priority] | 設定に応じて、 [!DNL Target] の UI とオプション [!UICONTROL Priority] 変化する。 の従来の設定を使用できます [!UICONTROL Low], [!UICONTROL Medium]、または [!UICONTROL High]または、0～999 の細かい優先度を有効にすることもできます。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>このオプションが有効になっていない場合 [!UICONTROL Administration] （デフォルト）。優先度を指定します。 [!UICONTROL Low], [!UICONTROL Medium]、または [!UICONTROL High].<P>を有効にする [きめ細かい優先度](/help/main/administrating-target/reporting.md)を選択し、 [!UICONTROL Administration] > [!UICONTROL Reporting]を切り替えます [!UICONTROL Enable Fine-Grained Priorities] 「オン」の位置へのオプション。 <P>このオプションが有効な場合は、0 ～ 999 の値を指定します。0 = [!UICONTROL Low] および 999 = [!UICONTROL High]. <P>の以前のバージョンで作成されたアクティビティの場合 [!DNL Target], [!UICONTROL Low] 優先度は 0 に変換されます。 [!UICONTROL Medium] は 5 に変換されます。 [!UICONTROL High] は 10 に変換されます。 これらの値は必要に応じて調整できます。<P>注：詳細な優先順位を使用した後でこのオプションを無効にする前に、すべての優先順位を 0、5、10 に戻す必要があります。 |
| 期間 | アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。 |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

この [!UICONTROL Reporting Settings] の節 [!UICONTROL Goals & Settings] ページでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Reporting Source] | どのソリューション データを収集するかを指定します。<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>でレポートソースが指定されている場合 [アカウント設定](/help/main/administrating-target/reporting.md)：指定したソースが使用され、この設定は表示されません。<P>アクティビティがライブになった後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。<P>**Adobe Analytics**：を参照 [Target のレポートソースとしてのAdobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) レポートソリューションの違いとそれぞれの利点について説明します。 選択時 [!DNL Analytics] のレポートソースとしての [!DNL Target]を選択する場合は、 [!DNL Analytics] 受信するレポートスイート [!DNL Target] アクティビティデータ。<P>レポートソースを指定するには、まず次のいずれかを選択します [!DNL Analytics] アカウントが関連付けられている会社を選択し、アクティビティに適したレポートスイートを選択します。 に接続するようにプロビジョニングされているレポートスイートのみ [!DNL Adobe Target] を選択できます。 目的のレポートスイートが表示されない場合は、まずログアウトして、に再度ログインしてみてください [!DNL Adobe Experience Cloud] を再度実行してください。 それでもリストにレポートスイートが表示されない場合は、カスタマーケアへのお問い合わせ。<P><P>**Adobe Customer Journey Analytics**：を参照 [[!DNL Target] でのレポート [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) 間の統合について詳しくは、 [!DNL Adobe Customer Journey Analytics] および [!DNL Target].<P>[!DNL Target] でのレポート [!DNL Customer Journey Analytics] は、手動トラフィック分割を使用した A/B アクティビティでサポートされます。 [!UICONTROL Auto-Target] および [!UICONTROL Auto-Allocate] A/B アクティビティでを使用できない [!DNL Target] でのレポート [!DNL Customer Journey Analytics]. |
| [!UICONTROL Goal Metric] | 目標達成の基準となる、訪問者の行動を選択します。例えば、 [!UICONTROL Conversion] 次に、成功を達成するタイミングを決定するパラメーターを設定します。 指標の設定について詳しくは、[指標の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)を参照してください。<P>メモ：レポートソリューションがに設定されている場合 [!DNL Analytics]使用できる目標指標はのみです。 [!UICONTROL Conversion]. [!DNL Analytics] 指標は目標として選択できません。 成功指標を選択したら、セレクターが表示されます。このセレクターを使用して、成功指標の具体的な内容を選択します。<P>有効な場合、 [!UICONTROL Estimated Value of the Conversion] フィールド （ [!UICONTROL Page Score] （指標）は、他の指標の値ではなく、目標の値を提供します。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。すべての売上高指標（[!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales]、および [!UICONTROL Orders]）に設定する必要があります。 [!UICONTROL Revenue per Visitor]. データタイプは通貨です。<P>アクティビティの目標を達成した後も、その訪問者が優先度の高いアクティビティの対象となっている場合を除き、その訪問者には引き続きアクティビティコンテンツが表示されます。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。これは、のデフォルトの動作とは異なります [!DNL Target Classic]を選択します。訪問者がアクティビティを再度表示した場合は、新規訪問者としてカウントされます。 |
| [!UICONTROL Additional Metrics] | 追加の成功指標を作成します。 この設定は、レポートソリューションがに設定されている場合は使用できません [!DNL Analytics]. この場合、指標は、 [!DNL Analytics] レポートスイートが適用されます。 |
| [!UICONTROL Audiences for Reporting] | デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。レポートオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。 この設定は、次のいずれかを選択した場合は利用できません。 [!DNL Analytics] をレポートソリューションとして使用します。 に対して定義されたオーディエンス [!DNL Analytics] レポートスイートが適用されます。 |

## 詳細設定 {#section_E2FE441AFB324E498793ABB025ED9974}

この [!UICONTROL Advanced Settings] の節 [!UICONTROL Goals & Settings] ページでは、次のオプションを設定できます。

詳細設定を指定するには、 **[!UICONTROL More]** アイコン（垂直省略記号）をクリックし、 **[!UICONTROL Advanced Settings]**&#x200B;を次の図に示します。

![詳細設定メニュー](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。詳細設定オプションは使用できません。

![詳細設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | このオプションを使用すると、以前に別の成功指標に到達したユーザーのみを成功指標に到達するものとしてカウントできます。 例えば、アクティビティのコンバージョンが、訪問者がオファーをクリックした場合、または、コンバージョンする前に特定のページに到達する場合にのみ有効になることがあります。 複数の指標への依存関係を設定できるほか、カウントを増やすために指標に到達する必要があるかどうかを柔軟に選択できます。 両方（または複数）の成功指標を定義してから、成功指標を別の成功指標に依存させます。 この [!UICONTROL Add Dependency] オプションを使用すると、別の成功指標に達したか達していない場合に、成功指標を増分できます。 依存関係を追加する手順は次のとおりです。<ul><li>指標を追加したら、 [!UICONTROL Advanced Settings].</li><li>「」をクリックします [!UICONTROL Add Dependency] オプション：</li><li>目的の指標を左のペインから右のペインにドラッグ&amp;ドロップし、 [!UICONTROL Reached] 設定を切り替えるには [!UICONTROL Reached] および[!UICONTROL  Not Reached].</li><li>追加した依存関係は後で編集または削除できます。</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。<ul><li>を選択 [!UICONTROL Increment Count & Keep User in Activity] カウントの増分方法を指定します。</li><li>を選択 [!UICONTROL Increment Count, Release User & Allow Reentry] アクティビティに再度入った場合に表示されるエクスペリエンスを指定します。</li><li>を選択 [!UICONTROL Increment Count, Release User & Bar from Reentry] アクティビティのコンテンツの代わりにユーザーに表示する内容を指定します。</li></ul> |
| [!UICONTROL How will the count be incremented?] | カウントの増加方法について、以下の 3 つのオプションがあります。<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## その他のメタデータ {#section_2E8917BEFB954480A4206B9E9E917F80}

この [!UICONTROL Other Metadata] の節 [!UICONTROL Goals & Settings] ページでは、自分自身や他のチームメンバーが把握するのに役立つ、アクティビティに関する情報を指定できます。 ノート ペインはサイズ変更が可能です。|

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### アクティビティ設定（3:02） ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

(https://video.tv.adobe.com/v/17381?captions=jpn

### A/B テストの作成（8:36） ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、アクティビティを作成する際に 3 ステップのガイドによるワークフロー内でどのようにアクティビティ設定がなされるのか示します。目標と設定の説明は、5:30 から始まります。

* Adobe Target での A/B アクティビティの作成
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391)
