---
keywords: 多変量分析テスト；トラブルシューティング；トラブルシューティング；mvt
description: '[!UICONTROL Multivariate Test] で  [!DNL Adobe Target] （MVT）アクティビティを使用する際に発生する可能性のある課題を、提案されたソリューションと共に紹介します。'
title: '[!UICONTROL Multivariate Test] のトラブルシューティング方法'
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 22%

---

# [!UICONTROL Multivariate Test] アクティビティのトラブルシューティング

この記事では、[!UICONTROL Multivariate Test] で [!DNL Adobe Target] （MVT）を設計する際に発生する可能性のある問題を解決するための推奨事項を説明します。

* アクティビティの編集時に [!DNL Analytics] ベースの指標を使用したが、レポートスイートが読み込まれない（編集ボックスが表示される）場合は、指標を [!DNL Target] ベースの指標に切り替えてから、もう一度 [!DNL Analytics] ベースの指標に切り替えます。 これで、レポートスイートがロードされるようになります。
* 既に実行中のテストに変更を加えると、テストとそのデータがリセットされる場合があります。

  ライブアクティビティを編集で [!DNL Target] ます。 進行中のアクティビティを編集すると、テストがリセットされる可能性があるので、レポートで一部の変更が認識されない場合があります。

  既存のテキストまたは HTML オファーなど、小さな変更のみをおこなうようにしてください。

  エクスペリエンス名およびレポートをリセットする具体的なアクションを次に示します。

   * 新しい場所の追加
   * 場所の削除
   * 新しいオファーの追加、または既存の場所からのオファーの削除
