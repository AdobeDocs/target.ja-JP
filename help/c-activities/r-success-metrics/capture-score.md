---
keywords: capture score;score
description: スコアキャプチャのエンゲージメント指標では、訪問者がキャンペーンの最初の表示ターゲットリクエストを最初に見た時点から、サイトで訪問されたページに割り当てられた値に基づいて集計スコアを計算します。
title: スコアキャプチャ
feature: null
subtopic: Getting Started
topic: Standard
uuid: 977454ad-da32-449a-a8c9-1f3c75220be6
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 51%

---


# スコアキャプチャ{#capture-score}

The Capture Score engagement metric calculates an aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the campaign&#39;s first display [!DNL Target] request.

次の例は、猫の画像と犬の画像の 2 つのエクスペリエンスをテストするキャンペーンのスコアエンゲージメントの計算方法を示しています。

![](assets/example_score.png)

この例では、最初の訪問者は猫のエクスペリエンスを体験します。Assume that a global [!DNL Target] request passes in a page score based on the value of the page. If the marketer has captured page count engagement on a success metric associated with `**any Target request**`, the visit score accumulates for any request seen after the display request around the cat image.

最初のページでスコアに 1 が加えられ、2 番目のページで 0.25、3 番目のページで 0.10、4 番目のページで 0.10 がそれぞれ加えられ、合計で 1.45 になります。この数値は、通貨またはポイントのいずれかに換算できます。別の訪問では、訪問者は犬のエクスペリエンスを体験します。表示したページは猫のエクスペリエンスよりも少なかったにも関わらず、スコアは 2.10 と高くなっていますが、これは犬のエクスペリエンスの方がページの価値が高いためです。

獲得コストとアフィリエイトリンクの売上高を計算に入れるには、後続のページフローに示すように、adbox とリダイレクターを渡します。Notice that, in this example, both [!DNL Target] requests on the article page pass a score, possibly representing a known CPM.

![](assets/example_score2.png)

**ページスコアの割り当て**

サイトのページに値を割り当てる場合、自分にとってそのページが持つ価値に基づいて割り当てることができます。例えば、料理サイトでは、エクスペリエンスのセクションではなく、特集記事ページのほうが広告を高く売ることができるとします。この場合、特集記事はエクスペリエンスのセクションよりも価値が高くなります。ページにスコアを割り当てることによって、単にエクスペリエンスを閲覧するだけの訪問者よりも特集記事を読む訪問者の方が高い「ポイント」が得られるように、訪問の総合的な「価値」を作成することができます。

ページにスコアを割り当てるには次の 2 つの方法があります。

* リクエストで、という名前のパラメーターを作成し [!DNL Target]`mboxPageValue`ます。

   例：`('global_mbox', 'mboxPageValue=10');`

   The specified value is added to the score every time the page with that [!DNL Target] request is viewed. ページ上の複数のリクエストにスコア値が含まれる場合、そのページのスコアはすべてのリクエスト値の合計になります。 `mboxPageValue` は、エンゲージメントスコアを取り込むためにターゲットリクエストに値を渡すために予約されたパラメーターです。 正の値も負の値も渡される可能性があります。各訪問者の訪問の最後に合計が計算され、その訪問の合計スコアが算出されます。

* ページの URL で `?mboxPageValue=n` パラメーターを渡します。

   例：`https://www.mydomain.com?mboxPageValue=5`

   Using this method, the specified value is added to the score for each [!DNL Target] request on the page. For example, if you pass the parameter `?mboxPageValue=10`and there are three [!DNL Target] requests on the page, the score for the page is 30.

>[!NOTE]
>
>アクティビティの最初の表示 [!DNL Target] 要求の上にあるターゲット要求は、スコアに含まれません。

Best practice is to assign values in the [!DNL Target] request. これにより、各リクエストの内容に応じて、測定する値を正確に指定できます。

>[!NOTE]
>
>メンテナンスを容易にするために、JavaScript の条件ロジックを含んだ [!DNL at.js] または [!DNL mbox.js] ファイル内で、サイトのページスコア値の割り当てを設定できます。これにより、ページに多くのコードを記述しなくても済みます。サポートが必要な場合は、担当のアカウントコンサルタントにお問い合わせください。

上記の 2 つの方法を組み合わせることもできますが、スコアは予期したよりも高くなる場合があります。For example, if you assign a value of 10 to each of three [!DNL Target] requests and no score to a fourth request, then pass the URL parameter `?mboxPageValue=5`, your page score will be 50, 30 for the three requests with assigned values, and then 5 for each of the four requests on the page.

カウンター開始は、入口要求ではなく、最初の表示要求を持ちます。 例えば、表示要求のないホームページのアクティビティに入り、表示要求を含むカタログページにリンクすると、カウンターはカタログページに移動した時点から開始されます。

また、費用がかかるページや訪問者が見る価値のないページには、負の値を割り当てることができます。負の値もまたスコアの総計に入れられます。このテクニックを広告から訪問者が移動するページに適用して、CPC の値を判定することができます。また、訪問者がそのページから連絡をとったり、ヘルプを要求することがわかっている連絡先ページやサポートページに、負の値を割り当てることもできます。
