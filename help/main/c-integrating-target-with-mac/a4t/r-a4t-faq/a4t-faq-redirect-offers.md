---
keywords: FAQ;よくある質問;analytics for target;A4T;リダイレクト;リダイレクトオファー;adobe-mc-sdid;adobe_mc_ref
description: Analytics を使用して [!DNL Target] (A4T)。 A4T では、 [!DNL Target]  アクティビティに Analytics のレポート機能を使用できます。
title: A4T を使用したリダイレクトオファーに関する FAQ はどこで確認できますか？
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 55%

---

# リダイレクトオファー - A4T FAQ

このトピックには、 [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T)。

## Analytics for Adobe Target(A4T) ではリダイレクトオファーがサポートされますか？ {#section_46B8B03ED4D542C6AD875F5F61176298}

はい、実装で [!DNL at.js]. ただし、Analytics をレポートソースとして使用するアクティビティで[リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)を使用するには、実装がいくつかの最小要件を満たす必要があります。

>[!NOTE]
>
>A4T によるリダイレクトを使用するお客様の数に制限があることにより、未関連付けヒット率の割合が高く表示されるという既知の問題があります。[既知の問題と解決された問題](/help/main/r-release-notes/known-issues-resolved-issues.md#redirect)を参照してください。

## A4T でリダイレクトオファーを使用するための最小要件を教えてください。 {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

実装が次の最小要件を満たしている必要があります。

* Experience Cloud 訪問者 ID サービス：[!DNL visitorAPI.js] バージョン 2.3.0 以降。
* Adobe Analytics：[!DNL appMeasurement.js] バージョン 2.1。
* Adobe Target：[!DNL at.js] バージョン 1.6.2 以降。

これら 3 つのライブラリを、リダイレクトオファーを使用するページと訪問者のリダイレクト先となるページの両方に含める必要があります。

## 場合により A4T と Analytics の間でデータに相違があるのはなぜですか。

データに多少相違があることが予想されます。詳しくは、[A4T を使用する場合と使用しない場合とでの Target と Analytics 間での予想されるデータの相違](/help/main/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)を参照してください。

## A4T アクティビティでリダイレクトオファーを使用する際に、トラフィック配分の不一致を最小限に抑えるには、どうすればよいですか？ {#discrepancies}

限られた数のお客様が、 [!UICONTROL Analytics for Target] (A4T)。

次の点に留意してください。

* 順序が正しくありません [!DNL Target] および [!DNL Analytics] 呼び出しは、より高い分散度を引き起こす可能性があります。

   この [!DNL Target] 呼び出しは [!DNL Analytics] を呼び出す（リダイレクトが発生する場合）ことをお勧めします。

* A4T のリダイレクトアクティビティでリダイレクトオファーを使用していることを確認します。
* 複数の [!DNL Target] （リダイレクトが発生する）ソースページの場所リクエスト [!DNL Adobe] では、最初の [!DNL Target] 場所のリクエスト。

   最初の [!DNL Target] 場所のリクエストを使用すると、他のでアクティビティの選定がおこなわれる可能性が低くなります [!DNL Target] 場所のリクエストと、レポートでカウントされる情報を含んでいます。 リダイレクトされた訪問者は、エクスペリエンスが表示されないので、他のアクティビティのレポートでカウントされる必要はありません。

## 元のページとリダイレクトページでページビュー数がカウントされることがあるのはなぜですか？ {#section_B8F6CC2190B84CF08D945E797C5AF07B}

at.js バージョン 1.6.3 以降を使用する場合、両方のページでページビュー数をカウントすることは問題になりません。 この競合条件は、それ以前のバージョンを使用している場合にのみ影響します。Target チームがサポートを提供しているのは、at.js の最新バージョンとその 1 つ前のバージョンの 2 つです。必要に応じて at.js をアップグレードし、 [サポート対象バージョン](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}。

at.js の以前のサポートされていないバージョンを使用している場合、最初のページでリダイレクトが実行される前に競合条件が生じ、Analytics の呼び出しが実行されることがあります。この状況では、元のページとリダイレクトページでのページビュー数がすべてカウントされる可能性があります。 こうしたケースでは、訪問者が最初のページを実際に閲覧しなくても、そのページでページビューが余分にカウントされます。

ページ上でコードが実行される場所が原因で、フォームベースのコンポーザーを使用してリダイレクトアクティビティを作成することは、ページリダイレクトの速度を向上させることをお勧めします。 また、デフォルトのエクスペリエンスも含め、リダイレクトによって元のページが返されるすべてのエクスペリエンスで、リダイレクトオファーを作成することもお勧めします。各エクスペリエンスのリダイレクトオファーを作成すると、誤ったカウントが発生した場合に、すべてのエクスペリエンスでリダイレクトオファーが発生します。 レポートと分析は、引き続きテストに有効です。

デフォルト（コントロール）エクスペリエンスを含む、アクティビティのすべてのエクスペリエンスにリダイレクトオファーを使用したい理由の 1 つは、すべてのエクスペリエンスに同じ条件を課すことです。例えば、デフォルトエクスペリエンスにリダイレクトオファーがなく、他のエクスペリエンスリダイレクトオファーがある場合、リダイレクトオファーのないエクスペリエンスは、速度の点で有利です。リダイレクトオファーは、一時的なシナリオ（テストなど）にのみ推奨されます。リダイレクトオファーは、恒常的なシナリオ（パーソナライゼーションなど）には推奨されません。「勝者」を決定したら、ページ読み込みのパフォーマンスを向上させるために、リダイレクトを削除する必要があります。

この問題について詳しくは、[既知の問題](/help/main/r-release-notes/known-issues-resolved-issues.md#redirect)の「リダイレクトオファー」情報を参照してください。

## Visual Experience Composer（VEC）とフォームベースの Experience Composer の両方がサポートされていますか？ {#section_FDA26FE7909B48539DA770559E687677}

はい。組み込みのリダイレクトオファーを使用するのであれば、どちらのコンポーザーもサポートされます。

リダイレクトに独自のカスタムコードを使用する場合、リダイレクト URL に関連付けられた 2 つの新しいパラメーター（以下で説明する `adobe_mc_sdid` と `adobe_mc_ref`）を必ず設定する必要があります。

## リダイレクト URL に追加される新しいクエリ文字列パラメーターは何ですか？ {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

次のクエリ文字列パラメーターが、リダイレクトオファーに関連付けられます。

| パラメーター | 説明 |
|--- |--- |
| `adobe_mc_sdid` | この `adobe_mc_sdid` パラメーターは、追加データ ID(SDID) およびExperience Cloud組織 ID をデフォルトページから新しいページに渡します。 これらの ID を使用すると、A4T はデフォルトページの Target リクエストと新しいページの Analytic リクエストを「ステッチ」できます。 |
| `adobe_mc_ref` | `adobe_mc_ref` パラメーターは、デフォルトのページの参照 URL を新しいページに渡します。AppMeasurement.js バージョン 2.1（またはそれ以降）で使用する場合、Analytics はこのパラメーター値を新しいページの参照 URL として使用します。 |

訪問者 ID サービスがページに実装されていると、VEC とフォームベースの Experience Composer で組み込みのリダイレクトオファーを使用する場合に、これらのパラメーターがリダイレクト URL に自動的に追加されます。VEC またはフォームベースのコンポーザーでリダイレクトに独自のカスタムコードを使用している場合、必ずこれらのパラメーターをカスタムコードとともに渡す必要があります。

## Web サーバーで、これらのパラメーターが URL から除去されます。どうすればよいですか？ {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

IT チームと協力して、次のパラメータ ( `adobe_mc_sdid` および `adobe_mc_ref`)許可リストに加える

## A4T でリダイレクトアクティビティを使用しておらず、URL に追加されるこれらの追加のパラメーターが必要ない場合、どうすればよいですか？ {#section_9E608D75FF9349FE96C65FEDD7539F45}

次の場合に、カスタムコードされたリダイレクトを使用します。

* A4T をリダイレクトアクティビティで使用していない
* 訪問者 ID サービスが実装されている
* これらのパラメーターを URL に自動的に追加したくない場合

しかし、ベストプラクティスとして、リファラー情報を `adobe_mc_ref` に正しくレポートするために、URL の [!DNL Analytics] パラメーターを保持することもできます。

## 実装で URL が adobe_mc_ref パラメーターと adobe_mc_sdid パラメーターによって二重エンコードされるのはなぜですか？ {#section_5EFE5F012B944C40865731EA18E7E79E}

A4T とリダイレクトオファーを使用する場合、Target によって `adobe_mc_ref` パラメーターと `adobe_mc_sdid` パラメーターが URL に追加されます。これらの値は既に URL エンコードされています。ほとんどの場合は、すべてが期待どおりに動作します。しかし、お客様によっては、クエリ文字列パラメーターを再度エンコードしようとするロードバランサーまたは Web サーバーが配置されている場合があります。

訪問者 API は、`adobe_mc_sdid` 値をデコードしようとしたときにこの二重エンコードが原因で SDID 値を抽出できないので、新しい SDID を生成します。このプロセスにより、間違った SDID 値が Target および Analytics に送信され、Analytics レポートにリダイレクトの不均等な分割が表示されます。

Adobeは、IT チームに問い合わせて、 `adobe_mc_ref` および `adobe_mc_sdid` これらの値が変換されないように許可リストに加えるされます。

## 参照 URL を新しいページに渡す必要があるのはなぜですか？ {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

訪問者がリンクをクリックしたとします。 [!DNL `www.google.com`] をホームページ (`www.mysite.com/index.html`) にリダイレクトされ、その後、新しいページ (`www.mysite.com/index2.html`) をクリックします。

以前は、新しいページの [!DNL Analytics] リクエストによって、[!DNL `www.mysite.com/index.html`] ではなく、[!DNL `www.google.com`] の参照 URL がレポートされていました。そのため、参照 URL に関連付けられた [!DNL Analytics] のレポート（例えば、マーケティングチャネルレポート）が不正確になっており、[!DNL `www.google.com`] からそのサイトにリダイレクトされた事実がレポートから失われていました。

を使用 [!DNL at.js] バージョン 0.9.6（またはそれ以降） [!DNL AppMeasurement.js] 2.1（以降）の場合は、 [!DNL Analytics] 新しいページでのリクエストは、 [!DNL `www.google.com`].

## カスタム／HTML リダイレクトオファーを使用することはできますか？ {#section_E49F9A83A286488C8F1098A040203D7E}

いいえ。[!DNL Analytics] をレポートソースとして使用するアクティビティでは（A4T）、組み込みのリダイレクトオファーを使用する必要があります。[!DNL Target] からは、HTML オファーは不明瞭です。[!DNL Target] は、リダイレクトをインスタンス化する JavaScript を含む HTML の特定部分を認識することができません。

## ![Adobe Experience Platform Web SDK バッジ](/help/main/assets/platform.png) を実行します。 [!DNL Adobe Experience Platform Web SDK] A4T のリダイレクトオファーをサポートしますか？ {#platform}

次の FAQ では、A4T の使用に関する詳細と、 [!DNL Platform Web SDK].

### Analytics for Target（A4T）ではリダイレクトオファーがサポートされますか？

はい、Platform Web SDK 経由での A4T では、 [リダイレクトオファー](/help/main/c-experiences/c-manage-content/offer-redirect.md).

### は [!UICONTROL Visual Experience Composer] (VEC) および [!UICONTROL フォームベースの Experience Composer] サポート対象？

はい、 [[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) および [[!UICONTROL フォームベースの Experience Composer]](/help/main/c-experiences/form-experience-composer.md) は、組み込みのリダイレクトオファーを使用する場合にサポートされます。

### カスタム/HTMLリダイレクトオファーを [!DNL Platform Web SDK]?

いいえ。A4T を使用するアクティビティでは、組み込みのリダイレクトオファーを使用する必要があります。 次の [!DNL Target] パースペクティブ、HTMLオファーは不透明です。 [!DNL Target] は、リダイレクトをインスタンス化する JavaScript が含まれているHTMLを特定できない。
