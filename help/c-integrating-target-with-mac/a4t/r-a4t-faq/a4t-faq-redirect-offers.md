---
description: このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合のリダイレクトオファーの使用に関するよくある質問に対する回答が含まれています。
keywords: FAQ;よくある質問;analytics for target;A4T;リダイレクト;リダイレクトオファー;adobe-mc-sdid;adobe_mc_ref
seo-description: このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合のリダイレクトオファーの使用に関するよくある質問に対する回答が含まれています。
seo-title: リダイレクトオファー - A4T FAQ
solution: 'Target '
title: リダイレクトオファー - A4T FAQ
topic: Standard
uuid: a45cef89-3003-4177-bf84-3d5a486b950d
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# リダイレクトオファー - A4T FAQ{#redirect-offers-a-t-faq}

このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合のリダイレクトオファーの使用に関するよくある質問に対する回答が含まれています。

## Analytics for Target（A4T）ではリダイレクトオファーがサポートされますか？{#section_46B8B03ED4D542C6AD875F5F61176298}

はい。実装で [!DNL at.js] が使用されている場合にサポートされます。ただし、Analytics をレポートソースとして使用するアクティビティで[リダイレクトオファー](../../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)を使用するには、実装がいくつかの最小要件を満たす必要があります。

## A4T でリダイレクトオファーを使用するために必要な最小要件を教えてください。{#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

実装が次の最小要件を満たしている必要があります。

* Experience Cloud 訪問者 ID サービス：[!DNL visitorAPI.js] バージョン 2.3.0 以降。
* Adobe Analytics：[!DNL appMeasurement.js] バージョン 2.1。
* Adobe Target: [!DNL at.js] バージョン1.6.2以降。

   [!DNL mbox.js] ライブラリを使用している場合、A4T によるリダイレクトオファーはサポートされません。実装では [!DNL at.js] を使用する必要があります。

これら 3 つのライブラリを、リダイレクトオファーを使用するページと訪問者のリダイレクト先となるページの両方に含める必要があります。

## A4TとAnalyticsの間でデータに相違があるのはなぜですか。

データに相違があることがあります。詳しくは、A4Tを使用しない場合のTargetとAnalyticsの間で [のデータの相違を参照](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)してください。

## 元のページとリダイレクトページでページビュー数がカウントされることがあるのはなぜですか？{#section_B8F6CC2190B84CF08D945E797C5AF07B}

最初のページでリダイレクトが実行される前に競合条件が生じ、Analytics の呼び出しが実行される場合があります。その場合は元のページとリダイレクトページでページビュー数がカウントされます。こうしたケースでは、訪問者が最初のページを実際に閲覧しなくても、そのページでページビューが余分にカウントされます。

リダイレクトアクティビティを作成する際は、ページのリダイレクトを高速化するために、フォームベースのコンポーザーを使用することをお勧めします。これは、コードがページ上で実行されるためです。また、デフォルトのエクスペリエンスも含め、リダイレクトによって元のページが返されるすべてのエクスペリエンスで、リダイレクトオファーを作成することもお勧めします。これにより、ページビューが余分にカウントされても、すべてのエクスペリエンスで同様にカウントされるので、テスト用のレポートや分析には問題ありません。

