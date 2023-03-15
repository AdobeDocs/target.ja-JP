---
keywords: Recommendations;設定;名前;目的;優先度;期間;レポート設定;他のメタデータ
description: Adobe TargetでのRecommendationsアクティビティの説明と制御に使用する設定を行う方法について説明します。
title: どうすればRecommendations Activity を設定できますか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 84%

---

# Recommendations アクティビティの設定

の説明と制御に使用できる設定に関する情報 [!UICONTROL Recommendations] アクティビティ [!DNL Adobe Target].

![Recommendations 目標と設定ページ](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

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

[!UICONTROL Recommendations Classic] の別のアクティビティとして既に存在する [!UICONTROL Recommendation] アクティビティ名を指定すると、新しいアクティビティは、新しい名前で再同期されます。新しい名前は、一意なものにするために、元の名前にタイムスタンプが追加されたものになります。この新しい名前は、 [!DNL Target Standard/Premium] および [!UICONTROL Recommendations Classic].

## 目的

（オプション）アクティビティの目標を記述します。

## 優先度

スライダーを調節して優先度を決定します。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

## 期間

アクティビティの期間を設定します。

アクティビティは、アクティブ化されたときに開始したり、特定の日時を設定したりできます。同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## レポート設定

* **レポートソース：** レポートソースを選択します。 [!DNL Adobe Target] または [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md). アクティビティがライブになった後でレポートソースを変更しないでください。アクティビティがライブになった後にレポートソースを変更すると、レポートの整合性が失われます。
* **目標指標：**&#x200B;アクティビティが成功したかどうかを判定する成功指標を選択します。
* **追加の指標：**&#x200B;レポートに使用する追加の成功指標を設定します。
* **レポート対象のオーディエンス：**&#x200B;レポートをフィルタリングする際に使用できるオーディエンスを定義します。

## その他のメタデータ

アクティビティに関するメモを入力します。

## トレーニングビデオ：アクティビティの設定(3:02) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
