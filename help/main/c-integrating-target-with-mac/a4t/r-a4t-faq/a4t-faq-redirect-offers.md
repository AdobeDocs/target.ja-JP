---
keywords: FAQ;よくある質問;analytics for target;A4T;リダイレクト;リダイレクトオファー;adobe-mc-sdid;adobe_mc_ref
description: Analytics for  [!DNL Target]  （A4T）使用時のリダイレクトオファーの使用に関する質問への回答を示します。 A4T では、 [!DNL Target]  アクティビティに Analytics のレポート機能を使用できます。
title: A4T でのリダイレクトオファーに関する FAQ はどこで見つけることができますか？
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 51%

---

# リダイレクトオファー - A4T FAQ

このトピックには、[!DNL Adobe Analytics] を [!DNL Adobe Target] のレポートソースとして使用する場合（A4T）のリダイレクトオファーの使用に関するよくある質問に対する回答が含まれています。

## Analytics for Adobe Target（A4T）はリダイレクトオファーをサポートしていますか？ {#section_46B8B03ED4D542C6AD875F5F61176298}

+++回答
はい（実装で [!DNL at.js] を使用している場合）。 ただし、Analytics をレポートソースとして使用するアクティビティで[リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)を使用するには、実装がいくつかの最小要件を満たす必要があります。

+++

## A4T でリダイレクトオファーを使用するための最小要件を教えてください。 {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

+++回答
実装が次の最小要件を満たしている必要があります。

* Experience Cloud 訪問者 ID サービス：[!DNL visitorAPI.js] バージョン 2.3.0 以降。
* Adobe Analytics：[!DNL appMeasurement.js] バージョン 2.1。
* Adobe Target：[!DNL at.js] バージョン 1.6.2 以降。

これら 3 つのライブラリを、リダイレクトオファーを使用するページと訪問者のリダイレクト先となるページの両方に含める必要があります。

+++

## 場合により A4T と Analytics の間でデータに相違があるのはなぜですか。

+++回答
データに多少相違があることが予想されます。詳しくは、[A4T を使用する場合と使用しない場合とでの Target と Analytics 間での予想されるデータの相違](/help/main/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)を参照してください。

+++

## A4T アクティビティでリダイレクトオファーを使用する際に、トラフィック配分の不一致を最小限に抑えるには、どうすればよいですか？ {#discrepancies}

+++回答
[!UICONTROL Analytics for Target] （A4T）で設定されたアクティビティのリダイレクトオファーを使用すると、限られた数の顧客で、トラフィック配分の平方偏差の比率が高く報告されていました。

次の点に留意してください。

* [!DNL Target] と [!DNL Analytics] の呼び出しの順序が正しくないと、分散の度合いが高くなる場合があります。

  [!DNL Target] 呼び出しは、ソースページ（リダイレクトが発生する場所）および宛先ページ（リダイレクトが終了する場所）の [!DNL Analytics] 呼び出しの前に行う必要があります。

* A4T のリダイレクトアクティビティでリダイレクトオファーを使用してください。
* ソースページ（リダイレクトが発生するページ）に複数の [!DNL Target] ロケーションリクエストがある場合、[!DNL Adobe] では、最初の [!DNL Target] ロケーションリクエストでリダイレクトアクティビティを実行することをお勧めします。

  最初の [!DNL Target] 場所リクエストでリダイレクトアクティビティを実行すると、他の [!DNL Target] 場所リクエストでアクティビティの選定が発生し、レポートにカウントされる可能性が低くなります。 リダイレクトされた訪問者は、エクスペリエンスが表示されないので、他のアクティビティのレポートでカウントされる必要はありません。

+++

## 元のページとリダイレクトページでページビュー数がカウントされることがあるのはなぜですか？ {#section_B8F6CC2190B84CF08D945E797C5AF07B}

+++回答
at.js バージョン 1.6.3 以降を使用している場合、両方のページでページビューをカウントしても問題ありません。 この競合条件は、それ以前のバージョンを使用している場合にのみ影響します。Target チームがサポートを提供しているのは、at.js の最新バージョンとその 1 つ前のバージョンの 2 つです。必要に応じて at.js をアップグレードし、[サポート対象のバージョン](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank}を実行していることを確認してください。

