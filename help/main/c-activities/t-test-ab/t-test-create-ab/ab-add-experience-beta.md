---
keywords: ターゲット設定;エクスペリエンス;エクスペリエンスの追加;エクスペリエンス追加
description: '[!UICONTROL Visual Experience Composer] （VEC）を使用したアクティビティへのエクスペリエンス追加のマスター。'
title: A/B アクティビティにエクスペリエンスを追加するにはどうすればよいですか？
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: 6e9d18b8347d8ae68be699640c4cde91bdec762c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 28%

---

# エクスペリエンスの追加

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）は、ページ上でエクスペリエンスを追加および編集するための視覚的なインターフェイスを提供します。

エクスペリエンスについて詳しくは、[エクスペリエンス](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)を参照してください。

1. VEC の **[!UICONTROL Experiences]** ページで、[!UICONTROL Experiences] ペインの上部にある [!UICONTROL Add] アイコン（![ 追加アイコン ](/help/main/assets/icons/Add.svg)）をクリックします。

   VEC では、新しいアクティビティを作成した後、左側に「エクスペリエンス A」と「エクスペリエンス B」という 2 つのタブが表示されます。エクスペリエンス A はコントロールエクスペリエンスです。 複数のエクスペリエンスをテストに追加できます。

1. 変更する要素を選択し、必要な変更を行います。

   ページ上の要素にポインタを合わせると、その要素がハイライト表示される。 強調表示されている要素は、VEC を使用して変更できます。

   [!DNL Target Classic] （旧称 [!DNL Test&Target]）を使用してページ上で [!DNL Target] リクエストを作成した場合、そのリクエストは、リクエスト名を示す要素として表示され、他の要素と同様に変更できます [!DNL Target]

   エクスペリエンスを変更するために表示されるページの要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >メインページ以外のソースから画像を提供する場合（例えば、`akamai.net` 上でホストされている画像を `example.com` で提供する場合）、フロー図内のページのサムネールには画像が表示されません。

1. エクスペリエンスのデザインが完了したら、「**[!UICONTROL Next]**」をクリックします。

## エクスペリエンス名を変更

1. エクスペリエンスの横にある **[!UICONTROL Rename Experience]** アイコン ![ 名前を変更アイコン ](/help/main/assets/icons/Rename.svg)）をクリックして、エクスペリエンスに新しい名前を付けます。

2. 新しい名前を指定し、「**[!UICONTROL Save]**」をクリックします。

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

1. **[!UICONTROL Experiences]** ウィンドウで、エクスペリエンスの横にある **[!UICONTROL More]** アイコン ![ 詳細アイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックし、「**[!UICONTROL Redirect to URL]**」をクリックします。

   詳しくは、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)を参照してください。

1. エクスペリエンスのリダイレクト先の URL を指定します。

1. （条件付き） **[!UICONTROL Include Current Query Parameters]** チェックボックスをオンにします。

1. **[!UICONTROL Save]** をクリックします。

## エクスペリエンスの複製

[!UICONTROL A/B Test] でエクスペリエンスをコピーすると、エクスペリエンスを再作成せずに小規模な変更を加えることができます。

1. **[!UICONTROL Experiences]** ウィンドウで、エクスペリエンスの横にある **[!UICONTROL More]** アイコン ![ 詳細アイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックし、「**[!UICONTROL Duplicate]**」をクリックします。

## エクスペリエンスを削除する

1. **[!UICONTROL Experiences]** ウィンドウで、エクスペリエンスの横にある **[!UICONTROL More]** のアイコン ![ 詳細アイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックし、「**[!UICONTROL Delete]**」をクリックします。次に、「**[!UICONTROL Delete]**」をクリックしてアクションを確定します。