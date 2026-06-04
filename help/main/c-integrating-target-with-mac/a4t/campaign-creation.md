---
keywords: a4t;A4T;Target のレポートソースとしての Analytics
description: Adobe Analyticsをレポートソース（A4T）として使用するAdobe [!DNL Target] でアクティビティを設定する方法について説明します。
title: A4Tを使用するアクティビティを作成するにはどうすればよいですか？
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
TQID: https://experienceleague.adobe.com/7fdf22c0HzpPYQbKgGjHEy23oJQsjQTJpfqy93mG1kI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 30%

---

# Analytics をレポートソースとして使用するアクティビティの作成

[!DNL Adobe Analytics]をレポートソース （A4T）として使用するように、[!DNL Adobe Target]のアクティビティを設定できます。

[!DNL Analytics]をレポートソースとして使用するアクティビティを設定する前に、訪問者あたりの売上高（RPV）の向上やショッピングカートのクリック数の増加など、アクティビティの目標を設定します。 アクティビティの最終的な成功指標を選択します。 [!DNL Analytics]でいつでも他の指標を選択できますが、このテストが影響を与えると思われる特定の指標を指定する必要があります。

## アクティビティの作成

レポートソースとして[!DNL Analytics]を使用する[!DNL Target] アクティビティの作成は、通常の[!DNL Target] アクティビティの設定と似ていますが、いくつかの重要な違いがあります。 例えば、[!DNL Analytics]で使用可能なすべてのセグメントは、レポートの表示時に適用できるため、アクティビティの作成中にレポート用のセグメントを選択することはできません。

1. 「**[!UICONTROL アクティビティを作成]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Analytics]がレポートソースとして使用されている場合、アクティビティ名に「%」文字を含めることはできません。
   >
   >A4T レポートを使用している別々の[ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)の2つのアクティビティに対して、同じアクティビティ名を使用しないでください。

1. アクティビティのタイプを選択して、アクティビティの設定を開始します。

   [!UICONTROL 自動配分]または[!UICONTROL 自動ターゲット ] アクティビティを作成する場合は、[自動配分と自動ターゲット アクティビティのA4T サポート ](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。

1. アクティビティ作成フローの&#x200B;**[!UICONTROL Settings]**&#x200B;部分にアクセスしたら、**[!UICONTROL Adobe Analytics]**&#x200B;を選択し、会社を指定します。
1. レポートスイートを選択します。

   [!DNL Analytics]で使用可能な任意のレポートスイートを選択できます。 レポートスイートでは、収集されたデータの利用場所を定義します。 仮想レポートスイートは、レポートスイートリストには含まれません。

   レポートスイートを選択する際に、次の 2 つのエラーが発生する可能性があります。

   * レポートスイートが利用できないが、アカウントが正しく設定されているというエラーが表示されます。

     お客様の[!DNL Analytics]社をご確認ください。 お客様の[!DNL Adobe Experience Cloud] アカウントが複数の[!DNL Analytics]企業に関連付けられている場合は、[!DNL Target]からログアウトし、適切な企業下の[!DNL Analytics]にログインしてください。 次に[!DNL Target]に戻り、レポートスイートが読み込まれます。

   * 対象のレポートスイートが表示されません。

     [!DNL Target]に接続するようにプロビジョニングされたレポートスイートのみが選択できます。 期待するレポートスイートが表示されない場合は、まずログアウトして[!DNL Adobe Experience Cloud]に再度ログインし、もう一度やり直してください。

   リストに1つ以上のレポートスイートが見つからない場合は、[ カスタマーケアにお問い合わせください](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. トラッキングサーバーを指定します。

   詳細については、「[Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)」を参照してください。

1. エクスペリエンスの定義。
1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択する必要があります。 アクティビティの目標は、アクティビティの成功を示すコンバージョンアクティビティです。 ベストプラクティスは、必ず何らかの意味で向上が図れる目標を設定してからテストを実行することです。 [!DNL Analytics]指標セレクターで使用できる任意の[!DNL Analytics]指標を選択できます。

   >[!NOTE]
   >
   >[!DNL Analytics] データのみに依存するのではなく、[!DNL Analytics]にカスタム Target ベースの指標を送信できます。 例えば、通常は[!DNL Analytics]によって追跡されないページのクリックを監視できます。 このカスタム指標は、[!DNL Target] サーバーから自動的に[!DNL Analytics]に送信され、[!DNL Analytics]の指標セレクターに「[!DNL Target] コンバージョン」指標として表示されます。 [!DNL Analytics]指標を使用することを選択した場合、[!DNL Target] コンバージョン指標は空です。

   目標を設定した場合でも、テスト結果を評価する際に他の指標を使用することは可能です。 ただし、この目標は、アクティビティにおいて向上させたいものを明確にする役割を果たします。

   訪問者は、目標を達成した後もアクティビティ内にとどまります。 訪問者には引き続きアクティビティコンテンツが表示されますが、新たなアクティビティエントリとしてはカウントされません。

   >[!NOTE]
   >
   >レポートソースとして[!DNL Analytics]を設定した後にアクティビティを設定する場合、レポート用のオーディエンスを設定するオプションはありません。 [!DNL Analytics] セグメントは、[!DNL Target] アクティビティ レポートで利用できます。

1. 「**[!UICONTROL 保存]**」をクリックします。

## A4T アクティビティおよび自動配分アクティビティと自動ターゲットアクティビティ

詳しくは、[A4T での自動割り当ておよび自動ターゲットアクティビティのサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。
