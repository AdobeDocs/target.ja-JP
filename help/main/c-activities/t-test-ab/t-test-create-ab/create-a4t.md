---
keywords: ターゲティング；分析；トラッキングサーバー；ターゲット用の分析；a4t
description: '[!DNL Adobe Analytics]をレポートソース （A4T）として使用するように[!DNL Adobe Target]でアクティビティを設定する方法について説明します。'
title: '[!DNL Target]で[!DNL Analytics] データを使用するにはどうすればよいですか？'
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: 'https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 891742a5-242d-5099-966a-ca76c17cd2d2
    internal-label: Analytics for Target (A4T)
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%
---
# [!DNL Adobe Analytics] データを使用しています {#create-a4t}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!DNL Adobe Analytics]をレポートソース （A4T）として使用するようにアクティビティを設定する方法、開始する前に準備する方法、アクティビティの目標を選択する方法について説明します。

>[!ENDSHADEBOX]

Analytics for Target （A4T）は、[!DNL Adobe Target] アクティビティの結果を[!DNL Adobe Analytics]のデータと指標で測定します。 A4Tを使用するには、[!DNL Analytics]がレポートソースになるようにアクティビティを設定します。 [!DNL Analytics]を[!DNL Target]のデータソースとして設定する方法について詳しくは、[Adobe Analytics as the Reporting Source for Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md)を参照してください。

## 始める前に {#before-you-begin}

>[!NOTE]
>
>**[!UICONTROL Adobe Analytics]** オプションは、[!DNL Target]と[!DNL Analytics]の間の統合がアカウントに設定されていない場合でも、[!DNL Adobe Experience Cloud] アカウントが[!DNL Analytics]と[!DNL Target]の両方にリンクされている場合に使用できます。

アクティビティを作成する前に、訪問者あたりの売上高（RPV）の向上やショッピングカートへのクリック数の増加など、目標を設定します。 そして、この目標を測定する最終的な成功指標を選択します。 追加の指標はいつでも[!DNL Analytics]で選択できますが、このテストが影響を与えると予想される指標を1つ指定する必要があります。

## レポートソースとして「Analytics」を選択します {#select-reporting-source}

>[!NOTE]
>
>at.js バージョン 0.9.1以降を使用する場合、[!DNL Adobe Analytics]をレポートソースとして使用するアクティビティを作成する際に、トラッキングサーバーを指定する必要はありません。 at.js ライブラリは、トラッキングサーバーの値を自動的に[!DNL Target]に送信します。 **[!UICONTROL 目標と設定]** ページの&#x200B;**[!UICONTROL トラッキングサーバー]** フィールドは空のままにできます。

レポートソースは、アクティビティの&#x200B;**[!UICONTROL 目標と設定]** ページで選択されます。 このページでは、[!DNL Target] アクティビティデータを受け取る[!DNL Analytics]会社とレポートスイートを選択し、トラッキングサーバーを確認します。

➡️手順、レポートスイートの要件、トラッキングサーバーの詳細については、[&#x200B; レポート Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source)を参照してください。

[!DNL Analytics]がレポートソースの場合、アクティビティには、レポート用のオーディエンスを設定するオプションはありません。 [!DNL Analytics] セグメントは、代わりに[!DNL Target] **[!UICONTROL アクティビティ]** レポートで利用できます。

## アクティビティの目標の設定 {#set-goal}

各アクティビティには、目標としての成功指標が必要です。 目標は、成功を示すコンバージョン活動です。 [!DNL Analytics]指標セレクターで使用できる指標はすべて使用できます。 特定の方法で改善することを目標とせずにテストを実行することは決してベストプラクティスです。

目標を設定しても、他の指標を使用してテスト結果を評価することは妨げられません。 ただし、この目標は、テストで改善したい1つのものを特定します。

訪問者が目標を達成すると、その訪問者はアクティビティに含まれなくなります。 訪問者がアクティビティを完了した後に再エントリすると、その訪問者は新規訪問者としてカウントされます。
