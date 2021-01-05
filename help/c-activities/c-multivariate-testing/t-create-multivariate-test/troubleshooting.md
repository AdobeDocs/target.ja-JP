---
keywords: Multivariate Tests;troubleshoot;troubleshooting;mvt
description: このトピックでは、Adobe TargetでMVTテストを設計する際に発生する可能性のあるいくつかの問題の解決方法を提案します。
title: 多変量分析テストのトラブルシューティング
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 45%

---


# 多変量分析テストのトラブルシューティング

このトピックでは、[!DNL Adobe Target]で[!UICONTROL 多変量分析](MVT)テストを設計する際に発生する可能性がある一部の問題の解決方法を提案します。

* アクティビティの編集時に、[!DNL Analytics]ベースの指標を使用していて、レポートスイートが読み込まれない場合（スピナーが表示される場合）は、指標を[!DNL Target]指標に切り替えてから、再度[!DNL Analytics]ベースの指標に切り替えます。 これで、レポートスイートがロードされるようになります。
* 既に実行中のテストに変更を加えた場合、テストとそのデータがリセットされることがあります。

   [!DNL Target] ライブアクティビティを編集できます。進行中のアクティビティを編集するとテストがリセットされ、レポートで一部の変更内容を認識できない場合があることに注意してください。

   既存のテキストまたは HTML オファーなど、小さな変更のみをおこなうようにしてください。

   エクスペリエンス名やレポートがリセットされるアクションには、次のものがあります。

   * 新しい場所の追加
   * 場所の削除
   * 新しいオファーの追加、または既存の場所からのオファーの削除

