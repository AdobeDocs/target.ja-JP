---
keywords: ターゲティング；分析；トラッキングサーバー；ターゲット用の分析；a4t
description: レポートソース（A4T）として [!DNL Adobe Analytics] を使用するように [!DNL Adobe Target] でアクティビティを設定する方法について説明します。
title: ' [!DNL Target]で [!DNL Analytics]  データを使用するにはどうすればよいですか？'
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 492
ht-degree: 19%

---

# [!DNL Adobe Analytics] データを使用しています

[!DNL Adobe Analytics]をレポートソース （A4T）として使用するように、[!DNL Adobe Target]のアクティビティを設定できます。

[!DNL Analytics]を[!DNL Target]のデータソースとして設定する方法について詳しくは、[Adobe Analytics as the Reporting Source for Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md)を参照してください。

[!DNL Analytics]をレポートソースとして使用するアクティビティを設定する前に、訪問者あたりの売上高（RPV）の向上やショッピングカートのクリック数の増加など、アクティビティの目標を設定します。 アクティビティの最終的な成功指標を選択します。 [!DNL Analytics]でいつでも追加の指標を選択できますが、このテストが影響を与えると思われる特定の指標を指定する必要があります。

>[!NOTE]
>
>[!DNL Adobe Analytics] オプションは、[!DNL Adobe Experience Cloud] アカウントを[!DNL Analytics]と[!DNL Target]の両方にリンクしている場合に、[!DNL Target]と[!DNL Analytics]の統合がアカウントに設定されていない場合でも使用できます。

[!DNL Analytics]を[!DNL Target]のレポートソースとして選択する場合、[!DNL Analytics] レポートスイートを選択して[!DNL Target] アクティビティデータを受信します。 レポートソースを指定するには、まずアカウントが関連付けられている[!DNL Analytics]社の中から選択し、アクティビティに適したレポートスイートを選択します。 [!DNL Adobe Target]に接続するようにプロビジョニングされたレポートスイートのみが選択できます。 期待するレポートスイートが表示されない場合は、まずログアウトして[!DNL Adobe Experience Cloud]に再度ログインし、もう一度やり直してください。 レポートスイートがまだリストにない場合は、カスタマーケアにお問い合わせください。

[!UICONTROL Analytics for Target] （A4T）では、結果を正しく報告するためにトラッキングサーバーが必要です。 デフォルトのトラッキングサーバーが「[!UICONTROL &#x200B; トラッキングサーバー]」フィールドに表示されます。 複数のトラッキングサーバーを使用する場合は、このフィールドに正しいトラッキングサーバーを含めるようにしてください。 詳しくは、[Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)を参照してください。

>[!NOTE]
>
>アクティビティのレポートソースとして[!DNL Adobe Analytics]を使用する場合、at.js バージョン 0.9.1以降を使用している場合、アクティビティの作成中にトラッキングサーバーを指定する必要はありません。 at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。 アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

レポートソースとして[!DNL Analytics]を設定した後にアクティビティを設定する場合、レポート用のオーディエンスを設定するオプションはありません。 [!DNL Analytics] セグメントは、[!DNL Target] [!UICONTROL &#x200B; アクティビティ &#x200B;] レポートで利用できます。

各アクティビティの目標として使用する成功指標を選択する必要があります。 アクティビティの目標は、アクティビティの成功を示すコンバージョンアクティビティです。 ベストプラクティスは、必ず何らかの意味で向上が図れる目標を設定してからテストを実行することです。 [!DNL Analytics]指標セレクターで使用できる任意の[!DNL Analytics]指標を選択できます。

目標を設定した場合でも、テスト結果を評価する際に他の指標を使用することは可能です。 ただ、この目標は、テストにおいて向上させたいものを明確にする役割を果たします。

訪問者が目標を達成すると、その訪問者はアクティビティに含まれなくなります。 訪問者がアクティビティを完了した後にアクティビティに再エントリした場合、その訪問者は新規訪問者としてカウントされます。
