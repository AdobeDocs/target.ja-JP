---
keywords: ターゲティング；analytics；トラッキングサーバー；analytics for target;a4t
description: レポートソース（A4T）として使用する  [!DNL Adobe Target]  の  [!DNL Adobe Analytics]  アクティビティを設定する方法を説明します。
title: ' [!DNL Target] でデータを使用  [!DNL Analytics]  る方法'
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 16%

---

# [!DNL Adobe Analytics] データの使用

[!DNL Adobe Analytics] をレポートソース（A4T）として使用する [!DNL Adobe Target] うに、のアクティビティを設定できます。

[!DNL Analytics] を [!DNL Target] のデータソースとして設定する方法について詳しくは、[Adobe TargetのレポートSourceとしてのAdobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) を参照してください。

[!DNL Analytics] をレポートソースとして使用するアクティビティを設定する前に、訪問者あたりの売上高（RPV）の向上や買い物かごのクリック数の増加など、アクティビティの目標を確立します。 アクティビティの最終的な成功指標を選択します。追加の指標は [!DNL Analytics] でいつでも選択できますが、このテストで影響を受ける特定の指標を指定する必要があります。

>[!NOTE]
>
>[!DNL Adobe Analytics] オプションは、[!DNL Adobe Experience Cloud] アカウントを [!DNL Analytics] と [!DNL Target] の両方にリンクした場合に使用できます。アカウントで [!DNL Target] と [!DNL Analytics] の統合が設定されていない場合でも同様です。

[!DNL Target] のレポートソースとして [!DNL Analytics] を選択する場合は、アクティビティデータを受け取る [!DNL Analytics] レポートスイート [!DNL Target] 選択します。 レポートソースを指定するには、まずアカウントが関連付けられている [!DNL Analytics] の会社のいずれかを選択してから、アクティビティに適したレポートスイートを選択します。 [!DNL Adobe Target] に接続するようにプロビジョニングされているレポートスイートのみを選択できます。 目的のレポートスイートが表示されない場合は、まずログアウトして [!DNL Adobe Experience Cloud] にログインし直し、もう一度試してください。 それでもリストにレポートスイートが表示されない場合は、カスタマーケアへのお問い合わせ。

[!UICONTROL Analytics for Target] （A4T）では、結果を正しく報告するためのトラッキングサーバーが必要です。 デフォルトのトラッキングサーバーが「[!UICONTROL Tracking Server]」フィールドに表示されます。 複数のトラッキングサーバーを使用する場合、このフィールドに正しいトラッキングサーバーが含まれていることを確認してください。 詳しくは [Analytics トラッキングサーバーの使用 ](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) を参照してください。

>[!NOTE]
>
>[!DNL Adobe Analytics] をアクティビティのレポートソースとして使用し、at.js バージョン 0.9.1 （またはそれ以降）を使用している場合は、アクティビティの作成時にトラッキングサーバーを指定する必要はありません。 at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL Goals & Settings] のページの「[!UICONTROL Tracking Server]」フィールドを空白にできます。

[!DNL Analytics] をレポートソースとして設定した後でアクティビティを設定する場合、レポート用にオーディエンスを設定するオプションはありません。 [!DNL Analytics] セグメントは、[!DNL Target] [!UICONTROL Activities] レポートで使用できます。

各アクティビティの目標として使用する成功指標を選択する必要があります。 アクティビティの目標は、アクティビティの成功を示すコンバージョンアクティビティです。ベストプラクティスは、必ず何らかの意味で向上が図れる目標を設定してからテストを実行することです。[!DNL Analytics] 指標セレクターで使用可能な任意の [!DNL Analytics] 指標を選択できます。

目標を設定した場合でも、テスト結果を評価する際に他の指標を使用することは可能です。ただ、この目標は、テストにおいて向上させたいものを明確にする役割を果たします。

訪問者が目標を完了すると、その訪問者はアクティビティに含まれなくなります。 訪問者がアクティビティの完了後にアクティビティに再度入ると、その訪問者は新規訪問者としてカウントされます。
