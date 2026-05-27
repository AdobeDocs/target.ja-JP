---
keywords: 概要およびリファレンス
description: Adobe CampaignでAdobe [!DNL Target] を使用してメールコンテンツを最適化する方法を説明します。
title: ' [!DNL Target] をAdobe Campaignと統合するにはどうすればよいですか？'
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
TQID: https://experienceleague.adobe.com/RMW9ijj8UqzrDr1-PKwwfw5aWfH4YmtSi1HR7rLDSZ4
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 372
ht-degree: 32%

---

# [!DNL Target]とAdobe Campaignの統合

[!DNL Target]と[!DNL Adobe Campaign]を使用して、メールコンテンツを最適化します。

メールコンテンツを最適化するには、[!DNL Target]でリダイレクトオファーを作成し、[!DNL Adobe Campaign]を使用してメールオファーを管理します。 例えば、男性と女性の受信者に対して異なるオファーを表示できます。

電子メールを開いた際に、統合が実施されます。 お客様が電子メールを開くと、[!DNL Target]への呼び出しが行われ、コンテンツの動的バージョンが表示されます。 コンテンツは、すべてのブラウザーでサポートされる静的な画像で構成されます。 [!DNL Target]は、オーディエンスレベルまたはセッションレベルでオファーに対する反応を追跡し、そのデータは[!DNL Target]件のレポートで利用できます。

[!DNL Target]は次のデータを追跡できます：

* ユーザーエージェント
* IP アドレス
* 地理的な場所
* [!DNL Target]の訪問者IDに関連付けられているセグメント （法的承認が必要です）
* [!DNL Campaign] データマートからのデータ

いくつかの制限があります。

* 使用できるのは画像のみなので、コンテンツはパーソナライズできません。
* トラッキングは[!DNL Adobe Campaign]で統合されていません。
* 統一されたユーザーエクスペリエンスはありません。

[!DNL Target]と[!DNL Campaign]の両方を使用して、統合の異なる部分を設定します。

* 生のボックスと[!DNL Target]でのエクスペリエンス

>[!NOTE]
>
>rawboxと[!DNL Target]を使用する場合は、[Target に mbox 呼び出しを送信する権限のあるホストを指定する許可リストの作成](/help/main/administrating-target/hosts.md#allowlist)の重要なセキュリティ通知を参照してください。

* [!DNL Campaign]の配信

## 始める前に {#section_FF19BF1BCA064260930BF6C141313B0E}

[!DNL Adobe Campaign]を使用してターゲットメールのオファーを設定する前に、[!DNL Target]で次の設定を行ってください。

* 2つ以上の[!DNL Target] リダイレクト オファー

  [ リダイレクトオファーの作成](/help/main/c-experiences/c-manage-content/offer-redirect.md)を参照してください。

* 各オファーのエクスペリエンスと目的の[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md)を含む[!DNL Target] アクティビティ。

  [URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)を参照してください。

統合の[!DNL Campaign]部分を設定する前に、[!DNL Target]でアクティビティを開始します。

## [!DNL Adobe Campaign]件の電子メールに[!DNL Target]件のオファーを含める {#section_B201BBE27A704E18AF0D553F35695837}

1. [!DNL Adobe Campaign]にメールを作成します。
1. メールのプロパティで、**[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]**&#x200B;をクリックします。
1. 共有アセットからデフォルト画像を選択します。
1. 場所（rawbox）を指定します。
1. 受信者の性別など、その他の決定パラメーターを追加します。
1. 各オファーに少なくとも 1 人の受信者を選択して（この場合、男性および女性）、電子メールをプレビューします。
1. [!DNL Campaign]で、アクティビティとテナントの名前を制御するために使用している[!DNL Target] Edge サーバーを定義します。
1. [!DNL Experience Cloud]のリソースにアクセスできるように、[!DNL Adobe Experience Cloud]に使用する外部アカウントを指定してください。

詳しくは、[!DNL Adobe Campaign] ドキュメントを参照してください。

## ビデオ：[!DNL Target]と[!DNL Campaign]の統合

>[!VIDEO](https://video.tv.adobe.com/v/35149)
