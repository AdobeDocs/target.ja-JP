---
description: Automated Personalization アクティビティで、特定のオーディエンスに対してオファーをターゲット設定できます。
seo-description: Automated Personalization アクティビティで、特定のオーディエンスに対してオファーをターゲット設定できます。
seo-title: Target の Automated Personalization オファー
solution: Target,Analytics
title: Target の Automated Personalization オファー
title-outputclass: Premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: Premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Target の Automated Personalization オファー{#target-automated-personalization-offers}

自動パーソナライゼーション（AP）アクティビティでは、特定のオーディエンスにオファーをターゲット設定できます。

この機能を使用すると、特定の訪問者が閲覧できるオファーの数を減らすことができます。例えば、3つのオファーを持つAPアクティビティを考えてみましょう。オファー1には、オーディエンスAにさらされるターゲットルールがあります。2人の訪問者がこのAPアクティビティを閲覧しました。

|  | 訪問者 1 | 訪問者 2 |
|--- |--- |--- |
| オーディエンス資格認定 | オーディエンス A | オーディエンス B |
| オファー 1 Target パーソナライゼーションモデルスコア | 90 | 90 |
| オファー 2 Target パーソナライゼーションモデルスコア | 50 | 70 |
| オファー 3 Target パーソナライゼーションモデルスコア | 80 | 60 |

このシナリオでは、訪問者 1は（オーディエンス A に属すると認定されているので）、オファー 1 を閲覧します。それがこの訪問者の最高スコアになります。一方、訪問者 2 は（オーディエンス A に属していないので）、オファー 1 の場合に最高スコアになるとしても、オファー 2 を閲覧します。この例は、ビジネスニーズに応えるにはターゲットルールを慎重に使用する必要がある理由を示しています。これらのルールを追加すると、Target のパーソナライゼーションモデルの有効性が弱まるおそれがあります。

## ターゲットルールの設定

1. Create an [Automated Personalization activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) containing the offers you want to target.
1. After setting up the offers for the activity in the Visual Experience Composer, click **[!UICONTROL Manage Content]**.

   ![コンテンツの管理](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   コンテンツを管理ダイアログボックスが開きます。

1. 「オファー」タブをクリックします。

   ![オファーページ](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 目的のオファーを選択し、そのオファーを表示する対象となるオーディエンスを選択します。

   To set up targeting for a single offer, hover over the desired offer, then click the **[!UICONTORL Targeting]** icon.

   To set up targeting for multiple offers, select the checkboxes for the desired offers, then click the **[!UICONTROL Targeting] icon that displays at the top right of the list.

1. In the [!UICONTROL Choose Audience] dialog box, select the desired audience(s) for the offer(s), then click **[!UICONTROL Done]** to return to the [!UICONTROL Manage Content] dialog box.

   >[!NOTE]
   >
   >既存のオーディエンスの選択に加え、新規のオーディエンスを作成する代わりに、複数のオーディエンスを結合してアドホックな結合オーディエンスを作成することができます。詳しくは、[複数のオーディエンスの結合](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)を参照してください。

1. 「 **[!UICONTROL 完了]**」をクリックします。

>[!NOTE]
>
>場所は 50 カ所を設定でき、場所ごとに最大 250 個のオファーを設定できます。
