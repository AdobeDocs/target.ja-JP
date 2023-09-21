---
keywords: ターゲット設定;エクスペリエンス;エクスペリエンスの追加;エクスペリエンス追加
description: の使用方法を学ぶ [!UICONTROL Visual Experience Composer] (VEC) [!DNL Adobe Target].
title: エクスペリエンスを [!DNL Target] A/B アクティビティ？
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: 6fa1b428e7955bae976649c42d3eb9b2ddc2c79f
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 43%

---

# エクスペリエンスの追加

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) は、ページ上のエクスペリエンスを追加および編集するための視覚的なインターフェイスを備えています。

エクスペリエンスについて詳しくは、[エクスペリエンス](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)を参照してください。

1. 次から： **[!UICONTROL エクスペリエンス]** VEC のページで、 **[!UICONTROL エクスペリエンスを追加]**.

   ![「エクスペリエンスを追加」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >オーディエンスに対してエクスペリエンスをターゲット設定する場合は、エクスペリエンスを追加する前にオーディエンスを選択する必要があります。オーディエンスを選択するように促すメッセージが表示されます。

1. 変更する要素を選択し、必要な変更を行います。

   ページ上の要素の上にマウスポインターを置くと、その要素がハイライト表示されます。 強調表示された要素は、Experience Composer を使用して変更できます。

   以下を作成した場合、 [!DNL Target] 次を使用してページ上でリクエスト [!DNL Target Classic] ( 以前の [!DNL Test&Target]) [!DNL Target] リクエストは、リクエスト名を示す要素として表示され、他の要素と同様に変更できます。

   エクスペリエンスを変更するために表示されるページの要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >メインページ以外のソースから画像を提供する場合（例えば、`akamai.net` 上でホストされている画像を `example.com` で提供する場合）、フロー図内のページのサムネールには画像が表示されません。

1. エクスペリエンスのデザインが終了したら、「**[!UICONTROL 保存]**」をクリックします。

## エクスペリエンス名を変更

1. 次をクリック： **[!UICONTROL エクスペリエンス名を変更]** 内のエクスペリエンスのアイコン [!UICONTROL A/B テスト] または [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティを使用して、エクスペリエンスに新しい名前を付けます。

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

1. 次をクリック： **[!UICONTROL その他]** 内のエクスペリエンス上のアイコン（縦並びの省略記号） [!UICONTROL A/B テスト] または [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティを選択し、 **[!UICONTROL URL にリダイレクト]**.

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

1. （条件付き） **[!UICONTROL 現在のクエリパラメーターを含める]** 」チェックボックスをオンにします。

## エクスペリエンスの複製

エクスペリエンスを [!UICONTROL A/B テスト] そのため、ゼロからエクスペリエンスを再作成する必要なく、マイナーな変更を加えることができます。

1. 次の日： **[!UICONTROL エクスペリエンス]** ページ（3 ステップのガイドによるワークフローの最初の手順）に表示される縦並びの省略記号アイコン/ **[!UICONTROL 複製]**.

   ![「エクスペリエンスを複製」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## エクスペリエンスを削除する

1. 次の日： **[!UICONTROL エクスペリエンス]** ページ（3 ステップのガイドによるワークフローの最初の手順）に表示される縦並びの省略記号アイコン/ **[!UICONTROL 複製]**.

   ![「エクスペリエンスを削除」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## トレーニングビデオ： [!UICONTROL Visual Experience Composer]

次のビデオでは、 [!UICONTROL Visual Experience Composer] オプション。 (7:17)

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399)
