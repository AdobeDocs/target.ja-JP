---
keywords: Recommendations;設定;名前;目的;優先度;期間;レポート設定;他のメタデータ
description: Adobe TargetのRecommendations アクティビティを記述および制御するために使用する設定を行う方法について説明します。
title: Recommendations アクティビティの設定は、どうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 50%

---

# Recommendations アクティビティの設定

[!DNL Adobe Target] の [!UICONTROL Recommendations] ーザーアクティビティを説明および制御するために使用できる設定に関する情報です。

![Recommendations 目標と設定ページ](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

次の節では、[!UICONTROL Recommendations] アクティビティで使用できる設定について説明します。

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

[!UICONTROL Recommendations Classic] の別のアクティビティに既に存在する [!UICONTROL Recommendations] しいアクティビティの名前を指定した場合、新しいアクティビティは新しい名前で再同期されます。 新しい名前は、一意なものにするために、元の名前にタイムスタンプが追加されたものになります。この新しい名前は、[!DNL Target Standard/Premium] と [!UICONTROL Recommendations Classic] の両方で表示されます。

## 目的

（オプション）アクティビティの目標を記述します。

## 優先度

スライダーを調節して優先度を決定します。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

## 期間

アクティビティの期間を設定します。

アクティビティは、アクティブ化されたときに開始したり、特定の日時を設定したりできます。同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。

## レポート設定

* **レポートSource:** どのソリューションデータが収集されるかを指定します。

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  [ アカウント設定 ](/help/main/administrating-target/reporting.md) でレポートソリューションが指定されている場合、指定されたソリューションが使用され、この設定は表示されません。

  アクティビティがライブになった後は、レポートの一貫性を維持するためにレポートソースを変更することはできません。

  **[!DNL Adobe Analytics]**: レポートソリューションの違いとそれぞれの利点について詳しくは  [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) のレポートソースとしての） [[!DNL Adobe Analytics]  を参照してください。

  [!DNL Target] （A4T）のレポートソースとして [!DNL Analytics] を選択する場合は、アクティビティデータを受け取る [!DNL Analytics] レポートスイート [!DNL Target] 選択します。 これを行うには、まずアカウントが関連付けられている [!DNL Analytics] の会社のいずれかを選択し、次に、アクティビティに適したレポートスイートを選択します。 [!DNL Target] に接続するようにプロビジョニングされているレポートスイートのみを選択できます。 目的のレポートスイートが表示されない場合は、まずログアウトして [!DNL Adobe Experience Cloud] にログインし直し、もう一度試してください。 それでもリストにレポートスイートが表示されない場合は、[ カスタマーケア ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) にお問い合わせください。

  [!DNL Analytics for Target] （A4T）では、結果を正しく報告するためのトラッキングサーバーが必要です。 デフォルトのトラッキングサーバーが「[!UICONTROL Tracking Server]」フィールドに表示されます。 複数のトラッキングサーバーを使用する場合、このフィールドに正しいトラッキングサーバーを含めてください。 詳しくは [Analytics トラッキングサーバーの使用 ](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) を参照してください。

  **[!DNL Adobe Customer Journey Analytics]**: [!DNL Adobe Customer Journey Analytics] と [!DNL Target] の統合について詳しくは、[[!DNL Target]  でのレポート  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) を参照してください。

* **目標指標：**&#x200B;アクティビティが成功したかどうかを判定する成功指標を選択します。
* **追加の指標：**&#x200B;レポートに使用する追加の成功指標を設定します。
* **レポート対象のオーディエンス：**&#x200B;レポートをフィルタリングする際に使用できるオーディエンスを定義します。

## その他のメタデータ

アクティビティに関するメモを入力します。

## トレーニングビデオ：アクティビティ設定（3:02） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
