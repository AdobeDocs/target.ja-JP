---
keywords: アクティビティ設定;A/B 目標と設定;レポート設定;目標指標;成功指標;従属成功指標;詳細設定;主な目標;追加の指標;目的;優先度;期間;レポートソリューション;目標;レポートのためのオーディエンス;指標を増分する前にどの成功指標に達するべきか;この目的指標にユーザーが達した後はどうなるか;メモ
description: '[!UICONTROL 目標と設定] ページを使用してA/B アクティビティ目標を定義する方法を説明します。'
title: '[!DNL Target] A/B アクティビティで目標と設定を指定する方法を教えてください。'
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
TQID: 'https://experienceleague.adobe.com/X3JDvfXDHM2rAOodEY5N9TVO-tBpz4vNDUvhOpC0XZ4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: abab6b3e464bb9f294e9c3c455dca1f57bb0d458
workflow-type: tm+mt
source-wordcount: '1669'
ht-degree: 24%
---
# 目標と設定 {#ab-goals-and-settings}

>[!BEGINSHADEBOX]

**このページ：** A/B、エクスペリエンスのターゲット設定（XT）、または多変量テスト（MVT）アクティビティの&#x200B;**[!UICONTROL 目標と設定]** ページで設定できるものを説明します。アクティビティ設定、レポート設定、詳細設定、およびメモです。

>[!ENDSHADEBOX]

[!DNL Adobe Target]の&#x200B;**[!UICONTROL 目標と設定]** ページでは、アクティビティの目標に関する情報を指定します。

