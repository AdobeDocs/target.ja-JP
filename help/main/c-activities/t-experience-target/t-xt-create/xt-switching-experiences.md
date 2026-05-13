---
keywords: 優先度;エクスペリエンス作成;優先度;エクスペリエンス;オーディエンス;エクスペリエンス;エクスペリエンスの切り替え;visual experience composer
description: プロファイルの進化に伴い、訪問者が [!DNL Adobe Target] [!UICONTROL Experience Targeting] （XT） アクティビティ内のエクスペリエンスを切り替える方法について説明します。
title: 訪問者は[!UICONTROL Experience Targeting] アクティビティでエクスペリエンスを切り替えることができますか？
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
TQID: https://experienceleague.adobe.com/4bBukCristluFUClhewMcSsNMTPjLjXEqM1QyyropKU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 723
ht-degree: 41%

---

# [!UICONTROL Experience Targeting]でのエクスペリエンスの切り替え

[!UICONTROL Experience Targeting]を使用すると、プロファイルの進化に合わせて、訪問者に表示するエクスペリエンスを制御できます。

次のリストは、訪問者のプロファイルが進化するシナリオをいくつか示しており、これらの変化に基づいて異なるコンテンツを表示する場合があります。

| シナリオ | 詳細 |
|--- |--- |
| 地理的な位置 | 訪問者が出張または旅行により、異なる地理的位置から Web サイトまたはモバイルアプリを表示します。 |
| 顧客ステータス | 訪問者は、アカウントを作成したり、商品を購入する前に、見込み客と見なされる可能性があります。 |
| カテゴリ親和性 | [!DNL Target]の[ カテゴリ親和性](/help/main/c-target/c-visitor-profile/category-affinity.md)機能は、訪問者が表示するカテゴリを自動的にキャプチャし、ターゲティング目的でカテゴリに対する訪問者の親和性を計算します。 例えば、特定のテーマに関する記事をweb サイトで複数閲覧した訪問者には、そのテーマに関連するコンテンツが表示されます。 |
| 曜日 | 週末の取り組みとして、訪問者に映画、食事またはその他の娯楽に関するコンテンツを表示できます。 |

[!DNL Target]でこれらの機能を使用するには、[!UICONTROL Experience Targeting] アクティビティを操作する際に、次の情報を理解することが重要です。

* **優先度は、エクスペリエンスの順序（上から下）によって制御されます。** 訪問者が2つ以上のオーディエンスに適格である場合、その訪問者は、より優先度の高いエクスペリエンスからコンテンツを受け取ります。
* **訪問者は、優先度の高いエクスペリエンスのオーディエンスの対象として開始すると、[!UICONTROL Experience Targeting] アクティビティ内のエクスペリエンスを切り替えます。**

  例えば、次のアクティビティの設定で、訪問者が米国から Web サイトにアクセスし、その後、ドイツに旅行して Web サイトに 2 回目の訪問をしました。 最初の訪問中、この訪問者はエクスペリエンス A（米国の訪問者）の資格を得ます。 ドイツから Web サイトを表示した後、この訪問者は、エクスペリエンス B（ドイツの訪問者）に切り替えます。

  ![優先度：米国 > ドイツ](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

* **訪問者は、現在のオーディエンスの選定を中止し、優先度の低いエクスペリエンスの選定を開始した場合、エクスペリエンスを切り替えることもできます。**
* **訪問者が現在のエクスペリエンスの資格を失い、別のエクスペリエンスの資格を得ない場合、デフォルトのコンテンツが表示されます。**

  例えば、次のアクティビティの設定で、訪問者が米国から Web サイトにアクセスし、その後、フランスに旅行して Web サイトに 2 回目の訪問をしました。 最初の訪問中、この訪問者はエクスペリエンス A（米国の訪問者）の資格を得ます。 フランスからweb サイトを表示した後、この訪問者は元のエクスペリエンスに残ります。

  ![優先度：米国 > ドイツ](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

* **「すべての訪問者」をターゲットにしたエクスペリエンスは、[!UICONTROL Experience Targeting] アクティビティの最後のエクスペリエンスとして使用して、他のエクスペリエンスに適格でない訪問者を「獲得」することができます。 「すべての訪問者」をターゲットにしたエクスペリエンスが最後のエクスペリエンスではない場合、このエクスペリエンスよりも低いリストの他のターゲット エクスペリエンスは引き続き評価されます。**

  例えば、次のアクティビティの設定で、訪問者が米国から Web サイトにアクセスし、その後、ドイツに旅行して Web サイトに 2 回目の訪問をしました。 最初の訪問中、この訪問者はエクスペリエンス A（米国の訪問者）の資格を得ます。 ドイツからweb サイトを表示した後、この訪問者はエクスペリエンス A （米国の訪問者）に残ります。

  ![優先度：米国 > すべての訪問者](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-refresh.png)

  これが望ましくない場合、次の例に示すように、ターゲットオーディエンスの正反対として明示的に定義された新しいオーディエンスを作成できます。

  ![優先度：米国 > 米国以外](/help/main/c-activities/t-experience-target/t-xt-create/assets/not-us.png)

* **単一のエクスペリエンス [!UICONTROL Experience Targeting]のアクティビティを使用すると、訪問者は、そのエクスペリエンスに参加するオーディエンスの資格を失っても、エクスペリエンスに残ります。**

  これが望ましくない場合、正反対のオーディエンスをターゲットにした別のエクスペリエンスを作成できます（例えば、「United States」（米国）に対して「Not United States」（米国以外））。

  別のオプションとして、次に示すように、100%のトラフィック配分を使用して、目的のオーディエンスをターゲットとする[!UICONTROL A/B Test] アクティビティを作成できます。

  ![優先度 1 エクスペリエンス](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-refresh.png)

* **エクスペリエンスの優先順位は、[!DNL Target] UIに表示される順序（トップダウン）によって定義されます。**

  これは、訪問者が複数のオーディエンスの資格を得る可能性があるシナリオで覚えておくべき重要な点です。 例えば、2つのエクスペリエンスがある場合、1つは「米国」をターゲットとしたものと1つは「ニューヨーク」をターゲットとしたもので、ニューヨークにある訪問者は両方のオーディエンスに適格です。 したがって、[!DNL Target] UIの「United States」エクスペリエンスの前に、「New York」エクスペリエンスが定義されていることを確認する必要があります。 この方法では、次の例に示すように、よりターゲットを絞った「ニューヨーク」エクスペリエンスの優先度が高くなります。

  ![優先度：ニューヨーク > 米国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-refresh.png)
