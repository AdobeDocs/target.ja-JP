---
keywords: レコメンデーション;設定;名前;目的;優先度;期間;レポート設定;他のメタデータ
description: Adobe TargetでRecommendations アクティビティの説明と制御に使用する設定を行う方法について説明します。
title: Recommendations アクティビティの設定を行う方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
TQID: 'https://experienceleague.adobe.com/pfMAvl6MmLCtH3PZfOR4Ve-WFIc3e2iN2Bh-cIzjeC0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 17%
---
# レコメンデーションアクティビティの設定 {#recs-activity-settings}

>[!BEGINSHADEBOX]

**このページで：** [!DNL Adobe Target]の[!DNL Recommendations] アクティビティを記述および制御する設定について説明します。

>[!ENDSHADEBOX]

アクティビティ設定：[!DNL Recommendations] アクティビティを特定し、いつ、どこで表示するかを制御し、その結果をレポートする方法を定義します。

## 名前

その他のアクション アイコン（![その他のアクション アイコン ](/help/main/assets/icons/MoreSmallListVert.svg)）をクリックし、**[!UICONTROL 名前変更]**&#x200B;をクリックして、アクティビティにわかりやすい名前を付けます。

アクティビティ名には、次の文字は使用できません：`/`、`?`、`#`、`:`、`=`、`+`、`-`、および`@`。

[!UICONTROL Recommendations Classic]の別のアクティビティに[!DNL Recommendations] アクティビティの名前が既に存在する場合、新しいアクティビティは新しい名前で再同期されます。 新しい名前は、タイムスタンプが付加された元の名前で、一意にします。 [!DNL Target Standard/Premium]と[!UICONTROL Recommendations Classic]の両方に表示されます。

## 目的

（オプション）アクティビティの目標を記述します。

## 優先度

スライダーを調整して、優先度レベルを設定します。

優先度は、同じオーディエンスを持つ同じ場所に複数のアクティビティが割り当てられている場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

## 期間

アクティビティの期間を設定します。

アクティビティは、アクティブ化されたときに、または特定の日時に開始できます。 同様に、非アクティブ化された場合、または特定の日時に終了する場合があります。

タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。 タイムゾーンは、ブラウザーで設定されたタイムゾーンです。 別のタイムゾーンを使用するには、ブラウザーをそのタイムゾーンに設定し、ブラウザーを再起動します。

## レポート設定

次の設定は、アクティビティの結果のレポート方法を定義します。

* **[!UICONTROL レポート Source]:** データが収集されるソリューションを指定します：[!DNL Adobe Target]、[!DNL Adobe Analytics]、または[!DNL Adobe Customer Journey Analytics]。

  [ アカウント設定](/help/main/administrating-target/reporting.md)でレポートソリューションが指定されている場合、そのソリューションが使用され、この設定は表示されません。 アクティビティの公開後にレポートソースを変更して、レポートの一貫性を維持することはできません。

  **[!DNL Adobe Analytics]**: レポートソリューションと各ソリューションの利点の違いについては、 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)のレポートソースとして[[!DNL Adobe Analytics] を参照してください。 [!DNL Analytics] レポートスイートとトラッキングサーバーの選択については、[ レポートSource](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source)を参照してください。

  **[!DNL Adobe Customer Journey Analytics]**: [!DNL Adobe Customer Journey Analytics]と[!DNL Target]の統合について詳しくは、 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)の[[!DNL Target]  レポートを参照してください。

* **[!UICONTROL 目標指標]:** アクティビティが成功したかどうかを判断する成功指標を選択します。
* **[!UICONTROL 追加指標]:** レポートの追加成功指標を設定します。
* **[!UICONTROL レポート用オーディエンス ]:** レポートのフィルタリングに使用できるオーディエンスを定義します。

## その他のメタデータ

アクティビティに関するメモを入力します。

## トレーニングビデオ：アクティビティ設定（3:02） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、次のアクティビティ設定について説明します。

* アクティビティの目標を入力します。
* アクティビティの優先度レベルを設定します。
* 開始時間と終了時間を設定します。
* レポート用オーディエンスを追加して、レポートフィルターを作成します。
* アクティビティのメモを入力します。

>[!VIDEO](https://video.tv.adobe.com/v/17381)
