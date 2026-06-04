---
kewords: redirect;redirect url;send to different page
description: 同じページにコンテンツを表示するのではなく、別のページに訪問者を送信する場合に、Adobe [!DNL Target] で「URLにリダイレクト」オプションを使用する方法を説明します。
title: ページを別のURLにリダイレクトできますか？
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 80%

---

# URL にリダイレクト

同じページにコンテンツを表示するのではなく、別のページに訪問者を送信する場合は、[!DNL Adobe Target]の「[!UICONTROL URLにリダイレクト ]」オプションを使用します。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。 この場合、A/B テストではページ A とページ B を比較します。A/B テストキャンペーンを 2 つのエクスペリエンスで設定します。1 つはデフォルトのページ A をポイントするエクスペリエンス、もう 1 つはページ B にリダイレクトするエクスペリエンスです。エクスペリエンスに対して表示される文字のラベルをクリックして表示できるエクスペリエンスのアクションメニューで、「**[!UICONTROL URL にリダイレクト]**」を選択して、ページ B の URL を指定します。訪問者を別のページにリダイレクトするオファーが設定されます。

リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。 このオファーでは`window.location.replace();`メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。 そのため、訪問者はブラウザーの「戻る」ボタンを引き続き使用できます。

リダイレクトオファーには、いくつかの制限があります。

* A4T を使用してアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。 また、知っておくべき重要な情報があります。 詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。
* フォームベースの Experience Composer を使用する場合、リダイレクトオファーはページの一部である mbox で使用しないでください。 リダイレクトオファーは、HTML の`<head>`の一部であるスクリプトタグからのみ使用する必要があります。 常に自動作成を使用して、グローバル mbox にリダイレクトオファーを設定する必要があります。

>[!NOTE]
>
>ランディングページのリファラー値を渡す場合、リダイレクトオファーではなく HTML オファーを使用することをお勧めします。

リダイレクトオファーを作成する手順は次のとおりです。

1. エクスペリエンスを作成します。
1. [!UICONTROL  エクスペリエンス ] フレームから、目的のエクスペリエンスの&#x200B;**[!UICONTROL 詳細アクション]** アイコン （![詳細アクション アイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックします。
1. 「**[!UICONTROL URLにリダイレクト]**」をクリックします。
1. URLにリダイレクト ダイアログボックスで、URLを入力します。
1. 必要に応じて、現在のクエリパラメーターを含めるオプションを選択します。

   このオプションを選択すると、 訪問者の URL の ? の後にある要素が、リダイレクト時にリダイレクト URL に追加されます。

1. （オプション）追加のルールを作成します。

   追加のルールは、以下のいずれかに基づいています。

   * URL
   * ドメイン
   * パス
   * ハッシュ（#）フラグメント
   * クエリ
   * mbox パラメーター

   追加のルールは、AND または OR を使用してアクティビティ URL と結合できます。 追加したすべてのルールは、AND を使用してお互いに評価されます。

## 既知の問題

* at.js 実装でのアクティビティのリダイレクトは、プレビュー URL がループする原因となる可能性があります（オファーが繰り返し配信されます）。 代わりに [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md) を使用して、プレビューと QA を実行できます。 この問題は、実際のオファーの配信には影響しません。 （TGT-23019）
