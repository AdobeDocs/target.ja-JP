---
keywords: 多変量テスト；トラブルシューティング；トラブルシューティング；mvt
description: ' [!DNL Adobe Target]で[!UICONTROL 多変量テスト &#x200B;] （MVT）アクティビティを使用する際に直面する可能性のある潜在的な課題と、推奨される解決策について説明します。'
title: '[!UICONTROL 多変量テスト &#x200B;]のトラブルシューティング方法を教えてください。'
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
TQID: https://experienceleague.adobe.com/O9lmC1PmICPCOxcMDYVcSdpRoM-bqwKR-79deFIG2mg
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 21%

---

# [!UICONTROL 多変量テスト &#x200B;] アクティビティのトラブルシューティング

この記事では、[!DNL Adobe Target]で[!UICONTROL 多変量テスト &#x200B;] （MVT）を設計する際に発生する可能性のある問題を解決するための推奨事項について説明します。

* アクティビティを編集する際に、[!DNL Analytics] ベースの指標を使用し、レポートスイートが読み込まれない（スピナー表示）場合は、指標を[!DNL Target]指標に切り替えてから、もう一度[!DNL Analytics] ベースの指標に切り替えます。 これで、レポートスイートがロードされるようになります。
* 既に実行中のテストに変更を加えた場合は、テストとそのデータをリセットする可能性があります。

  [!DNL Target]では、ライブアクティビティを編集できます。 処理中のアクティビティを編集すると、テストがリセットされ、レポートが変更の一部を認識しない場合があります。

  既存のテキストまたは HTML オファーなど、小さな変更のみをおこなうようにしてください。

  エクスペリエンス名とレポートをリセットするアクションには、次のものが含まれます。

   * 新しい場所の追加
   * 場所の削除
   * 新しいオファーの追加、または既存の場所からのオファーの削除