at.js の以前のサポートされていないバージョンを使用している場合、最初のページでリダイレクトが実行される前に競合条件が生じ、Analytics の呼び出しが実行されることがあります。元のページとリダイレクトページのページビューがすべてカウントされる可能性があります。 こうしたケースでは、訪問者が最初のページを実際に閲覧しなくても、そのページでページビューが余分にカウントされます。

ページ上でコードが実行される場所により、ページのリダイレクトの速度を速めるには、フォームベースのコンポーザーを使用してリダイレクトアクティビティを作成することをお勧めします。 また、デフォルトのエクスペリエンスも含め、リダイレクトによって元のページが返されるすべてのエクスペリエンスで、リダイレクトオファーを作成することもお勧めします。各エクスペリエンスにリダイレクトオファーを作成すると、誤ったカウントが発生した場合にすべてのエクスペリエンスで発生します。 レポートと分析は、テストに対して引き続き有効です。

デフォルト（コントロール）エクスペリエンスを含む、アクティビティのすべてのエクスペリエンスにリダイレクトオファーを使用したい理由の 1 つは、すべてのエクスペリエンスに同じ条件を課すことです。例えば、デフォルトエクスペリエンスにリダイレクトオファーがなく、他のエクスペリエンスリダイレクトオファーがある場合、リダイレクトオファーのないエクスペリエンスは、速度の点で有利です。リダイレクトオファーは、一時的なシナリオ（テストなど）にのみ推奨されます。リダイレクトオファーは、恒常的なシナリオ（パーソナライゼーションなど）には推奨されません。「勝者」を決定した後、ページ読み込みのパフォーマンスを向上させるために、リダイレクトを削除する必要があります。

+++

## Visual Experience Composer（VEC）とフォームベースの Experience Composer の両方がサポートされていますか？ {#section_FDA26FE7909B48539DA770559E687677}

+++回答
はい。ビルトインのリダイレクトオファーを使用するのであれば、どちらのコンポーザーもサポートされます。

リダイレクトに独自のカスタムコードを使用する場合、リダイレクト URL に関連付けられた 2 つの新しいパラメーター（以下で説明する `adobe_mc_sdid` と `adobe_mc_ref`）を必ず設定する必要があります。

+++

## リダイレクト URL に追加される新しいクエリ文字列パラメーターは何ですか？ {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

+++回答
次のクエリ文字列パラメーターが、リダイレクトオファーに関連付けられます。

| パラメーター | 説明 |
|--- |--- |
| `adobe_mc_sdid` | `adobe_mc_sdid` パラメーターは、追加データ ID （SDID）とExperience Cloud組織 ID をデフォルトページから新しいページに渡します。 これらの ID により、A4T は、デフォルトページの Target リクエストと新しいページの Analytic リクエストを「ステッチ」できます。<br>URL で SDID を渡すと期待される形式（ハイブリッドアプリの場合、またはアプリケーションから Web サイトの場合、または Web サイトから別の Web サイトの場合）は `ex. adobe_mc_sdid=SDID=123|MCORGID=123456789@AdobeOrg|TS=1498569322` です |
| `adobe_mc_ref` | `adobe_mc_ref` パラメーターは、デフォルトのページの参照 URL を新しいページに渡します。AppMeasurement.js バージョン 2.1 （以降）で使用する場合、Analytics はこのパラメーター値を新しいページの参照 URL として使用します。 |

訪問者 ID サービスがページに実装されていると、VEC とフォームベースの Experience Composer で組み込みのリダイレクトオファーを使用する場合に、これらのパラメーターがリダイレクト URL に自動的に追加されます。VEC またはフォームベースのコンポーザーでリダイレクトに独自のカスタムコードを使用している場合、必ずこれらのパラメーターをカスタムコードとともに渡す必要があります。

+++

## Web サーバーで、これらのパラメーターが URL から除去されます。どうすればよいですか？ {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

+++回答
IT チームと協力して、これらのパラメーター（`adobe_mc_sdid` と `adobe_mc_ref`）を許可リストに加えるします。

+++

## A4T でリダイレクトアクティビティを使用しておらず、URL に追加されるこれらの追加のパラメーターが必要ない場合、どうすればよいですか？ {#section_9E608D75FF9349FE96C65FEDD7539F45}

+++回答
次の場合は、カスタムコーディングリダイレクトを使用します。

