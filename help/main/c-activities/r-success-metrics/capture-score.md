---
keywords: キャプチャスコア;スコア
description: サイトで訪問したページに割り当てられた値に基づいて集計スコアを計算する  [!DNL Target] Adobeでのスコアエンゲージメント指標について説明します。
title: キャプチャスコア指標とは
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 48%

---

# スコアキャプチャ

[!DNL Adobe Target] のキャプチャスコアエンゲージメント指標は、サイト上で訪問したページに割り当てられた値に基づいて、訪問者が最初にキャンペーンの最初の表示 [!DNL Target] ーザーリクエストを見た時点からの集計スコアを計算します。

次の例は、猫の画像と犬の画像の 2 つのエクスペリエンスをテストするキャンペーンのスコアエンゲージメントの計算方法を示しています。

![example_score 画像 ](assets/example_score.png)

この例では、最初の訪問者は猫のエクスペリエンスを体験します。グローバル [!DNL Target] リクエストが、ページの値に基づいてページスコアを渡すと仮定します。 `**any Target request**` に関連付けられた成功指標に対するページ数エンゲージメントをマーケターがキャプチャした場合、訪問スコアは、猫の画像に関する表示リクエスト後に表示されたリクエストに対して累積されます。

最初のページでスコアに 1 が加えられ、2 番目のページで 0.25、3 番目のページで 0.10、4 番目のページで 0.10 がそれぞれ加えられ、合計で 1.45 になります。この数値は、通貨またはポイントのいずれかに換算できます。別の訪問では、訪問者は犬のエクスペリエンスを体験します。表示したページは猫のエクスペリエンスよりも少なかったにも関わらず、スコアは 2.10 と高くなっていますが、これは犬のエクスペリエンスの方がページの価値が高いためです。

獲得コストとアフィリエイトリンクの売上高を計算に入れるには、後続のページフローに示すように、adbox とリダイレクターを渡します。この例では、記事ページ上の両方の [!DNL Target] リクエストがスコアを渡し、おそらく既知の CPM を表していることに注意してください。

![example_score2 画像 ](assets/example_score2.png)

## ページスコアの割り当て

サイトのページに値を割り当てる場合、自分にとってそのページが持つ価値に基づいて割り当てることができます。例えば、料理サイトでは、エクスペリエンスのセクションではなく、特集記事ページのほうが広告を高く売ることができるとします。この場合、特集記事はエクスペリエンスのセクションよりも価値が高くなります。ページにスコアを割り当てることによって、単にエクスペリエンスを閲覧するだけの訪問者よりも特集記事を読む訪問者の方が高い「ポイント」が得られるように、訪問の総合的な「価値」を作成することができます。

ページにスコアを割り当てるには次の 2 つの方法があります。

* [!DNL Target] リクエストで、`mboxPageValue` というパラメーターを作成します。

  例：`('global_mbox', 'mboxPageValue=10');`

  指定された値は、そのリク [!DNL Target] ストを含むページが表示されるたびにスコアに追加されます。 ページ上の複数のリクエストにスコア値が含まれる場合、ページのスコアはすべてのリクエスト値の合計になります。 `mboxPageValue` は、エンゲージメントスコアを取得するために Target リクエストで値を渡すために使用される予約済みのパラメーターです。 正の値も負の値も渡される可能性があります。各訪問者の訪問の最後に合計が計算され、その訪問の合計スコアが算出されます。

* ページの URL で `?mboxPageValue=n` パラメーターを渡します。

  例：`https://www.mydomain.com?mboxPageValue=5`

  このメソッドを使用すると、ページ上の [!DNL Target] リクエストごとのスコアに指定された値が追加されます。 例えば、パラメーター `?mboxPageValue=10` を渡し、ページに 3 つの [!DNL Target] リクエストがある場合、ページのスコアは 30 になります。

>[!NOTE]
>
>アクティビティの最初の表示 [!DNL Target] リクエストの上にある Target リクエストはスコアに含まれません。

ベストプラクティスは、[!DNL Target] リクエストで値を割り当てることです。 これにより、各リクエストの内容に応じて、測定する値を正確に指定できます。

>[!NOTE]
>
>メンテナンスを容易にするために、いくつかの条件付きJavaScript ロジックを使用して、[!DNL at.js] ファイルでサイトのページスコア値の割り当てを設定できます。 これにより、ページに多くのコードを記述しなくても済みます。サポートが必要な場合は、担当のアカウントコンサルタントにお問い合わせください。

上記の 2 つの方法を組み合わせることもできますが、スコアは予期したよりも高くなる場合があります。例えば、3 つの [!DNL Target] リクエストのそれぞれに値 10 を割り当て、4 番目のリクエストにスコアを割り当てない場合、URL パラメーター `?mboxPageValue=5` を渡すと、値が割り当てられた 3 つのリクエストに対するページスコアは 50、30、その後ページ上の 4 つのリクエストのそれぞれに対して 5 になります。

カウンターは、エントリリクエストではなく、最初の表示リクエストで始まります。 例えば、表示要求のないホームページでアクティビティを入力し、表示要求のあるカタログページにリンクした場合、カウンターはカタログページに移動した時点で始まります。

また、費用がかかるページや訪問者が見る価値のないページには、負の値を割り当てることができます。負の値もまたスコアの総計に入れられます。このテクニックを広告から訪問者が移動するページに適用して、CPC の値を判定することができます。また、訪問者がそのページから連絡をとったり、ヘルプを要求することがわかっている連絡先ページやサポートページに、負の値を割り当てることもできます。