>[!NOTE]
>
>この競合条件は、at.js バージョン 1.6.3 以前を使用している場合にのみ影響します。Target チームが提供している at.js のサポートは、最新バージョンとその 1 つ前のバージョンの 2 つのみであることに注意してください。必要に応じて at.js をアップグレードし、[サポート対象のバージョン](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を実行していることを確認してください。

この問題に関する詳細については、「[既知の問題](../../../r-release-notes/known-issues-resolved-issues.md#concept_625C3A16B7F24D4B82EFF130F0945541)」の表の「リダイレクトオファー」列を参照してください。

## mbox.js JavaScript ライブラリを使用している場合に、A4T でリダイレクトオファーを使用できますか？{#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

[!DNL mbox.js] ライブラリを使用している場合、A4T によるリダイレクトオファーはサポートされません。実装では [!DNL at.js] を使用する必要があります。

## Visual Experience Composer（VEC）とフォームベースの Experience Composer の両方がサポートされていますか？{#section_FDA26FE7909B48539DA770559E687677}

はい。組み込みのリダイレクトオファーを使用するのであれば、どちらのコンポーザーもサポートされます。

リダイレクトに独自のカスタムコードを使用する場合、リダイレクト URL に関連付けられた 2 つの新しいパラメーター（以下で説明する `adobe_mc_sdid` と `adobe_mc_ref`）を必ず設定する必要があります。

## リダイレクト URL に追加される新しいクエリ文字列パラメーターは何ですか？{#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

次のクエリ文字列パラメーターが、リダイレクトオファーに関連付けられます。

| パラメーター | 説明 |
|--- |--- |
| `adobe_mc_sdid` | `adobe_mc_sdid` パラメーターは、追加のデータ ID（SDID）と Experience Cloud 組織 ID をデフォルトのページから新しいページに渡します。これにより、A4T によって、デフォルトのページの Target リクエストが新しいページの Analytic リクエストに「関連付け」られます。 |
| `adobe_mc_ref` | `adobe_mc_ref` パラメーターは、デフォルトのページの参照 URL を新しいページに渡します。AppMeasurement.js バージョン 2.1（またはそれ以降）を使用した場合、このパラメーター値は Analytics によって新しいページの参照 URL として使用されます。 |

訪問者 ID サービスがページに実装されていると、VEC とフォームベースの Experience Composer で組み込みのリダイレクトオファーを使用する場合に、これらのパラメーターがリダイレクト URL に自動的に追加されます。VEC またはフォームベースのコンポーザーでリダイレクトに独自のカスタムコードを使用している場合、必ずこれらのパラメーターをカスタムコードとともに渡す必要があります。

## Web サーバーで、これらのパラメーターが URL から除去されます。どうすればよいですか？ {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

組織の IT チームと協力して、これらのパラメーター（`adobe_mc_sdid` と `adobe_mc_ref`）をホワイトリストに登録する必要があります。

## A4T でリダイレクトアクティビティを使用しておらず、URL に追加されるこれらの追加のパラメーターが必要ない場合、どうすればよいですか？{#section_9E608D75FF9349FE96C65FEDD7539F45}

A4T でリダイレクトアクティビティを使用していない場合、訪問者 ID サービスを実装します。これらのパラメーターが URL に自動的に追加されないようにするには、カスタムコーディングされたリダイレクトを使用する必要があります。

しかし、ベストプラクティスとして、リファラー情報を `adobe_mc_ref` に正しくレポートするために、URL の [!DNL Analytics] パラメーターを保持することもできます。

## 実装で URL が adobe_mc_ref パラメーターと adobe_mc_sdid パラメーターによって二重エンコードされるのはなぜですか？{#section_5EFE5F012B944C40865731EA18E7E79E}

A4T とリダイレクトオファーを使用する場合、Target によって `adobe_mc_ref` パラメーターと `adobe_mc_sdid` パラメーターが URL に追加されます。これらの値は既に URL エンコードされています。ほとんどの場合は、すべてが期待どおりに動作します。しかし、お客様によっては、クエリ文字列パラメーターを再度エンコードしようとするロードバランサーまたは Web サーバーが配置されている場合があります。

訪問者 API は、`adobe_mc_sdid` 値をデコードしようとしたときにこの二重エンコードが原因で SDID 値を抽出できないので、新しい SDID を生成します。これにより、間違った SDID 値が Target と Analytics に送信され、その結果、Analytics レポートにリダイレクトの不均一な分割が表示されます。

これらの値が変換されないようにするために、IT チームに相談して `adobe_mc_ref` と `adobe_mc_sdid` をホワイトリストに登録することをお勧めします。

## 参照 URL を新しいページに渡す必要があるのはなぜですか？{#section_91AB8B0891F6416CBF7E973DCAF54EB5}

[!DNL `www.google.com`] にある、ホームページ（`www.mysite.com/index.html]`）のリンクを訪問者がクリックすると仮定します。このとき、このリンクでリダイレクトアクティビティが有効であり、新しいページ（[!DNL `www.mysite.com/index2.html`]）にリダイレクトされるようになっていると仮定します。

以前は、新しいページの [!DNL Analytics] リクエストによって、[!DNL `www.mysite.com/index.html`] ではなく、[!DNL `www.google.com`] の参照 URL がレポートされていました。そのため、参照 URL に関連付けられた [!DNL Analytics] のレポート（例えば、マーケティングチャネルレポート）が不正確になっており、[!DNL `www.google.com`] からそのサイトにリダイレクトされた事実がレポートから失われていました。

[!DNL at.js] バージョン 0.9.6（またはそれ以降）と [!DNL AppMeasurement.js] 2.1（またはそれ以降）では、新しいページの [!DNL Analytics] リクエストによって、[!DNL `www.google.com`] の参照 URL がレポートされます。

## カスタム／HTML リダイレクトオファーを使用することはできますか？{#section_E49F9A83A286488C8F1098A040203D7E}

いいえ。[!DNL Analytics] をレポートソースとして使用するアクティビティでは（A4T）、組み込みのリダイレクトオファーを使用する必要があります。[!DNL Target] からは、HTML オファーは不明瞭です。[!DNL Target] は、リダイレクトをインスタンス化する JavaScript を含む HTML の特定部分を認識することができません。
