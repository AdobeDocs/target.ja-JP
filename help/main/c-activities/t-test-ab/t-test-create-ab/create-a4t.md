---
keywords: ターゲット設定；analytics；トラッキングサーバー；analytics for target;a4t
description: でアクティビティを設定する方法を説明します。 [!DNL Adobe Target] 使用する [!DNL Adobe Analytics] を使用します (A4T)。
title: 使用方法 [!DNL Analytics] データ入力 [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 19%

---

# 使用 [!DNL Adobe Analytics] データ

アクティビティは [!DNL Adobe Target] 使用する [!DNL Adobe Analytics] を使用します (A4T)。

を設定する方法について詳しくは、 [!DNL Analytics] を [!DNL Target]を参照してください。 [Adobe TargetのレポートソースとしてのAdobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

を使用するアクティビティを設定する前に [!DNL Analytics] レポートソースとして、訪問者あたりの売上高 (RPV) の向上や買い物かごのクリック数の増加など、アクティビティの目標を設定します。 アクティビティの最終的な成功指標を選択します。ただし、 [!DNL Analytics]に値を入力しない場合でも、このテストの対象となる特定の指標を指定する必要があります。

>[!NOTE]
>
>The [!DNL Adobe Analytics] 」オプションは、 [!DNL Adobe Experience Cloud] 両方を考慮する [!DNL Analytics] および [!DNL Target]( [!DNL Target] および [!DNL Analytics] はお使いのアカウント用に設定されていません。

選択時 [!DNL Analytics] レポートソースとして [!DNL Target]を選択した場合、 [!DNL Analytics] 受信するレポートスイート [!DNL Target] アクティビティデータ。 レポートソースを指定するには、まず次のいずれかから選択します。 [!DNL Analytics] アカウントに結び付けられた会社を選択し、アクティビティに適したレポートスイートを選択します。 接続するようにプロビジョニングされたレポートスイートのみ [!DNL Adobe Target] は選択可能です。 対象のレポートスイートが表示されない場合は、まず、ログアウトしてから、 [!DNL Adobe Experience Cloud] 再度お試しください。 それでもレポートスイートがリストに表示されない場合は、カスタマーケアにお問い合わせください。

[!UICONTROL Analytics for Target] (A4T) 結果を正しくレポートするには、トラッキングサーバーが必要です。 デフォルトのトラッキングサーバーが [!UICONTROL トラッキングサーバー] フィールドに入力します。 複数のトラッキングサーバーを使用する場合は、このフィールドに正しいトラッキングサーバーが含まれていることを確認してください。 詳しくは、 [Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) を参照してください。

>[!NOTE]
>
>次を使用する場合、 [!DNL Adobe Analytics] at.js バージョン 0.9.1（またはそれ以降）を使用している場合、アクティビティのレポートソースとして、アクティビティの作成中にトラッキングサーバーを指定する必要はありません。 at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

設定後にアクティビティを設定する場合 [!DNL Analytics] レポートソースとして、レポート用のオーディエンスを設定するオプションはありません。 [!DNL Analytics] セグメントは、 [!DNL Target] [!UICONTROL アクティビティ] レポート。

各アクティビティの目標として使用する成功指標を選択する必要があります。 アクティビティの目標は、アクティビティの成功を示すコンバージョンアクティビティです。ベストプラクティスは、必ず何らかの意味で向上が図れる目標を設定してからテストを実行することです。任意の [!DNL Analytics] 指標 [!DNL Analytics] 指標セレクターを使用します。

目標を設定した場合でも、テスト結果を評価する際に他の指標を使用することは可能です。ただ、この目標は、テストにおいて向上させたいものを明確にする役割を果たします。

訪問者が目標を達成すると、その訪問者はアクティビティに含まれなくなります。 アクティビティの完了後に訪問者が再度アクティビティに参加した場合、その訪問者は新規訪問者としてカウントされます。
