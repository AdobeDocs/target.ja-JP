---
keywords: ターゲティング;成功;コンバージョン指標;ページスコア指標;ページビュー指標;売上高指標;サイト滞在時間指標;推定値;詳細設定;成功指標;詳細設定;依存関係;依存;カウントを増分、アクティビティでユーザーを保持;カウントを増分、ユーザーをリリース、再エントリを許可;カウントを増分、ユーザーをリリース、再エントリを許可しない;
description: アクティビティの成功を判断するのに役立つ成功指標について学びます。 成功指標には、コンバージョン、売上高、ページビュー数、カスタムスコア、サイト滞在時間が含まれます。
title: 成功指標とは
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: a34d40bef584bfa941731df718cb402c658f5d28
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 44%

---

# [!UICONTROL Success metrics]

[!DNL Adobe Target] の成功指標は、アクティビティのパフォーマンスの測定に役立つ主要な指標です。 これらの指標では、コンバージョン、訪問者あたりの売上高、顧客エンゲージメントなど、重要なビジネス成果を把握し、特定のエクスペリエンスやオファーの影響を評価できます。

例えば、新しいプロモーションによって、訪問者あたりの売上高が増加したり、買い物かごに追加されたアイテムの数が増加したかどうかを追跡できます。 成功指標は、登録、チェックアウト、購入プロセスなどのユーザーフローの問題を特定するのにも役立ち、同時に訪問者全体の行動に関するインサイトを提供します。

## 概要

ま [!DNL Target]、正確なレポートと効果的なトラッキングを確保するために、成功指標は推奨設定を使用して事前設定されます。

コンバージョンイベントでは、デフォルトで **[!UICONTROL Increment count & keep user in activity]設定が使用されます。** この設定は、各訪問者が 1 回だけコンバージョンとしてカウントされることを意味します。 リピートコンバージョンはカウントされません。 これらの訪問者は、セッション全体を通してアクティビティコンテンツを表示し続けます。

同じ設定を使用する売上高指標の場合、訪問者からの最初の注文でのみ注文の詳細が記録されます。 後続の注文ではコンバージョン数が増加しますが、[!UICONTROL Revenue per Visitor (RPV)]、[!UICONTROL Average Order Value (AOV)]、[!DNL Total Sales] などの収益ベースの指標には貢献しません。 これらの追加の注文も、[!UICONTROL Order Details] レポートから除外されます。