* リダイレクトアクティビティで A4T を使用していません
* 訪問者 ID サービスが実装されている
* これらのパラメーターを URL に自動的に追加しないようにする必要があります

しかし、ベストプラクティスとして、リファラー情報を `adobe_mc_ref` に正しくレポートするために、URL の [!DNL Analytics] パラメーターを保持することもできます。

+++

## adobe_mc_ref および adobe_mc_sdid パラメーターが実装で二重 URL エンコードされるのはなぜですか？ {#section_5EFE5F012B944C40865731EA18E7E79E}

+++回答
A4T とリダイレクトオファーを使用する場合、Target によって `adobe_mc_ref` パラメーターと `adobe_mc_sdid` パラメーターが URL に追加されます。これらの値は既に URL エンコードされています。ほとんどの場合は、すべてが期待どおりに動作します。しかし、お客様によっては、クエリ文字列パラメーターを再度エンコードしようとするロードバランサーまたは Web サーバーが配置されている場合があります。

訪問者 API は、`adobe_mc_sdid` 値をデコードしようとしたときにこの二重エンコードが原因で SDID 値を抽出できないので、新しい SDID を生成します。このプロセスにより、Target と Analytics に間違った SDID 値が送信され、Analytics レポートでリダイレクトに不均等な分割が見られます。

Adobeでは、IT チームに問い合わせて、これらの値が変換されないように `adobe_mc_ref` と `adobe_mc_sdid` を許可リストに加えるすることをお勧めします。

+++

## 参照 URL を新しいページに渡す必要があるのはなぜですか？ {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

+++回答
訪問者が、リダイレクトアクティビティがライブであるホームページ（[!DNL `www.google.com`]）へのリンクを `www.mysite.com/index.html` クリックし、新しいページ（`www.mysite.com/index2.html`）にリダイレクトされたとします。

以前は、新しいページの [!DNL Analytics] リクエストで、[!DNL `www.mysite.com/index.html`] ではなく [!DNL `www.google.com`] の参照 URL がレポートされていました。 そのため、参照 URL に関連付けられた [!DNL Analytics] のレポート（例えば、マーケティングチャネルレポート）が不正確になっており、報告書には、あなたが [!DNL `www.google.com`] からサイトに来たという事実を失っていました。

[!DNL at.js] バージョン 0.9.6 （以降）および [!DNL AppMeasurement.js] 2.1 （以降）では、新しいページの [!DNL Analytics] リクエストは [!DNL `www.google.com`] の参照 URL をレポートします。

+++

## カスタム／HTML リダイレクトオファーを使用することはできますか？ {#section_E49F9A83A286488C8F1098A040203D7E}

+++回答
いいえ。[!DNL Analytics] をレポートソースとして使用するアクティビティでは（A4T）、ビルトインのリダイレクトオファーを使用する必要があります。[!DNL Target] からは、HTML オファーは不明瞭です。[!DNL Target] は、リダイレクトをインスタンス化する JavaScript を含む HTML の特定部分を認識することができません。

+++

## ![Adobe Experience Platform Web SDK バッジ ](/help/main/assets/platform.png) この [!DNL Adobe Experience Platform Web SDK] は、A4T のリダイレクトオファーをサポートしていますか？ {#platform}

次の FAQ では、[!DNL Platform Web SDK] での A4T の使用とオファーのリダイレクトに関する詳細情報を提供しています。

### Analytics for Target（A4T）ではリダイレクトオファーがサポートされますか？

+++回答
はい、Platform Web SDKを介した A4T では、[ リダイレクトオファー ](/help/main/c-experiences/c-manage-content/offer-redirect.md) をサポートしています。

+++

### [!UICONTROL Visual Experience Composer] （VEC）および [!UICONTROL Form-Based Experience Composer] はサポートされていますか？

+++回答
はい。組み込みのリダイレクトオファーを使用する場合、[[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）と [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md) がサポートされます。

+++

### [!DNL Platform Web SDK] でカスタム/HTML リダイレクトオファーを使用できますか？

+++回答
いいえ。A4T を使用するアクティビティには、組み込みのリダイレクトオファーを使用する必要があります。 [!DNL Target] の観点から見ると、HTML オファーは不透明です。 リダイレク [!DNL Target] をインスタンス化するJavaScriptがHTMLの特定の部分に含まれているとは知りません。

+++
