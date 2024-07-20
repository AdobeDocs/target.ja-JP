---
keywords: a4t;A4T;Target のレポートソースとしての Analytics
description: ' [!DNL Target]  Adobe Analyticsをレポートソースとして使用するアクティビティをAdobe（A4T）で設定する方法について説明します。'
title: A4T を使用するアクティビティの作成方法
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 30%

---

# Analytics をレポートソースとして使用するアクティビティの作成

[!DNL Adobe Analytics] をレポートソース（A4T）として使用する [!DNL Adobe Target] うに、のアクティビティを設定できます。

[!DNL Analytics] をレポートソースとして使用するアクティビティを設定する前に、訪問者あたりの売上高（RPV）の向上や買い物かごでのクリック数の増加など、アクティビティの目標を確立します。 アクティビティの最終的な成功指標を選択します。[!DNL Analytics] の任意の時点で追加の指標を選択できますが、このテストで影響を受ける特定の指標を指定する必要があります。

## アクティビティの作成

[!DNL Analytics] をレポートソースとして使用する [!DNL Target] アクティビティの作成は、通常の [!DNL Target] アクティビティの設定と似ていますが、いくつかの重要な違いがあります。 例えば、[!DNL Analytics] で使用可能なすべてのセグメントがレポートの表示時に適用できるので、アクティビティの作成時にレポート用のセグメントを選択することはできません。

1. **[!UICONTROL Create Activity]** をクリックします。

   >[!NOTE]
   >
   >[!DNL Analytics] がレポートソースとして使用されている場合、アクティビティ名に「%」文字を含めることはできません。
   >
   >A4T レポートを使用している、別の [ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) からの 2 つのアクティビティに同じアクティビティ名を使用しないでください。

1. アクティビティのタイプを選択して、アクティビティの設定を開始します。

   [!UICONTROL Auto-Allocate] アクティビティまたは [!UICONTROL Auto-Target] アクティビティを作成する場合、詳細は、自動配分と自動ターゲットアクティビティに対する [A4T のサポート ](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) を参照してください。

1. アクティビティ作成フローの **[!UICONTROL Settings]** 部に移動したら、「**[!UICONTROL Adobe Analytics]**」を選択して会社を指定します。
1. レポートスイートを選択します。

   [!DNL Analytics] で使用可能な任意のレポートスイートを選択できます。 レポートスイートでは、収集したデータを使用できる場所が定義されます。 仮想レポートスイートは、レポートスイートリストには含まれません。

   レポートスイートを選択する際に、次の 2 つのエラーが発生する可能性があります。

   * レポートスイートが利用できないが、アカウントが正しく設定されているというエラーが表示されます。

     [!DNL Analytics] 会社を確認してください。 [!DNL Adobe Experience Cloud] アカウントが複数の [!DNL Analytics] 会社に結び付けられている場合は、[!DNL Target] からログアウトして、適切な会社で [!DNL Analytics] にログインします。 次に [!DNL Target] に戻り、レポートスイートが読み込まれます。

   * 対象のレポートスイートが表示されません。

     [!DNL Target] に接続するようにプロビジョニングされているレポートスイートのみを選択できます。 目的のレポートスイートが表示されない場合は、まずログアウトして [!DNL Adobe Experience Cloud] にログインし直し、もう一度試してください。

   それでもリストに 1 つ以上のレポートスイートが表示されない場合は、[ カスタマーケアへのお問い合わせ ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) してください。

1. トラッキングサーバーを指定します。

   詳細については、「[Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)」を参照してください。

1. エクスペリエンスを定義します。
1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択する必要があります。 アクティビティの目標は、アクティビティの成功を示すコンバージョンアクティビティです。ベストプラクティスは、必ず何らかの意味で向上が図れる目標を設定してからテストを実行することです。[!DNL Analytics] 指標セレクターで使用可能な任意の [!DNL Analytics] 指標を選択できます。

   >[!NOTE]
   >
   >[!DNL Analytics] のデータのみに依存するのではなく、カスタム Target ベースの指標を [!DNL Analytics] に送信できます。 例えば、[!DNL Analytics] で通常は追跡されないページのクリックを監視できます。 このカスタム指標は、[!DNL Target] サーバーから自動的に [!DNL Analytics] に送信され、[!DNL Analytics] の指標セレクターの「[!DNL Target] コンバージョン」指標として表示されます。 [!DNL Analytics] の指標を使用することを選択した場合、[!DNL Target] コンバージョン指標は空になります。

   目標を設定した場合でも、テスト結果を評価する際に他の指標を使用することは可能です。ただし、この目標は、アクティビティにおいて向上させたいものを明確にする役割を果たします。

   訪問者は、目標を達成した後もアクティビティ内にとどまります。訪問者には引き続きアクティビティコンテンツが表示されますが、新たなアクティビティエントリとしてはカウントされません。

   >[!NOTE]
   >
   >[!DNL Analytics] をレポートソースとして設定した後にアクティビティを設定する場合、レポート用のオーディエンスを設定するオプションはありません。 セグメント [!DNL Analytics]、[!DNL Target] のアクティビティレポートで使用できます。

1. **[!UICONTROL Save]** をクリックします。

## A4T アクティビティ、自動配分アクティビティ、自動ターゲットアクティビティ

詳しくは、[A4T での自動配分および自動ターゲットアクティビティのサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。
