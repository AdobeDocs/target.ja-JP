---
keywords: FAQ;よくある質問;analytics for target;A4T;リダイレクト;リダイレクトオファー;adobe-mc-sdid;adobe_mc_ref
description: Analyticsを [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] アクティビティに使用する場合のリダイレクトオファーの使用に関する質問に対する回答を見つけます。
title: A4Tを使用したリダイレクトオファーに関するFAQはどこで確認できますか？
feature: Analytics for Target（A4T）
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: 3be6ad187b99472ccd3019e6998eba4953e2f5b5
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 62%

---

# リダイレクトオファー - A4T FAQ

このトピックには、[!DNL Adobe Analytics]を[!DNL Adobe Target]のレポートソースとして使用する(A4T)場合のリダイレクトオファーの使用に関するよくある質問に対する回答が含まれています。

## Analytics for Adobe Target(A4T)ではリダイレクトオファーがサポートされますか？ {#section_46B8B03ED4D542C6AD875F5F61176298}

はい、実装で[!DNL at.js]を使用している場合は有効です。 ただし、Analytics をレポートソースとして使用するアクティビティで[リダイレクトオファー](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)を使用するには、実装がいくつかの最小要件を満たす必要があります。

>[!NOTE]
>
>A4T によるリダイレクトを使用するお客様の数に制限があることにより、未関連付けヒット率の割合が高く表示されるという既知の問題があります。[既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md#redirect)を参照してください。

## A4Tでリダイレクトオファーを使用するための最小要件を教えてください。 {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

実装が次の最小要件を満たしている必要があります。

* Experience Cloud 訪問者 ID サービス：[!DNL visitorAPI.js] バージョン 2.3.0 以降。
* Adobe Analytics：[!DNL appMeasurement.js] バージョン 2.1。
* Adobe Target：[!DNL at.js] バージョン 1.6.2 以降。

   [!DNL mbox.js] ライブラリを使用している場合、A4T によるリダイレクトオファーはサポートされません。実装では [!DNL at.js] を使用する必要があります。

これら 3 つのライブラリを、リダイレクトオファーを使用するページと訪問者のリダイレクト先となるページの両方に含める必要があります。

## 場合により A4T と Analytics の間でデータに相違があるのはなぜですか。

データに多少相違があることが予想されます。詳しくは、[A4T を使用する場合と使用しない場合とでの Target と Analytics 間での予想されるデータの相違](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)を参照してください。

## 元のページとリダイレクトページでページビュー数がカウントされることがあるのはなぜですか？ {#section_B8F6CC2190B84CF08D945E797C5AF07B}

at.jsバージョン1.6.3以降を使用する場合、両方のページでページビュー数をカウントするのは問題になりません。 この競合条件は、それ以前のバージョンを使用している場合にのみ影響します。Target チームがサポートを提供しているのは、at.js の最新バージョンとその 1 つ前のバージョンの 2 つです。必要に応じて at.js をアップグレードし、[サポート対象のバージョン](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を実行していることを確認してください。

at.js の以前のサポートされていないバージョンを使用している場合、最初のページでリダイレクトが実行される前に競合条件が生じ、Analytics の呼び出しが実行されることがあります。この状況では、元のページとリダイレクトページでページビューがすべてカウントされる可能性があります。 こうしたケースでは、訪問者が最初のページを実際に閲覧しなくても、そのページでページビューが余分にカウントされます。

ページ上でコードが実行される場所が原因で、フォームベースのコンポーザーを使用してリダイレクトアクティビティを作成することを推奨します。 また、デフォルトのエクスペリエンスも含め、リダイレクトによって元のページが返されるすべてのエクスペリエンスで、リダイレクトオファーを作成することもお勧めします。各エクスペリエンスのリダイレクトオファーを作成すると、カウントミスが発生した場合に、すべてのエクスペリエンスでリダイレクトオファーが発生します。 レポートと分析は、引き続きテストに有効です。

デフォルト（コントロール）エクスペリエンスを含む、アクティビティのすべてのエクスペリエンスにリダイレクトオファーを使用したい理由の 1 つは、すべてのエクスペリエンスに同じ条件を課すことです。例えば、デフォルトエクスペリエンスにリダイレクトオファーがなく、他のエクスペリエンスリダイレクトオファーがある場合、リダイレクトオファーのないエクスペリエンスは、速度の点で有利です。リダイレクトオファーは、一時的なシナリオ（テストなど）にのみ推奨されます。リダイレクトオファーは、恒常的なシナリオ（パーソナライゼーションなど）には推奨されません。「勝者」を決定したら、ページ読み込みのパフォーマンスを向上させるために、リダイレクトを削除する必要があります。

この問題について詳しくは、[既知の問題](/help/r-release-notes/known-issues-resolved-issues.md#redirect)の「リダイレクトオファー」情報を参照してください。

## mbox.js JavaScript ライブラリを使用している場合に、A4T でリダイレクトオファーを使用できますか？ {#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

[!DNL mbox.js] ライブラリを使用している場合、A4T によるリダイレクトオファーはサポートされません。実装では [!DNL at.js] を使用する必要があります。

## Visual Experience Composer（VEC）とフォームベースの Experience Composer の両方がサポートされていますか？ {#section_FDA26FE7909B48539DA770559E687677}

はい。組み込みのリダイレクトオファーを使用するのであれば、どちらのコンポーザーもサポートされます。

リダイレクトに独自のカスタムコードを使用する場合、リダイレクト URL に関連付けられた 2 つの新しいパラメーター（以下で説明する `adobe_mc_sdid` と `adobe_mc_ref`）を必ず設定する必要があります。

## リダイレクト URL に追加される新しいクエリ文字列パラメーターは何ですか？ {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

次のクエリ文字列パラメーターが、リダイレクトオファーに関連付けられます。

| パラメーター | 説明 |
|--- |--- |
| `adobe_mc_sdid` | `adobe_mc_sdid`パラメーターは、Supplemental Data Id(SDID)とExperience Cloud組織IDをデフォルトページから新しいページに渡します。 これらのIDを使用すると、A4Tはデフォルトページ上のTargetリクエストと新しいページ上のAnalyticsリクエストを「ステッチ」できます。 |
| `adobe_mc_ref` | `adobe_mc_ref` パラメーターは、デフォルトのページの参照 URL を新しいページに渡します。AppMeasurement.jsバージョン2.1（またはそれ以降）で使用する場合、Analyticsはこのパラメーター値を新しいページの参照URLとして使用します。 |

訪問者 ID サービスがページに実装されていると、VEC とフォームベースの Experience Composer で組み込みのリダイレクトオファーを使用する場合に、これらのパラメーターがリダイレクト URL に自動的に追加されます。VEC またはフォームベースのコンポーザーでリダイレクトに独自のカスタムコードを使用している場合、必ずこれらのパラメーターをカスタムコードとともに渡す必要があります。

## Web サーバーで、これらのパラメーターが URL から除去されます。どうすればよいですか？ {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

ITチームと協力して、これらのパラメーター（`adobe_mc_sdid`と`adobe_mc_ref`）を許可リストに加えるします。

## A4T でリダイレクトアクティビティを使用しておらず、URL に追加されるこれらの追加のパラメーターが必要ない場合、どうすればよいですか？ {#section_9E608D75FF9349FE96C65FEDD7539F45}

次の場合に、カスタムコードされたリダイレクトを使用します。

* A4Tをリダイレクトアクティビティで使用していない
* 訪問者IDサービスが実装されている
* これらのパラメーターをURLに自動的に追加しない

しかし、ベストプラクティスとして、リファラー情報を `adobe_mc_ref` に正しくレポートするために、URL の [!DNL Analytics] パラメーターを保持することもできます。

## 実装で URL が adobe_mc_ref パラメーターと adobe_mc_sdid パラメーターによって二重エンコードされるのはなぜですか？ {#section_5EFE5F012B944C40865731EA18E7E79E}

A4T とリダイレクトオファーを使用する場合、Target によって `adobe_mc_ref` パラメーターと `adobe_mc_sdid` パラメーターが URL に追加されます。これらの値は既に URL エンコードされています。ほとんどの場合は、すべてが期待どおりに動作します。しかし、お客様によっては、クエリ文字列パラメーターを再度エンコードしようとするロードバランサーまたは Web サーバーが配置されている場合があります。

訪問者 API は、`adobe_mc_sdid` 値をデコードしようとしたときにこの二重エンコードが原因で SDID 値を抽出できないので、新しい SDID を生成します。このプロセスにより、間違ったSDID値がTargetおよびAnalyticsに送信され、Analyticsレポートにリダイレクトの不均一な分割が表示されます。

Adobeは、ITチームに相談して、これらの値が変換されないように`adobe_mc_ref`と`adobe_mc_sdid`を許可リストに加えるすることをお勧めします。

## 参照URLを新しいページに渡す必要があるのはなぜですか？ {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

訪問者が[!DNL `www.google.com`]上のリンクをクリックして、ホームページ(`www.mysite.com/index.html`)にリダイレクトアクティビティがライブになり、新しいページ(`www.mysite.com/index2.html`)にリダイレクトされるとします。

以前は、新しいページの [!DNL Analytics] リクエストによって、[!DNL `www.mysite.com/index.html`] ではなく、[!DNL `www.google.com`] の参照 URL がレポートされていました。そのため、参照 URL に関連付けられた [!DNL Analytics] のレポート（例えば、マーケティングチャネルレポート）が不正確になっており、[!DNL `www.google.com`] からそのサイトにリダイレクトされた事実がレポートから失われていました。

[!DNL at.js]のバージョンが0.9.6（以降）と[!DNL AppMeasurement.js] 2.1（以降）の場合、新しいページの[!DNL Analytics]リクエストは[!DNL `www.google.com`]の参照URLをレポートします。

## カスタム／HTML リダイレクトオファーを使用することはできますか？ {#section_E49F9A83A286488C8F1098A040203D7E}

いいえ。[!DNL Analytics] をレポートソースとして使用するアクティビティでは（A4T）、組み込みのリダイレクトオファーを使用する必要があります。[!DNL Target] からは、HTML オファーは不明瞭です。[!DNL Target] は、リダイレクトをインスタンス化する JavaScript を含む HTML の特定部分を認識することができません。

## ![Adobe Experience Platform Web SDKバッ](/help/assets/platform.png) ジA4Tのリダ [!DNL Adobe Experience Platform Web SDK] イレクトオファーはサポートされていますか？ {#platform}

次のFAQでは、A4Tの使用と[!DNL Platform Web SDK]でのリダイレクトオファーに関する詳細を説明します。

>[!NOTE]
>
>この記事で説明する[!DNL Adobe Experience Platform Web SDK]実装のA4Tサポートは、[!DNL Platform Web SDK]バージョン2.5.0リリース（2021年6月1日）で利用可能になる予定です。

### Analytics for Target（A4T）ではリダイレクトオファーがサポートされますか？

はい。Platform Web SDKを介したA4Tでは、[リダイレクトオファー](/help/c-experiences/c-manage-content/offer-redirect.md)がサポートされます。

### [!UICONTROL Visual Experience Composer](VEC)と[!UICONTROL フォームベースのExperience Composer]はサポートされていますか？

はい。組み込みのリダイレクトオファーを使用する場合、[[!UICONTROL Visual Experience Composer]](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)と[[!UICONTROL フォームベースのExperience Composer]](/help/c-experiences/form-experience-composer.md)がサポートされます。

### [!DNL Platform Web SDK]と共にカスタム/HTMLリダイレクトオファーを使用することはできますか？

いいえ。A4Tを使用するアクティビティでは、組み込みのリダイレクトオファーを使用する必要があります。 [!DNL Target]からは、HTMLオファーは不透明です。[!DNL Target]は、リダイレクトをインスタンス化するJavaScriptがHTMLの特定部分に含まれていることを認識できません。
