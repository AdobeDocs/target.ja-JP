---
keywords: アクティビティ設定;A/B 目標と設定;レポート設定;目標指標;成功指標;従属成功指標;詳細設定;主な目標;追加の指標;目的;優先度;期間;レポートソリューション;目標;レポートのためのオーディエンス;指標を増分する前にどの成功指標に達するべきか;この目的指標にユーザーが達した後はどうなるか;メモ
description: '[!UICONTROL 目標と設定] ページを使用してA/B アクティビティ目標を定義する方法を説明します。'
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
source-wordcount: 1292
ht-degree: 33%

---

# 目標と設定

[!DNL Adobe Target]の[!UICONTROL 目標と設定] ページでは、アクティビティの目標に関する情報を指定します。

使用可能な設定は、レポートソースとしてTargetまたは[Analyticsを使用するかどうかに応じて異なります](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

## [!UICONTROL アクティビティの設定] {#section_DCBDC354261F420EBD4B43EA34947BAC}

[!UICONTROL 目標と設定] ページの[!UICONTROL &#x200B; アクティビティ設定] セクションでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL 目標] | 目的を入力します（オプション）。 目的とは、組織やチームメンバーがアクティビティを特定するのに役立つ、あらゆる情報を指します。 |
| [!UICONTROL 優先順位] | 設定に応じて、[!UICONTROL 優先度]の[!DNL Target] UIとオプションが異なります。 [!UICONTROL Low]、[!UICONTROL Medium]または[!UICONTROL High]の従来の設定を使用するか、0 ～ 999の細かい優先度を有効にできます。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>このオプションが[!UICONTROL 管理] （デフォルト）で有効になっていない場合は、優先度を[!UICONTROL 低]、[!UICONTROL Medium]、または[!UICONTROL 高]に指定します。<P>[きめ細かい優先度](/help/main/administrating-target/reporting.md)を有効にするには、[!UICONTROL 管理] > [!UICONTROL &#x200B; レポート &#x200B;]をクリックし、[!UICONTROL きめ細かい優先度を有効にする] オプションを「オン」の位置に切り替えます。 <P>このオプションが有効になっている場合は、0 ～ 999の値を指定します。0 = [!UICONTROL Low]、999 = [!UICONTROL High]。 <P>以前のバージョンの[!DNL Target]で作成されたアクティビティの場合、[!UICONTROL 低]の優先度は0に変換され、[!UICONTROL Medium]は5に変換され、[!UICONTROL 高]は10に変換されます。 これらの値は必要に応じて調整できます。<P>注意：きめ細かい優先順位を使用した後にこのオプションを無効にする前に、すべての優先順位を0、5、および10に戻す必要があります。 |
| [!UICONTROL 期間] | アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。 同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。 時間ピッカーは24時間の時計を使用し、00:00は真夜中です。 タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。 別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。 |

## [!UICONTROL レポート設定] {#section_13119392051044FBA6387D9B3B1C43CF}

[!UICONTROL 目標と設定] ページの[!UICONTROL &#x200B; レポート設定] セクションでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL &#x200B; レポート Source] | 次の場所から収集するソリューション データを指定します。<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>[&#x200B; アカウント設定](/help/main/administrating-target/reporting.md)でレポートソースが指定されている場合、指定されたソースが使用され、この設定は表示されません。<P>アクティビティが公開された後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。<P>**Adobe Analytics**: レポートソリューションと各ソリューションの利点の違いについては、[Adobe Analytics as the Reporting Source for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md)を参照してください。 [!DNL Analytics]を[!DNL Target]のレポートソースとして選択する場合、[!DNL Analytics] レポートスイートを選択して[!DNL Target] アクティビティデータを受信します。<P>レポートソースを指定するには、まずアカウントが関連付けられている[!DNL Analytics]社の中から選択し、アクティビティに適したレポートスイートを選択します。 [!DNL Adobe Target]に接続するようにプロビジョニングされたレポートスイートのみが選択できます。 期待するレポートスイートが表示されない場合は、まずログアウトして[!DNL Adobe Experience Cloud]に再度ログインし、もう一度やり直してください。 レポートスイートがまだリストにない場合は、カスタマーケアにお問い合わせください。<P><P>**Adobe Customer Journey Analytics**: [!DNL Adobe Customer Journey Analytics]と[!DNL Target]の統合について詳しくは、 [!DNL Adobe Customer Journey Analytics][&#128279;](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)の[!DNL Target]  レポートを参照してください。<P>[!DNL Customer Journey Analytics]の[!DNL Target] レポートは、手動トラフィック分割を使用したA/B アクティビティでサポートされています。 [!UICONTROL 自動ターゲット &#x200B;]および[!UICONTROL 自動配分]のA/B アクティビティでは、[!DNL Customer Journey Analytics]で[!DNL Target]のレポートを使用できません。 |
| [!UICONTROL 目標指標] | 目標達成の基準となる、訪問者の行動を選択します。 例えば、[!UICONTROL &#x200B; コンバージョン &#x200B;]指標を選択し、成功が達成されたときに決定するパラメーターを設定します。 指標の設定について詳しくは、[指標の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)を参照してください。<P>注意：レポート ソリューションが[!DNL Analytics]に設定されている場合、使用可能な目標指標は[!UICONTROL &#x200B; コンバージョン &#x200B;]のみです。 目標として[!DNL Analytics]指標を選択できません。 成功指標を選択したら、セレクターが表示されます。 このセレクターを使用して、成功指標の具体的な内容を選択します。<P>有効にした場合、「[!UICONTROL &#x200B; コンバージョンの見積もり値]」フィールド（[!UICONTROL &#x200B; ページスコア &#x200B;]指標では使用できません）は、目標の値を提供しますが、他の指標の値は提供しません。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。 このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。 すべての収益指標（[!UICONTROL 訪問者あたりの売上高]、[!UICONTROL 平均注文額]、[!UICONTROL 総売上高]、および[!UICONTROL 注文数]）に対して、見積もりは[!UICONTROL 訪問者あたりの売上高]を使用します。 データタイプは通貨です。<P>アクティビティの目標に到達した後、訪問者は、その訪問者がより優先度の高いアクティビティに適格でない限り、アクティビティコンテンツを引き続き表示します。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。 これは、アクティビティが再度表示された場合に訪問者を新規としてカウントする[!DNL Target Classic]のデフォルトの動作とは異なります。 |
| [!UICONTROL 追加指標] | 追加の成功指標を作成します。 この設定は、レポートソリューションが[!DNL Analytics]に設定されている場合は使用できません。 この場合、[!DNL Analytics] レポートスイートに定義された指標が適用されます。 |
| [!UICONTROL &#x200B; レポート用オーディエンス &#x200B;] | デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。 レポートオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。 この設定は、レポートソリューションとして[!DNL Analytics]を選択した場合は使用できません。 [!DNL Analytics] レポートスイートに定義されたオーディエンスが適用されます。 |

## 詳細設定 {#section_E2FE441AFB324E498793ABB025ED9974}

[!UICONTROL 目標と設定] ページの[!UICONTROL 詳細設定] セクションでは、詳細オプションを設定できます。

詳細設定を指定するには、[!UICONTROL プライマリ目標] セクションの&#x200B;**[!UICONTROL 詳細]** アイコン （![詳細アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、**[!UICONTROL 詳細設定]**&#x200B;をクリックします。

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。 詳細設定オプションは使用できません。

以下のオプションがあります。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL この指標を増分する前に到達する必要がある成功指標はどれですか？] | このオプションを使用すると、以前に別の成功指標に達したことがあるユーザーを、成功指標に達したユーザーとしてのみカウントできます。 例えば、アクティビティのコンバージョンは、訪問者がオファーをクリックするか、コンバージョンする前に特定のページに到達した場合にのみ有効です。 複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。 別の指標に依存させる前に、両方（または複数）の成功指標を定義します。 「[!UICONTROL 依存関係を追加]」オプションを利用すると、ある成功指標に到達した場合、または到達しなかった場合に別の成功指標を増分するよう設定できます。 依存関係を追加する手順は次のとおりです。<ul><li>指標を追加したら、「[!UICONTROL 詳細設定]」をクリックします。</li><li>「[!UICONTROL 依存関係を追加]」オプションをクリックします。</li><li>左側のペインから目的の指標を右側のペインにドラッグ&amp;ドロップし、[!UICONTROL 到達]をクリックして、[!UICONTROL 到達]と[!UICONTROL 未到達]の間の設定を切り替えます。</li><li>追加した依存関係は後で編集または削除できます。</li></ul> |
| [!UICONTROL &#x200B; ユーザーがこの目標指標に遭遇した後はどうなりますか？] | ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。<ul><li>「**[!UICONTROL カウントを増分、アクティビティでユーザーを保持]**」を選択して、カウントの増分方法を指定します。</li><li>「**[!UICONTROL カウントを増分、ユーザーをリリース、再入場を許可]**」を選択して、ユーザーがアクティビティに再度入ったときに表示されるエクスペリエンスを指定します。</li><li>「**[!UICONTROL 増分カウント、リエントリからユーザーとバーを解放]**」を選択して、アクティビティコンテンツの代わりにユーザーに表示される内容を指定します。</li></ul> |
| [!UICONTROL &#x200B; カウントの増分方法を教えてください。] | カウントの増加方法について、以下の 3 つのオプションがあります。<ul><li>[!UICONTROL 参加者ごとに1回]</li><li>[!UICONTROL すべてのインプレッション （ページの更新を除く） &#x200B;]</li><li>[!UICONTROL すべてのインプレッション &#x200B;]</li></ul> |

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## その他のメタデータ {#section_2E8917BEFB954480A4206B9E9E917F80}

[!UICONTROL 目標と設定] ページの[!UICONTROL その他のメタデータ &#x200B;] セクションでは、自分や他のチームメンバーのために手元に置いておくのに役立つアクティビティに関する情報を指定できます。 メモ ウィンドウのサイズを変更できます。|
