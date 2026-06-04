---
keywords: レコメンデーション;設定;名前;目的;優先度;期間;レポート設定;他のメタデータ
description: Adobe TargetでRecommendations アクティビティの説明と制御に使用する設定を行う方法について説明します。
title: Recommendations アクティビティの設定を行う方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
TQID: https://experienceleague.adobe.com/pfMAvl6MmLCtH3PZfOR4Ve-WFIc3e2iN2Bh-cIzjeC0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 608
ht-degree: 47%

---

# レコメンデーションアクティビティの設定

[!DNL Adobe Target]の[!UICONTROL Recommendations] アクティビティの説明と制御に使用できる設定に関する情報。

次の節では、[!UICONTROL Recommendations] アクティビティで使用できる設定について説明します。

## 名前

その他のアクション アイコン（![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallListVert.svg)）をクリックし、**[!UICONTROL 名前変更]**&#x200B;をクリックして、ユーザーとチームがアクティビティを識別するのに役立つわかりやすい名前を指定します。

次の文字はアクティビティ名として入力できません。

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

[!UICONTROL Recommendations Classic] の別のアクティビティとして既に存在する [!UICONTROL Recommendation] アクティビティ名を指定すると、新しいアクティビティは、新しい名前で再同期されます。 新しい名前は、一意なものにするために、元の名前にタイムスタンプが追加されたものになります。 この新しい名前は、[!DNL Target Standard/Premium]と[!UICONTROL Recommendations Classic]の両方に表示されます。

## 目的

（オプション）アクティビティの目標を記述します。

## 優先度

スライダーを調節して優先度を決定します。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

## 期間

アクティビティの期間を設定します。

アクティビティは、アクティブ化されたときに開始したり、特定の日時を設定したりできます。 同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。 時間ピッカーは24時間の時計を使用し、00:00は真夜中です。 タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。 別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## レポート設定

* **レポート Source:**&#x200B;どのソリューション データを収集するかを指定します：

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  レポート ソリューションが[&#x200B; アカウント設定](/help/main/administrating-target/reporting.md)で指定されている場合、指定されたソリューションが使用され、この設定は表示されません。

  アクティビティが公開された後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。

  **[!DNL Adobe Analytics]**: レポートソリューションと各ソリューションの利点の違いについて詳しくは、 [!DNL Target][&#128279;](/help/main/c-integrating-target-with-mac/a4t/a4t.md)のレポートソースとして[!DNL Adobe Analytics] を参照してください。

  [!DNL Analytics]を[!DNL Target] （A4T）のレポートソースとして選択する場合、[!DNL Analytics] レポートスイートを選択して[!DNL Target] アクティビティデータを受信します。 これを行うには、最初にアカウントが関連付けられている[!DNL Analytics]社の中から選択し、次にアクティビティに適したレポートスイートを選択します。 [!DNL Target]に接続するようにプロビジョニングされたレポートスイートのみが選択できます。 期待するレポートスイートが表示されない場合は、まずログアウトして[!DNL Adobe Experience Cloud]に再度ログインし、もう一度やり直してください。 レポートスイートがまだリストにない場合は、[&#x200B; カスタマーケア &#x200B;](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

  [!DNL Analytics for Target] （A4T）は、結果を正しく報告するためにトラッキングサーバーを必要とします。 デフォルトのトラッキングサーバーが「[!UICONTROL &#x200B; トラッキングサーバー]」フィールドに表示されます。 複数のトラッキングサーバーを使用する場合は、このフィールドに正しいトラッキングサーバーを含めてください。 詳しくは、[Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)を参照してください。

  **[!DNL Adobe Customer Journey Analytics]**: [!DNL Adobe Customer Journey Analytics]と[!DNL Target]の統合について詳しくは、 [!DNL Adobe Customer Journey Analytics][&#128279;](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)の[!DNL Target]  レポートを参照してください。

* **目標指標：**&#x200B;アクティビティが成功したかどうかを判定する成功指標を選択します。
* **追加の指標：**&#x200B;レポートに使用する追加の成功指標を設定します。
* **レポート対象のオーディエンス：**&#x200B;レポートをフィルタリングする際に使用できるオーディエンスを定義します。

## その他のメタデータ

アクティビティに関するメモを入力します。

## トレーニングビデオ：アクティビティ設定（3:02） ![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
