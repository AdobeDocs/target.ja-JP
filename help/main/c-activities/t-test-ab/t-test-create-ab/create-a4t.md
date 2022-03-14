---
keywords: ターゲット設定；analytics；トラッキングサーバー；analytics for target;a4t
description: アクティビティをAdobe [!DNL Target] Adobe Analyticsをレポートソースとして使用する場合。 この統合は、 [!DNL Target] (A4T)。
title: Target で Analytics データを使用するにはどうすればよいですか？
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 78%

---

# Analytics データの使用

アクティビティは [!DNL Adobe Target] 使用する [!DNL Adobe Analytics] を使用します (A4T)。

Analytics を Target のデータソースとして設定する方法について詳しくは、 [Adobe TargetのレポートソースとしてのAdobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Analytics をレポートソースとして使用するアクティビティを設定する前に、アクティビティの目標を設定します。例えば、訪問者 1 人あたりの収益（RPV）や、ショッピングカートのクリック増加数などです。キャンペーンの最終的な成功指標を選択します。Analytics ではいつでも追加的な指標を選択できますが、このテストで効果を確かめたい特定の指標を 1 つ指定する必要があります。

>[!NOTE]
>
>Adobe Experience Cloud アカウントを Analytics と Target の両方にリンクしている場合は、Target と Analytics の間の統合がそのアカウントに設定されていなくても、Adobe Analytics オプションを利用できます。

Analytics を Target のレポートソースとして選択する場合、Target アクティビティデータを受け取るための Analytics レポートスイートを選択します。これをおこなうには、最初にアカウントに結び付けられた Analytics の任意のログインカンパニーから選択し、次に、アクティビティに適したレポートスイートを選択します。Adobe Target に接続するようにプロビジョニングされたレポートスイートだけを選択できます。対象のレポートスイートが表示されない場合、最初に、Adobe Experience Cloud からログアウトしてからログインし直して、もう一度試してみてください。それでもレポートスイートがリストに表示されない場合は、カスタマーケアまでお問い合わせください。

Analytics for Target では、結果を正確にレポートするために、トラッキングサーバーが必要です。デフォルトのトラッキングサーバーは、「トラッキングサーバー」フィールドに表示されます。複数のトラッキングサーバーを使用している場合は、このフィールドに適切なトラッキングサーバーが含まれていることを確認してください。詳しくは、[Analytics トラッキングサーバー](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)を参照してください。

>[!NOTE]
>
>Adobe Analyticsをアクティビティのレポートソースとして使用する場合、at.js バージョン 0.9.1（またはそれ以降）を使用している場合は、アクティビティの作成中にトラッキングサーバーを指定する必要はありません。 at.js ライブラリは、トラッキングサーバーの値をに自動的に送信します。 [!DNL Target]. アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

Analytics をレポートソースとして設定した後にアクティビティを設定する場合、レポートのオーディエンスを設定するオプションはありません。Analytics のセグメントはターゲットアクティビティレポートで利用できます。

各テストの目標として使用する成功指標を選択する必要があります。アクティビティの目標は、キャンペーンの成功を示すコンバージョンアクティビティです。ベストプラクティスは、必ず何らかの意味で向上が図れる目標を設定してからテストを実行することです。Analytics の指標セレクターにある Analytics 指標であればどれでも選択できます。

目標を設定した場合でも、テスト結果を評価する際に他の指標を使用することは可能です。ただ、この目標は、テストにおいて向上させたいものを明確にする役割を果たします。

ある訪問者が目標を達成すると、その訪問者はキャンペーンに含まれなくなります。その訪問者が、あるアクティビティを達成した後で再びキャンペーンに参加したときは、その人は新しい訪問者として数えられます。