使用可能な設定は、レポートソースとしてTargetまたは[Analyticsを使用するかどうかに応じて異なります](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）および[!UICONTROL 多変量テスト &#x200B;] （MVT）アクティビティにも同じ設定が適用されます。ただし、[統計的手法](#section_statistical-methodology)はA/B アクティビティでのみ使用できます。

* [&#x200B; アクティビティ設定](#section_DCBDC354261F420EBD4B43EA34947BAC)：目的、優先度、期間
* [&#x200B; レポート設定](#section_13119392051044FBA6387D9B3B1C43CF)：レポートソース、目標指標、追加指標、オーディエンス
* [詳細設定](#section_E2FE441AFB324E498793ABB025ED9974)：依存関係と、訪問者が目標に到達した後の処理
* [統計的手法](#section_statistical-methodology)：結果の分析方法
* [その他のメタデータ &#x200B;](#section_2E8917BEFB954480A4206B9E9E917F80)：メモ

## [!UICONTROL アクティビティの設定] {#section_DCBDC354261F420EBD4B43EA34947BAC}

**[!UICONTROL 目標と設定]** ページの&#x200B;**[!UICONTROL アクティビティ設定]** セクションでは、次のオプションを設定できます。

![](../../assets/goals-ab-1.png)

### 目的 {#objective}

目的を入力します（オプション）。 目的とは、組織やチームメンバーがアクティビティを特定するのに役立つ、あらゆる情報を指します。

### 優先度 {#priority}

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

設定に応じて、**[!UICONTROL 優先度]**&#x200B;の[!DNL Target] UIとオプションは異なります。

* **従来の優先度（デフォルト）:**&#x200B;このオプションが&#x200B;**[!UICONTROL 管理]** （デフォルト）で有効になっていない場合は、**[!UICONTROL 低]**、**[!UICONTROL Medium]**、または&#x200B;**[!UICONTROL 高]**&#x200B;の優先度を指定します。
* **きめ細かい優先度：** 0 ～ 999の値を指定します。0 = **[!UICONTROL Low]** and 999 = **[!UICONTROL High]**。

  [きめ細かい優先度](/help/main/administrating-target/reporting.md)を有効にするには、**[!UICONTROL 管理]** > **[!UICONTROL レポート]**&#x200B;にアクセスし、**[!UICONTROL きめ細かい優先度を有効にする]** オプションを切り替えます。

以前のバージョンの[!DNL Target]で作成されたアクティビティの場合、**[!UICONTROL 低]**&#x200B;の優先度は0に変換され、**[!UICONTROL Medium]**&#x200B;は5に変換され、**[!UICONTROL 高]**&#x200B;は10に変換されます。 これらの値は必要に応じて調整できます。

>[!NOTE]
>
>きめ細かい優先度を使用した後に無効にする前に、すべての優先度を0、5、および10に戻す必要があります。

### 期間 {#duration}

アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。 同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。

タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。 タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。 別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## [!UICONTROL レポート設定] {#section_13119392051044FBA6387D9B3B1C43CF}

**[!UICONTROL 目標と設定]** ページの&#x200B;**[!UICONTROL レポート設定]** セクションでは、次のオプションを設定できます。

![](../../assets/goals-ab-2.png)

### レポートソース {#reporting-source}

次の場所から収集するソリューション データを指定します。

* [!DNL Adobe Target]

* [!DNL Adobe Analytics]

  +++ レポートソースとしてのAnalyticsについて詳しく見る

  各レポートソリューションの差異およびそれぞれのメリットについて詳しくは、[Adobe Target のレポートソースとしての Adobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md)を参照してください。 [!DNL Analytics]を[!DNL Target]のレポートソースとして選択する場合、[!DNL Analytics] レポートスイートを選択して[!DNL Target] アクティビティデータを受信します。

  レポートソースを指定するには、まずアカウントが関連付けられている[!DNL Analytics]社の中から選択し、アクティビティに適したレポートスイートを選択します。 [!DNL Adobe Target]に接続するようにプロビジョニングされたレポートスイートのみが選択できます。 期待するレポートスイートが表示されない場合は、まずログアウトして[!DNL Adobe Experience Cloud]に再度ログインし、もう一度やり直してください。 レポートスイートがまだリストにない場合は、カスタマーケアにお問い合わせください。

  [!DNL Analytics for Target] （A4T）は、結果を正しく報告するためにトラッキングサーバーを必要とします。 デフォルトのトラッキングサーバーが「**[!UICONTROL トラッキングサーバー]**」フィールドに表示されます。 複数のトラッキングサーバーを使用する場合は、このフィールドに正しいトラッキングサーバーを含めてください。 詳しくは、[Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)を参照してください。
  +++

* [!DNL Adobe Customer Journey Analytics]

  +++ レポートソースとしてのCustomer Journey Analyticsの詳細

  サポートされているアクティビティタイプ、[!DNL Customer Journey Analytics]でのサンドボックスおよびデータビューの選択、目標指標、レポート設定については、 [!DNL Adobe Customer Journey Analytics]&#x200B;[&#128279;](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)の[!DNL Target]  レポートを参照してください。
  +++

[&#x200B; アカウント設定](/help/main/administrating-target/reporting.md)でレポートソースが指定されている場合、指定されたソースが使用され、この設定は表示されません。

アクティビティが公開された後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。

### 目標指標 {#goal-metric}

>[!NOTE]
>
>レポート ソリューションが[!DNL Analytics]に設定されている場合、使用可能な目標指標は&#x200B;**[!UICONTROL コンバージョン]**&#x200B;のみです。 目標として[!DNL Analytics]指標を選択できません。

目標達成の基準となる、訪問者の行動を選択します。 例えば、**[!UICONTROL コンバージョン]**&#x200B;指標を選択し、成功が達成されたときに決定するパラメーターを設定します。

指標の設定について詳しくは、[指標の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)を参照してください。

その他のオプションについては、目標指標の横にある&#x200B;**[!UICONTROL 詳細]** アイコンをクリックし、**[!UICONTROL 詳細設定]**&#x200B;をクリックします。 [詳細設定](#section_E2FE441AFB324E498793ABB025ED9974)を参照してください。

![](../../assets/goals-ab-3.png)

有効にした場合、「**[!UICONTROL コンバージョンの見積もり値]**」フィールドは、目標の値を提供しますが、他の指標の値は提供しません。 このフィールドには、次の点が適用されます。

* この値を使用すると、[!DNL Target]は売上増加の推定値を計算できます。
* このフィールドはオプションですが、収益以外の指標の増分収益は、このフィールドなしでは計算できません。
* このフィールドは、**[!UICONTROL ページスコア]**&#x200B;指標では使用できません。
* すべての収益指標（**[!UICONTROL 訪問者あたりの売上高]**、**[!UICONTROL 平均注文額]**、**[!UICONTROL 総売上高]**、および&#x200B;**[!UICONTROL 注文数]**）に対して、見積もりは&#x200B;**[!UICONTROL 訪問者あたりの売上高]**&#x200B;を使用します。 データタイプは通貨です。

### 追加の指標 {#additional-metrics}

この設定は、レポートソリューションが[!DNL Analytics]に設定されている場合は使用できません。 この場合、[!DNL Analytics] レポートスイートに定義された指標が適用されます。

### レポート対象のオーディエンス {#audiences-for-reporting}

![](../../assets/goals-ab-4.png)

デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。 レポートオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。

この設定は、レポートソリューションとして[!DNL Analytics]を選択した場合は使用できません。 [!DNL Analytics] レポートスイートに定義されたオーディエンスが適用されます。

## 詳細設定 {#section_E2FE441AFB324E498793ABB025ED9974}

**[!UICONTROL 目標と設定]** ページの&#x200B;**[!UICONTROL 詳細設定]** セクションでは、詳細オプションを設定できます。

詳細設定を指定するには、**[!UICONTROL プライマリ目標]** セクションの&#x200B;**[!UICONTROL 詳細]** アイコン （![詳細アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、**[!UICONTROL 詳細設定]**&#x200B;をクリックします。

![](../../assets/goals-ab-3.png)

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。 詳細設定オプションは使用できません。

### この指標を増分する前に達成する必要がある成功指標はどれですか？ {#dependencies}

このオプションを使用すると、以前に別の成功指標に達したことがあるユーザーを、成功指標に達したユーザーとしてのみカウントできます。 例えば、アクティビティのコンバージョンは、訪問者がオファーをクリックするか、コンバージョンする前に特定のページに到達した場合にのみ有効です。

複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。 別の指標に依存させる前に、両方（または複数）の成功指標を定義します。 「**[!UICONTROL 依存関係を追加]**」オプションを利用すると、ある成功指標に到達した場合、または到達しなかった場合に別の成功指標を増分するよう設定できます。

依存関係を追加する手順は次のとおりです。

1. 指標を追加したら、「**[!UICONTROL 詳細設定]**」をクリックします。

1. 「**[!UICONTROL 依存関係を追加]**」オプションをクリックします。

1. 目的の指標をドラッグ&amp;ドロップし、**[!UICONTROL 到達]**&#x200B;をクリックして、**[!UICONTROL 到達]**&#x200B;と&#x200B;**[!UICONTROL 未到達]**&#x200B;の設定を切り替えます。

追加した依存関係は後で編集または削除できます。

### ユーザーがこの目標指標に達した後、どうなりますか？ {#after-goal}

アクティビティの目標に到達した後、訪問者は、その訪問者がより優先度の高いアクティビティに適格でない限り、アクティビティコンテンツを引き続き表示します。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。 これは、アクティビティが再度表示された場合に訪問者を新規としてカウントする[!DNL Target Classic]のデフォルトの動作とは異なります。

ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。

* **[!UICONTROL カウントを増やし、ユーザーをアクティビティ]**&#x200B;に維持して、カウントの増分方法を指定します。
* **[!UICONTROL 増分カウント、リリースユーザー、再入力を許可]**&#x200B;して、ユーザーがアクティビティに再入力した場合にユーザーに表示されるエクスペリエンスを指定します。
* **[!UICONTROL アクティビティ コンテンツの代わりにユーザーに表示される内容を指定するには、再入力]**&#x200B;からユーザーとバーを解放してカウントを増やします。

### カウントをどのように増分しますか？ {#count-increment}

カウントの増加方法について、以下の 3 つのオプションがあります。

* **[!UICONTROL 参加者ごとに1回]**
* **[!UICONTROL すべてのインプレッション （ページの更新を除く）]**
* **[!UICONTROL すべてのインプレッション]**

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#overview)」を参照してください。

## 統計的手法 {#section_statistical-methodology}

**[!UICONTROL 目標と設定]** ページの&#x200B;**[!UICONTROL 統計的手法]** セクションでは、実験結果の分析方法を選択できます。

### 手法のオプション {#methodology-options}

この選択により、このアクティビティの&#x200B;**[!UICONTROL コンバージョン]**&#x200B;目標指標に使用される統計フレームワーク、結果指標、決定条件が決まります。

* **[!UICONTROL ベイズ &#x200B;]:** データの到達時に信念を更新し、継続的な監視とサンプルサイズの縮小をサポートする確率ベースの意思決定。 結果は、あるバリアントが別のバリアントよりも優れている確率、例えば「バリアント Bがコントロールに勝つ確率92%」として表されます。
  * 小規模なサンプルサイズ、継続的なモニタリング、確率を好む関係者、過去のテストから適用すべき事前知識がある場合に最適です。
  * 厳格な規制やコンプライアンスの承認が必要な場合や、従来のp値が必要な場合は理想的ではありません。
  * レポートには、**[!UICONTROL ビートコントロールの可能性]**&#x200B;と、フリークエンティストの&#x200B;**[!UICONTROL 信頼度]**&#x200B;列の代わりに信頼できる間隔が表示されます。
* **[!UICONTROL ウェルチのt テスト （フリークエンティスト） &#x200B;]:**&#x200B;既存の従来の仮説テスト手法です。 p値を使用し、固定サンプルサイズが必要です。 レポートには、**[!UICONTROL 信頼性]**&#x200B;の割合と信頼区間が表示されます。

この設定は、主な目標指標が&#x200B;**[!UICONTROL コンバージョン]**&#x200B;のアクティビティでのみ使用できます。 **[!UICONTROL 収益]**&#x200B;または&#x200B;**[!UICONTROL エンゲージメント]**&#x200B;の主な目標を持つアクティビティでは、常に&#x200B;**[!UICONTROL ウェルチのt テスト]**&#x200B;を使用します。

各手法の計算方法とレポート方法について詳しくは、[A/Bn テストでの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md)を参照してください。

### ベイズ設定 {#bayesian-configuration}

この設定は、**[!UICONTROL ベイジアン]**&#x200B;が&#x200B;**[!UICONTROL 統計手法]**&#x200B;として選択されている場合にのみ表示されます。 次のオプションを設定します。

* **[!UICONTROL 信頼区間]**：真の効果が想定される範囲を設定します。
* **[!UICONTROL 決定しきい値]**: バリアントが勝者として宣言される前に、**[!UICONTROL Control]**&#x200B;に対して到達しなければならない最小確率を設定します。
* **[!UICONTROL 過去のテストの事前知識を使用しますか？]**：このオプションをオンに切り替えて、過去のパフォーマンスの事前知識を提供し、**[!UICONTROL ベイズ]**&#x200B;計算に反映させます。

## その他のメタデータ {#section_2E8917BEFB954480A4206B9E9E917F80}

**[!UICONTROL 目標と設定]** ページの&#x200B;**[!UICONTROL その他のメタデータ]** セクションでは、自分や他のチームメンバーのために手元に置いておくのに役立つアクティビティに関する情報を指定できます。
