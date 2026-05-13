---
keywords: ターゲティング;エクスペリエンス;エクスペリエンスの追加;エクスペリエンス追加
description: アクティビティにエクスペリエンスを追加するには、[!UICONTROL Visual Experience Composer] （VEC）を使用します。
title: A/B アクティビティにエクスペリエンスを追加するにはどうすればよいですか？
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
TQID: https://experienceleague.adobe.com/7qEiUXkfMbPmtB2eMio0LztOYM3naHxG-WRQZOyMmlU
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 387
ht-degree: 33%

---

# エクスペリエンスの追加

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）は、ページ上のエクスペリエンスを追加および編集するための視覚的なインターフェイスを提供します。

エクスペリエンスについて詳しくは、[エクスペリエンス](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)を参照してください。

1. VECの&#x200B;**[!UICONTROL Experiences]** ページで、[!UICONTROL Experiences] ペインの上部にある[!UICONTROL Add] アイコン （![追加アイコン &#x200B;](/help/main/assets/icons/Add.svg)）をクリックします。

   VECは、新しいアクティビティを作成した後、左側にエクスペリエンス Aとエクスペリエンス Bの2つのタブを表示します。エクスペリエンス Aはコントロール エクスペリエンスです。 テストには複数のエクスペリエンスを追加できます。

1. 変更する要素を選択し、必要な変更を加えます。

   ページ上の要素にカーソルを合わせると、その要素がハイライト表示されます。 強調表示された要素は、Experience Composer を使用して変更できます。

   [!DNL Target Classic] （旧称[!DNL Test&Target]）を使用してページ上で[!DNL Target] リクエストを作成した場合、その[!DNL Target] リクエストはリクエスト名を示す要素として表示され、他の要素と同様に変更できます。

   エクスペリエンスを変更するために表示されるページの要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >メインページ以外のソースから画像を提供する場合（例えば、`akamai.net` 上でホストされている画像を `example.com` で提供する場合）、フロー図内のページのサムネールには画像が表示されません。

1. エクスペリエンスのデザインが完了したら、**[!UICONTROL Next]**&#x200B;をクリックします。

## エクスペリエンス名を変更

1. エクスペリエンスの横にある&#x200B;**[!UICONTROL Rename Experience]** アイコン（![名前を変更](/help/main/assets/icons/Rename.svg)）をクリックして、エクスペリエンスに新しい名前を付けます。

2. 新しい名前を指定し、**[!UICONTROL Save]**&#x200B;をクリックします。

   エクスペリエンスに名前を付けたり、名前を変更したりする場合、次の文字は使用できません。

   | 文字 | 説明 |
   |--- |--- |
   | / | フォワードスラッシュ |
   | ? | 疑問符 |
   | # | 番号記号 |
   | : | コロン |
   | = | イコール |
   | + | プラス |
   | - | マイナス |
   | @ | アットマーク |

## URL にリダイレクト

1. **[!UICONTROL Experiences]** ペインで、エクスペリエンスの横にある&#x200B;**[!UICONTROL More]** アイコン （![詳細アイコン &#x200B;](/help/main/assets/icons/MoreSmall.svg)）をクリックし、**[!UICONTROL Redirect to URL]**&#x200B;をクリックします。

   詳しくは、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)を参照してください。

1. エクスペリエンスをリダイレクトするURLを指定します。

1. （条件付き）「**[!UICONTROL Include Current Query Parameters]**」チェックボックスをオンにします。

1. **[!UICONTROL Save]** をクリックします。

## エクスペリエンスの複製

[!UICONTROL A/B Test]のエクスペリエンスをコピーして、エクスペリエンスを再作成することなく、エクスペリエンスにマイナーな変更を加えることができます。

1. **[!UICONTROL Experiences]** ペインで、エクスペリエンスの横にある&#x200B;**[!UICONTROL More]** アイコン （![詳細アイコン &#x200B;](/help/main/assets/icons/MoreSmall.svg)）をクリックし、**[!UICONTROL Duplicate]**&#x200B;をクリックします。

## エクスペリエンスを削除する

1. **[!UICONTROL Experiences]** ペインで、エクスペリエンスの横にある&#x200B;**[!UICONTROL More]** アイコン （![詳細アイコン &#x200B;](/help/main/assets/icons/MoreSmall.svg)）をクリックし、**[!UICONTROL Delete]**&#x200B;をクリックしてから、**[!UICONTROL Delete]**&#x200B;をクリックしてアクションを確認します。
