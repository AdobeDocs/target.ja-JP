---
keywords: Recommendations;Settings;name;objective;priority;duration;reporting settings;other metadata
description: いくつかの設定によって、Adobe Target の Recommendations アクティビティの説明を記述したり、制御したりすることができます。
title: Adobe Target での Recommendations アクティビティの設定
feature: recs creation
subtopic: Recommendations
uuid: 7c66d0e8-cecf-4d0d-8c62-5347a7d80a53
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 98%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations アクティビティの設定{#recommendations-activity-settings}

[!UICONTROL Recommendations] アクティビティの説明と制御に使用できる設定に関する情報です。

![Recommendations 目標と設定ページ](/help/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

次のセクションでは、[!UICONTROL Recommendations] アクティビティで使用可能な設定について説明します。

## 名前

アクティビティを特定しやすいわかりやすい名前を設定します。

次の文字はアクティビティ名として入力できません。

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

[!UICONTROL Recommendations Classic] の別のアクティビティとして既に存在する [!UICONTROL Recommendation] アクティビティ名を指定すると、新しいアクティビティは、新しい名前で再同期されます。新しい名前は、一意なものにするために、元の名前にタイムスタンプが追加されたものになります。この新しい名前は、Target Standard/Premium と [!UICONTROL Recommendations Classic] の両方で表示されます。

## 目的

（オプション）アクティビティの目標を記述します。

## 優先度

スライダーを調節して優先度を決定します。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

## 期間

アクティビティの期間を設定します。

アクティビティは、アクティブ化されたときに開始したり、特定の日時を設定したりできます。同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## レポート設定

* **レポートソース：** Adobe Target または [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md) からレポートソースを選択します。アクティビティがライブになった後でレポートソースを変更しないでください。アクティビティがライブになった後にレポートソースを変更すると、レポートの整合性が失われます。
* **目標指標：**&#x200B;アクティビティが成功したかどうかを判定する成功指標を選択します。
* **追加の指標：**&#x200B;レポートに使用する追加の成功指標を設定します。
* **レポート対象のオーディエンス：**&#x200B;レポートをフィルタリングする際に使用できるオーディエンスを定義します。

## その他のメタデータ

アクティビティに関するメモを入力します。

## トレーニングビデオ：アクティビティ設定(3:02) ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)