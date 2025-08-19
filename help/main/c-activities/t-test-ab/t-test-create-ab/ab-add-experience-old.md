---
keywords: ターゲット設定;エクスペリエンス;エクスペリエンスの追加;エクスペリエンス追加
description: '[!UICONTROL Visual Experience Composer] で  [!DNL Adobe Target] （VEC）を使用する方法を説明します。'
title: A [!DNL Target] A/B アクティビティにエクスペリエンスを追加するにはどうすればよいですか？
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 43%

---

# エクスペリエンスの追加

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）は、ページ上でエクスペリエンスを追加および編集するための視覚的なインターフェイスを提供します。

エクスペリエンスについて詳しくは、[エクスペリエンス](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)を参照してください。

1. VEC の **[!UICONTROL Experiences]** ページで、「**[!UICONTROL Add Experience]**」をクリックします。

   ![「エクスペリエンスを追加」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >オーディエンスに対してエクスペリエンスをターゲット設定する場合は、エクスペリエンスを追加する前にオーディエンスを選択する必要があります。オーディエンスを選択するように促すメッセージが表示されます。

1. 変更する要素を選択し、必要な変更を行います。

   ページ上の要素にポインタを合わせると、その要素がハイライト表示される。 強調表示されている要素は、VEC を使用して変更できます。

   [!DNL Target] （旧称 [!DNL Target Classic]）を使用してページ上で [!DNL Test&Target] リクエストを作成した場合、そのリクエストは、リクエスト名を示す要素として表示され、他の要素と同様に変更できます [!DNL Target]

   エクスペリエンスを変更するために表示されるページの要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >メインページ以外のソースから画像を提供する場合（例えば、`akamai.net` 上でホストされている画像を `example.com` で提供する場合）、フロー図内のページのサムネールには画像が表示されません。

1. エクスペリエンスのデザインが完了したら、「**[!UICONTROL Save]**」をクリックします。

## エクスペリエンス名を変更

1. **[!UICONTROL Rename Experience]** または [!UICONTROL A/B Test] （XT）アクティビティのエクスペリエンスで [!UICONTROL Experience Targeting] アイコンをクリックして、エクスペリエンスに新しい名前を付けます。

   ![エクスペリエンス名を変更](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/rename-experience.png)

2. 新しい名前を指定します。

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

1. **[!UICONTROL More]** または [!UICONTROL A/B Test] （XT）アクティビティ内のエクスペリエンスで [!UICONTROL Experience Targeting] アイコン（垂直省略記号）アイコンをクリックし、「**[!UICONTROL Redirect to URL]**」をクリックします。

   詳しくは、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)を参照してください。

   **注意**：エクスペリエンスに名前を付けたり、名前を変更したりする場合、以下の文字は使用できません。

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

1. エクスペリエンスのリダイレクト先の URL を指定します。

1. （条件付き） **[!UICONTROL Include Current Query Parameters]** チェックボックスをオンにします。

## エクスペリエンスの複製

[!UICONTROL A/B Test] でエクスペリエンスをコピーすると、エクスペリエンスを最初から再作成しなくても、小規模な変更を加えることができます。

1. **[!UICONTROL Experiences]** ページ（3 ステップのガイドによるワークフローの最初のステップ）で、縦並びの省略記号アイコン/**[!UICONTROL Duplicate]** をクリックします。

   ![「エクスペリエンスを複製」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## エクスペリエンスを削除する

1. **[!UICONTROL Experiences]** ページ（3 ステップのガイドによるワークフローの最初のステップ）で、縦並びの省略記号アイコン/**[!UICONTROL Duplicate]** をクリックします。

   ![「エクスペリエンスを削除」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## トレーニングビデオ：[!UICONTROL Visual Experience Composer] の使用

次のビデオでは、[!UICONTROL Visual Experience Composer] のオプションの使用方法について説明しています。 （7:17）

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/29948?captions=jpn)
