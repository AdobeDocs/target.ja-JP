---
keywords: リダイレクト；リダイレクト url；別のページに送信
description: 同じページにコンテンツを表示するのではなく、別のページに訪問者を送信する場合に、Adobe [!DNL Target]で「URLにリダイレクト」オプションを使用する方法を説明します。
title: ページを別のURLにリダイレクトできますか？
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: 'https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 2%
---
# URL にリダイレクト {#redirect-to-url}

>[!BEGINSHADEBOX]

**このページで：** **[!UICONTROL URLにリダイレクト]** オプションを使用して、同じページにコンテンツを表示するのではなく、別のページに訪問者を送信する方法を説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target]の「**[!UICONTROL URLにリダイレクト]**」オプションは、同じページにコンテンツを表示する代わりに、別のページに訪問者を送信します。 これは、1つのページ内のコンテンツの部分の変更とは対照的に、2つの完全に異なるページの比較に適しています。 A/B テストでは、ページ Aとページ Bを比較します。一方のエクスペリエンスはデフォルトページ Aを指し、もう一方のエクスペリエンスはページ Bにリダイレクトされます。

リダイレクトオファーでは、ブラウザーをリダイレクトするJavaScript コードが実行されます。 このコードは`window.location.replace();` メソッドを使用するため、訪問者がリダイレクトされるページはブラウザー履歴に保存されません。 したがって、訪問者は引き続きブラウザーの「戻る」ボタンを使用できます。

## リダイレクトオファーの作成 {#create-redirect-offer}

リダイレクトするエクスペリエンスは、訪問者を送信するページと、オプションでリダイレクトの条件を定義します。

1. エクスペリエンスを作成します。

1. **[!UICONTROL エクスペリエンス]** フレームから、リダイレクトするエクスペリエンスの&#x200B;**[!UICONTROL 詳細アクション]** アイコン （![詳細アクション アイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックします。

1. 「**[!UICONTROL URLにリダイレクト]**」をクリックします。

   ![その他のアクション アイコン ](assets/redirect_1.png)

1. 「**[!UICONTROL URLにリダイレクト]**」ダイアログボックスで、ページ BのURLを入力します。

   ![その他のアクション アイコン ](assets/redirect_2.png)

1. （オプション）現在のクエリパラメーターを含めるには、オプションを選択します。

   このオプションを選択すると、訪問者のURLの`?`以降のすべてが、リダイレクト時にリダイレクト URLに追加されます。

## 制限事項

リダイレクトオファーには、次の制限があります。

* **A4T:** A4Tを使用するアクティビティのリダイレクト オファーには、特定の最小要件を満たす実装が必要であり、その他の重要な情報が適用されます。 [ リダイレクトオファー – A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)を参照してください。
* **フォームベースのExperience Composer:**&#x200B;は、ページの一部であるmboxでリダイレクト オファーを使用しません。 HTML `<head>`の一部であるスクリプトタグからのみリダイレクトオファーを使用し、常に自動作成を使用してグローバル mboxのリダイレクトオファーを設定します。

>[!NOTE]
>
>ランディングページのリファラー値を渡すには、リダイレクトオファーの代わりにHTML オファーを使用します。

## 既知の問題

at.js実装のリダイレクトアクティビティでは、プレビューURLがループに入り、オファーが繰り返し配信される場合があります。 代わりに、[QA モード ](/help/main/c-activities/c-activity-qa/activity-qa.md)を使用して、アクティビティをプレビューおよびテストします。 この問題は、オファーの実際の配信には影響しません。 （TGT-23019）
