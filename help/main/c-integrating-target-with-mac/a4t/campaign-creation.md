---
keywords: a4t;A4T;Target のレポートソースとしての Analytics
description: Adobeでアクティビティを設定する方法を説明します [!DNL Target] Adobe Analyticsをレポートソースとして使用する (A4T)
title: A4T を使用するアクティビティを作成する方法を教えてください。
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 30%

---

# Analytics をレポートソースとして使用するアクティビティの作成

アクティビティは [!DNL Adobe Target] 使用する [!DNL Adobe Analytics] を使用します (A4T)。

を使用するアクティビティを設定する前に [!DNL Analytics] レポートソースとして、訪問者あたりの売上高 (RPV) の向上や買い物かごのクリック数の増加など、アクティビティの目標を設定します。 アクティビティの最終的な成功指標を選択します。ただし、 [!DNL Analytics]に値を入力しない場合でも、このテストの対象となる特定の指標を指定する必要があります。

## アクティビティの作成

の作成 [!DNL Target] を使用するアクティビティ [!DNL Analytics] レポートソースは、通常の [!DNL Target] アクティビティに含まれる変数です。 例えば、で使用可能なすべてのセグメントがあるので、アクティビティの作成時にレポート用のセグメントを選択することはできません。 [!DNL Analytics] を適用できます。

1. 「**[!UICONTROL アクティビティを作成]**」をクリックします。

   >[!NOTE]
   >
   >次の場合、アクティビティ名に「%」を含めることはできません： [!DNL Analytics] は、レポートソースとして使用されます。
   >
   >別々の [workspaces](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) A4T レポートを使用している

1. アクティビティのタイプを選択して、アクティビティの設定を開始します。

   を作成する場合、 [!UICONTROL 自動配分] または [!UICONTROL 自動ターゲット] アクティビティについては、 [自動配分と自動ターゲットアクティビティに対する A4T のサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) を参照してください。

1. 次に、 **[!UICONTROL 設定]** アクティビティ作成フローの一部で、「 」を選択します。 **[!UICONTROL Adobe Analytics]** 会社を指定します。
1. レポートスイートを選択します。

   任意のレポートスイートを選択できます。 [!DNL Analytics]. レポートスイートでは、収集したデータを使用できる場所を定義します。 仮想レポートスイートはレポートスイートリストに含まれていません。

   レポートスイートを選択する際に、次の 2 つのエラーが発生する可能性があります。

   * レポートスイートが利用できないが、アカウントが正しく設定されているというエラーが表示されます。

     以下を確認します。 [!DNL Analytics] 会社名。 次の場合、 [!DNL Adobe Experience Cloud] アカウントが複数の [!DNL Analytics] 会社、ログアウト [!DNL Target]をクリックし、にログインします。 [!DNL Analytics] 適切な会社の下で その後、に戻ります。 [!DNL Target]、およびレポートスイートが読み込まれます。

   * 対象のレポートスイートが表示されません。

     接続するようにプロビジョニングされたレポートスイートのみ [!DNL Target] は選択可能です。 対象のレポートスイートが表示されない場合は、まず、ログアウトしてから、 [!DNL Adobe Experience Cloud] 再度お試しください。

   それでも 1 つ以上のレポートスイートがリストに表示されない場合は、 [カスタマーケアにお問い合わせください](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. トラッキングサーバーを指定します。

   詳細については、「[Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)」を参照してください。

1. エクスペリエンスを定義します。
1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択する必要があります。 アクティビティの目標は、アクティビティの成功を示すコンバージョンアクティビティです。ベストプラクティスは、必ず何らかの意味で向上が図れる目標を設定してからテストを実行することです。任意の [!DNL Analytics] 指標 [!DNL Analytics] 指標セレクターを使用します。

   >[!NOTE]
   >
   >カスタムの Target ベースの指標をに送信できます。 [!DNL Analytics] 単に頼るのではなく [!DNL Analytics] データ。 例えば、ページのクリックを監視できますが、通常は [!DNL Analytics]. このカスタム指標はに送信されます。 [!DNL Analytics] 自動的に [!DNL Target] サーバーで、「[!DNL Target] 指標セレクターの「コンバージョン」指標 ( [!DNL Analytics]. The [!DNL Target] コンバージョン指標は、 [!DNL Analytics] 指標。

   目標を設定した場合でも、テスト結果を評価する際に他の指標を使用することは可能です。ただし、この目標は、アクティビティにおいて向上させたいものを明確にする役割を果たします。

   訪問者は、目標を達成した後もアクティビティ内にとどまります。訪問者には引き続きアクティビティコンテンツが表示されますが、新たなアクティビティエントリとしてはカウントされません。

   >[!NOTE]
   >
   >設定後にアクティビティを設定する場合 [!DNL Analytics] レポートソースとして、レポート用のオーディエンスを設定するオプションはありません。 [!DNL Analytics] セグメントは、 [!DNL Target] アクティビティレポート。

1. 「**[!UICONTROL 保存]**」をクリックします。

## A4T と自動配分と自動ターゲットアクティビティ

詳しくは、[A4T での自動配分および自動ターゲットアクティビティのサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。
