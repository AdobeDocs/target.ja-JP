---
keywords: オーディエンス、オーディエンスルール、結合、オーディエンス、exclusion、除外の追加、exclude、結合オーディエンス、アドホックオーディエンス、アドホックオーディエンス
description: 複数のオーディエンス (Adobe Experience Cloudのオーディエンス、 [!DNL Target] オーディエンス ) をオンフライで作成し、アドホックオーディエンスを作成する必要があります。
title: 複数のオーディエンスを組み合わせて新しいオーディエンスを作成することはできますか？
feature: Audiences
exl-id: 1d9bff9c-f63b-4e15-9809-71b046158b71
source-git-commit: 1383088bb2f6be0432e6f140400d8723048c8530
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 65%

---

# 複数のオーディエンスの結合

複数のオーディエンスの結合 ( [!DNL Adobe Experience Cloud], [!DNL Adobe Experience Platform]、および [!DNL Target] オーディエンス ) をオンフライで作成し、アドホックオーディエンスを作成する必要があります。 また、除外ルールを作成して、ルールからオーディエンスを除外できます。

>[!NOTE]
>
>この [!DNL Adobe Experience Platform] ソースは、すべての [!DNL Target] のお客様が [Adobe Experience Platform Web SDK](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=en){target=_blank}. 次の場所から利用可能なオーディエンス： [!DNL Adobe Experience Platform] は、このトピックで説明するように、そのまま使用することも、既存のオーディエンスと組み合わせて使用することもできます。
>
>詳しくは、 [Adobe Experience Platformのオーディエンスを使用](/help/main/c-target/c-audiences/audiences.md#aep).

「新規訪問者」オーディエンスと「Chrome ユーザー」オーディエンスがあるとします。特定のアクティビティについて、これらの既存のオーディエンスを結合して、Chrome ブラウザーを使用する新規訪問者をターゲティングします。第 3 オーディエンスを作成して[!UICONTROL オーディエンス]ライブラリに保存する代わりに、これらの 2 つのオーディエンスをアクティビティの作成時または既存のアクティビティの編集時に結合することができます。

もう 1 つの例として、すべてのロイヤルティ顧客をターゲットに設定できます。 例えば、特定の [!DNL Audience Manager] ロイヤリティステータスのオーディエンスと [!DNL Target] オーディエンスは、現在のセッション中にロイヤルティプログラムに登録した人で構成されます。 これら 2 つのオーディエンスを組み合わせる方が、3 つ目の永続的なオーディエンスを作成するよりも簡単です。

AND および OR 演算子を使用して、最大 20 個のオーディエンスを組み合わせることができます。

[!DNL Target] UI 全体の様々な場所で、結合オーディエンスの作成や利用が可能です。

## アクティビティの作成時に結合オーディエンスを作成 {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

3 ステップのガイドによるワークフローを実行する際に、アクティビティの [!UICONTROL Target] ページで結合オーディエンスをアドホックに作成できます。

1. を作成する際に、 [アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)、 **[!UICONTROL ターゲット設定]** ページで、縦並びの省略記号をクリックし、 **[!UICONTROL オーディエンスを置換]**.

   ![ステップの結果](assets/edit_audience.png)

1. **[!UICONTROL オーディエンスを選択]**&#x200B;ページで、結合オーディエンスの構成要素として使用するオーディエンスの横にあるチェックボックスをオンにします。

   以下を使用： [!UICONTROL オーディエンスを検索] 」ボックスを使用して、目的のオーディエンスの検索を絞り込みます。

   ![ステップの結果](assets/combine_multiple_audiences1.png)

1. クリック **[!UICONTROL 複数のオーディエンスを結合]** をクリックします。

   ![ステップの結果](assets/combine_multiple_audiences2.png)

1. （条件付き）必要に応じて新しい結合オーディエンスを編集します。

   [!UICONTROL オーディエンスを編集]ダイアログボックスでは、追加するオーディエンスの構成要素を左側から新しい結合オーディエンスにドラッグ＆ドロップできます。また、除外ルールを追加したり、オーディエンスを除外したりすることもできます。

   1. ドラッグ&amp;ドロップ機能を使用して、既存のセクション内にオーディエンスをレベル 2 の構成要素として追加します。

      例えば、前の例で、Safari ユーザーを結合オーディエンスに含める場合を考えてみます。以下の例のように、「Safari ブラウザー」オーディエンスを検索して、右側の「Firefox ブラウザー」ボックスにドラッグします。

      ![combine_multiple_audiences3 の画像](assets/combine_multiple_audiences3.png)

      2 つのブラウザータイプオーディエンスの間の演算子は「AND」になっています。を選択します。 [!UICONTROL および] 」ドロップダウンリストから「OR」に変更して、Firefox または Safari を使用する新規訪問者の新しい結合オーディエンスを作成します。 すべての潜在的なオーディエンスメンバーを除外するルールを作成しないように注意してください。例えば、Firefox と Safari を同時に使用してページに訪問することはできません。

      >[!NOTE]
      >
      >演算子（ANDまたはOR）は、オーディエンスの結合と同じでなければなりません。演算子を組み合わせることはできません。

   1. ルールに除外を追加するには、 **[!UICONTROL 除外]**.

      ![combine_multiple_audiences3a 画像](assets/combine_multiple_audiences3a.png)

      オーディエンスをドラッグ&amp;ドロップします。

      例えば、新規訪問者から米国の訪問者を除外するには、Market を次のようにドラッグします。米国のオーディエンスを追加しました。

      この結合オーディエンスには、Safari または Firefox を使用するすべてのサイト訪問者が含まれます（San Francisco からの訪問者を除く）。

   1. ルールからオーディエンスを除外するには、**[!UICONTROL 除外]**／**[!UICONTROL このオーディエンスを除外]**&#x200B;をクリックします。

      例えば、Firefox を使用する訪問者を除く、すべての新規サイト訪問者を含む結合オーディエンスを作成できます。Firefox を使用する訪問者の除外は、複数のブラウザー（Safari、Chrome、Internet Explorer）を明示的に含み、Firefox を含まない結合オーディエンスを作成するよりも簡単で、すばやくおこなえます。

1. 結合オーディエンスのわかりやすい名前を入力し、 **[!UICONTROL 完了]**.

## 指標のターゲティングで使用する結合オーディエンスを作成 {#section_A42E795AFCBD4575809C5942039910F0}

アクティビティの[!UICONTROL 目標と設定]ページで、指標のターゲティングで使用する結合オーディエンスをアドホックに作成できます。例えば、結合オーディエンスによるコンバージョンに基づいてターゲティングを作成するには、以下の手順に従います。

1. [アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を編集または作成中に、**[!UICONTROL 目標と設定]** ページでで、成功指標の&#x200B;**[!UICONTROL コンバージョン]**&#x200B;を選択し、アクションとして「**[!UICONTROL Mbox を表示]**」を選択します。
1. 目的の mbox を「**[!UICONTROL mbox を検索]**」フィールドで選択します。

   ![combine_multiple_audiences4 画像](assets/combine_multiple_audiences4.png)

1. 歯車アイコンをクリックし、「**[!UICONTROL オーディエンスターゲティングを追加]**」をクリックします。
1. 「**[!UICONTROL オーディエンス／ターゲット条件を追加]**」リンクをクリックして、[!UICONTROL オーディエンスを選択]ダイアログボックスを表示します。

   ![combine_multiple_audiences5 画像](assets/combine_multiple_audiences5.png)

1. 「アクティビティの作成時に結合オーディエンスを作成」の[手順 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) を実行して結合オーディエンスを作成します。

## レポートで使用する結合オーディエンスを作成 {#section_4682D342EFBB43C38E54B99B3A1E14CD}

アクティビティの[!UICONTROL 目標と設定]ページで、レポートで使用する結合オーディエンスをアドホックに作成できます。

1. While editing or creating an[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)の編集時または作成時に、**[!UICONTROL 目標と設定]**&#x200B;ページで、「**[!UICONTROL レポート対象のオーディエンス]**」の下の[!UICONTROL オーディエンスを追加]アイコンをクリックして、[!UICONTROL オーディエンスを選択]ページを表示します。

   ![combine_multiple_audiences6 の画像](assets/combine_multiple_audiences6.png)

1. 「アクティビティの作成時に結合オーディエンスを作成」の[手順 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) を実行して結合オーディエンスを作成します。

## アクティビティの編集時に結合オーディエンスを作成 {#section_364A12CE96E04B61B7C18113AA586C2C}

既存のアクティビティの編集時に結合オーディエンスをアドホックに作成することができます。

1. [!UICONTROL アクティビティ]ページで、目的のアクティビティの上にマウスポインターを置いて、**[!UICONTROL 編集]**&#x200B;アイコンをクリックします。

   または

   目的のアクティビティをクリックして開き、「**[!UICONTROL アクティビティ を編集]**」をクリックします。

1. 次をクリック： **[!UICONTROL 設定]** > **[!UICONTROL オーディエンス]** > **[!UICONTROL 複数のオーディエンス]**.

   ![設定／オーディエンス／複数のオーディエンス](assets/combine_multiple_audiences7.png)

1. アクティビティの現在のオーディエンスの横にある、その他のオプションアイコン（縦並びの省略記号）をクリックし、「**[!UICONTROL オーディエンスを変更]**」をクリックします。

   ![オーディエンスを変更](assets/combine_multiple_audiences8.png)

1. 「アクティビティの作成時に結合オーディエンスを作成」の[手順 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) を実行して結合オーディエンスを作成します。