>[!NOTE]
>
>[ レポートソースとしての Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用するアクティビティの場合、目標指標は常に「[!UICONTROL Increment Count & Keep User in Activity]」設定と「[!UICONTROL On Every Impression]」設定を使用します。 これらの設定は、*変更できません*。

[!UICONTROL Reporting Settings] の手順の [!UICONTROL Activity Settings page] の [!UICONTROL Goals & Settings] セクションでは、次の成功指標を設定できます。

| 成功指標 | 測定アプローチ | 定義 |
|--- |--- |--- |
| [!UICONTROL Conversion] | コンバージョンベース | コンバージョンとは、訪問者が、定義したサイトに対して、次のようなアクションを実行するときです。 <ul><li>ページが表示された</li><li>mbox が表示された</li><li>要素をクリックしました</li></ul>コンバージョンは訪問者ごとに 1 回としてカウントすることも、訪問者がコンバージョンを達成するたびにカウントすることもできます。 |
| [!UICONTROL Revenue] | コンバージョンベース | 訪問者によって生成された売上高。選択できる売上高指標は 1 つだけです。<ul><li>mbox が表示された</li></ul>収益成功指標に関連するように更新された [!DNL Target] UI の変更について詳しくは、以下の [ 更新  [!DNL Target] UI の変更 ](#changes) を参照してください。 |
| [!UICONTROL Engagement] | エンゲージメントベース | 訪問によって生成されたエンゲージメント。 次のエンゲージメント指標から選択できます。<UL><li>ページビュー：各ユニーク訪問は、コンバージョンとしてカウントされます。</li><li>[!UICONTROL Custom Scoring]：サイト上で訪問したページに割り当てられた値に基づいて計算された集計スコアです。訪問者が最初にアクティビティの最初の表示 [!DNL Target] ータリクエストを見た時点からの数字になります。</li>[!DNL Time on Site]：訪問者がアクティビティの最初の表示 [!DNL Target] ージのリクエストを確認してから、セッション内のリクエストを含む最終ページが読み込まれるまでの訪問に費やされた時間（秒単位）。</UL> |

エンゲージメントベースの指標の場合（コンバージョンベースの指標や収益ベースの指標の場合とは異なり）、訪問者は各訪問でアクティビティの対象を再認定し、そのセッションのカウントを増分する必要があります。 関連付けられた指標は、再評価の後にインクリメントが開始され、各訪問者のセッションの終わりでインクリメントが停止します。30 分間無操作状態が続くと、そのセッションは終了します。したがって、テスト中に結果がすぐに表示されるわけではありませんが、セッションのすべての結果がセッションの終了から数分以内に使用できるようになります。

## カスタム成功指標

カスタムの成功指標も作成できます。

成功指標を選択し、目的を達成するために訪問者がとるアクションを選択します。例えば、[!UICONTROL Conversion] 定の指標を選択し、訪問者あたり 1 回カウントされるように設定してから、訪問者が特定のページ（または一連のページ）を閲覧、特定の [!DNL Target] リクエストを閲覧または特定のリンクをクリック、のいずれの場合に成功とするかを設定します。

有効になっている場合は、「[!UICONTROL Estimated Value of one conversion]」フィールド（[!UICONTROL Page Score] 指標では使用できません）には他の指標の値ではなく、目標に関する値が示されます。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。すべての売上高指標（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales] および [!UICONTROL Orders]）について、予測には [!UICONTROL Revenue per Visitor] が使用されます。 データタイプは通貨です。詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。

アクティビティに対して選択した成功指標は、そのアクティビティのレポートを表示するときに、レポート設定で利用できます。

[!UICONTROL Custom Scoring] や [!UICONTROL Revenue Per Visitor] などの一部の指標では、合計注文額や注文 ID などの情報を渡すようにカスタマイズされた実装が必要です。

## 詳細設定 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

詳細設定を使用して、成功の測定方法を管理します。依存関係の追加、アクティビティでユーザーを保持するか削除するかの選択、参加者ごとに 1 回指標をカウントするか、すべてのインプレッションで指標をカウントするかの選択などのオプションがあります。

[!UICONTROL Advanced Settings] のオプションにアクセスするには、**[!UICONTROL More Actions]** のアイコン（その他のアクションアイコン ![ をクリックし ](/help/main/assets/icons/MoreSmallListVert.svg) から、「**[!UICONTROL Advanced Settings]**」をクリックします。

![詳細設定メニュー](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

[!UICONTROL Advanced Settings] オプション（「[!UICONTROL What will happen after a user encounters this goal]」および「[!UICONTROL How will the count be incremented]」）について詳しくは、[ この目標指標に達した後はどうなりますか ](#what-happens) を参照してください。

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。[!UICONTROL Advanced Settings] オプションは使用できません。 詳しくは、[Adobe Target（A4T）のレポートソースとしての Adobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) を参照してください。

### 依存関係の追加

詳細設定を使用して、訪問者が別の指標を先に達成した場合に 1 つの指標のみを増分する、従属成功指標を作成できます。

例えば、テストコンバージョンが、訪問者がオファーをクリックした場合、または、コンバートする前に特定のページに到達する場合にのみ有効になることがあります。

依存関係機能は、次の場合はサポートされて&#x200B;*いません*。

* [!UICONTROL Recommendations] 個のアクティビティ。 それ以外のすべてのアクティビティタイプには対応しています。
* [Analytics をレポートソース（A4T）として](/help/main/c-integrating-target-with-mac/a4t/a4t.md)使用している場合。
* 「ページが表示されました」指標タイプ。
* Visual Experience Composer（VEC）アクティビティの「要素がクリックされました」指標タイプ。

次の場合、従属成功指標は変換されません。

* 循環依存（指標 1 が指標 2 に依存し、指標 2 が指標 1 に依存する）を作成した場合、どちらの指標もコンバートできません。
* アクティビティ [!UICONTROL Automated Personalization]、コンバージョン指標に依存する指標が変換されないように、ユーザーをリリースし、コンバージョン指標に達した際にアクティビティを再開します。

### ユーザーがこの目標指標に達した後、どうなりますか？ {#what-happens}

ユーザーが目標指標に到達した後の動作について指定するには、詳細設定を使用します。次の表に、利用可能なオプションを示します。

| ユーザーがこの目標指標に達した後 | オプション |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | カウントの増分方法を指定します。<ul><li>参加者ごとに 1 回（デフォルト）</li><li>すべてのインプレッション（ページの更新を除く）</li><li>すべてのインプレッション</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | 訪問者がアクティビティに再度入った場合に表示されるエクスペリエンスを選択します。<ul><li>同じエクスペリエンス（デフォルト）</li><li>ランダムエクスペリエンス</li><li>未表示のエクスペリエンス</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | アクティビティのコンテンツの代わりにユーザーに表示する内容を指定します。<ul><li>トラッキングなしの同じエクスペリエンス（デフォルト）</li><li>デフォルト／他のアクティビティのコンテンツ</li></ul> |

>[!NOTE]
>
>指標を [!UICONTROL Increment Count] のオプション（上記）のいずれかに設定すると、指標カウントは訪問者レベルのみで、参加者ごとに正しく 1 回増分されます。 指標カウントは、訪問レベルで新しいセッションが始まるたびに、訪問ごとに 1 ずつ増分します。

### カウントの増分方法：

目的の動作を選択：

* 参加者ごとに 1 回
* すべてのインプレッション（ページの更新を除く）
* すべてのインプレッション

## 既知の問題

* 詳細オプション「カウントの増分方法」を「すべてのインプレッション」または「すべてのインプレッション（更新を除く）」に設定した成功指標を使用することはできません。これは、1 つの成功指標に別の指標が依存することになるためです。

  インプレッションの発生ごとに成功指標を増分するよう設定されている場合、訪問者がこの成功指標に訪問するたびに [!DNL Target] は訪問者を再度カウントします。[!DNL Target] では、成功指標「メンバーシップ」はその後 0 に設定されるので、次のインプレッションでもカウントが発生することになります。このため、この指標の表示が別の指標の条件になっていると、[!DNL Target] ではユーザーが最初の指標を表示したことを認識できなくなります。

## [!DNL Target] UI の変更を更新しました {#changes}

2015 年 2 月 17 日（PT）に公開された [[!DNL Target Standard/Premium] 25.2.1 リリース ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2) では、更新された [!DNL Target] および [!UICONTROL Visual Experience Composer] （VEC） UI が導入されました。 この節では、特に成功指標の設定と管理に関する、レガシー UI と更新された UI の主な違いについて説明します。

### [!UICONTROL Revenue] 成功指標に関連する UI の変更

更新された [!DNL Target] インターフェイスでは、「[!UICONTROL Default View for Reporting]」ドロップダウンが削除されました。 このフィールドは、以前はレガシー UI の [!DNL Overview]/[!UICONTROL Reports] でデフォルトのレポートビューを保存していたので、冗長でした。

更新された UI では、デフォルトのレポート指標が常に [!UICONTROL Revenue per Visitor (RPV)] に設定されるようになりました。 引き続き、「[!UICONTROL Reports]」セクションのビューをカスタマイズして、分析に最も関連する指標を表示できます。

この変更は、配信指標には影響しません。 この変更は、レポート ビューに表示される既定のフィルターにのみ影響します。 RPV は顧客の間で最も一般的に使用される指標なので、レポートワークフローを効率化するために、このデフォルトが選択されました。 [!UICONTROL Reports] セクション内でいつでも他の指標に切り替えることができます。