---
keywords: ターゲティング;エクスペリエンス;エクスペリエンスの追加;エクスペリエンス追加
description: ' [!DNL Adobe Target]で[!UICONTROL Visual Experience Composer] （VEC）を使用する方法について説明します。'
title: A [!DNL Target] A/B アクティビティにエクスペリエンスを追加するにはどうすればよいですか？
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 41%

---

# エクスペリエンスの追加

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）は、ページ上のエクスペリエンスを追加および編集するための視覚的なインターフェイスを提供します。

エクスペリエンスについて詳しくは、[エクスペリエンス](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)を参照してください。

1. VECの&#x200B;**[!UICONTROL エクスペリエンス]** ページで、**[!UICONTROL エクスペリエンスを追加]**&#x200B;をクリックします。

   ![「エクスペリエンスを追加」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/add-experience.png)

   >[!NOTE]
   >
   >オーディエンスに対してエクスペリエンスをターゲティングする場合は、エクスペリエンスを追加する前にオーディエンスを選択する必要があります。 オーディエンスを選択するように促すメッセージが表示されます。

1. 変更する要素を選択し、必要な変更を加えます。

   ページ上の要素にカーソルを合わせると、その要素がハイライト表示されます。 強調表示された要素は、Experience Composer を使用して変更できます。

   [!DNL Target Classic] （旧称[!DNL Test&Target]）を使用してページ上で[!DNL Target] リクエストを作成した場合、その[!DNL Target] リクエストはリクエスト名を示す要素として表示され、他の要素と同様に変更できます。

   エクスペリエンスを変更するために表示されるページの要素で実行可能なアクションのリストについては、[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   >[!NOTE]
   >
   >メインページ以外のソースから画像を提供する場合（例えば、`akamai.net` 上でホストされている画像を `example.com` で提供する場合）、フロー図内のページのサムネールには画像が表示されません。

1. エクスペリエンスのデザインが完了したら、**[!UICONTROL 保存]**&#x200B;をクリックします。

## エクスペリエンス名を変更

1. [!UICONTROL A/B テスト &#x200B;]または[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）アクティビティのエクスペリエンスの&#x200B;**[!UICONTROL エクスペリエンス名を変更]** アイコンをクリックして、エクスペリエンスに新しい名前を付けます。

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

1. [!UICONTROL A/B テスト &#x200B;]または[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）アクティビティで、エクスペリエンスの&#x200B;**[!UICONTROL 詳細]** アイコン（垂直省略記号）アイコンをクリックし、**[!UICONTROL URLにリダイレクト]**&#x200B;をクリックします。

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

1. エクスペリエンスをリダイレクトするURLを指定します。

1. （条件付き）現在のクエリパラメーターを含める&#x200B;**[!UICONTROL チェックボックスをオンにします。]**

## エクスペリエンスの複製

[!UICONTROL A/B テスト &#x200B;]でエクスペリエンスをコピーできるので、エクスペリエンスをゼロから再作成することなく、エクスペリエンスにマイナーな変更を加えることができます。

1. **[!UICONTROL エクスペリエンス]** ページ（3段階のガイド付きワークフローの最初のステップ）で、垂直省略記号アイコン > **[!UICONTROL 重複]**&#x200B;をクリックします。

   ![「エクスペリエンスを複製」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/duplicate-experience.png)

## エクスペリエンスを削除する

1. **[!UICONTROL エクスペリエンス]** ページ（3段階のガイド付きワークフローの最初のステップ）で、垂直省略記号アイコン > **[!UICONTROL 重複]**&#x200B;をクリックします。

   ![「エクスペリエンスを削除」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/delete-experience.png)

## トレーニングビデオ：[!UICONTROL Visual Experience Composer]の使用

次のビデオでは、[!UICONTROL Visual Experience Composer] オプションの使用に関する情報を示しています。 (7:17)

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399)
