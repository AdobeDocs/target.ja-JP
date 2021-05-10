---
keywords: 概要およびリファレンス
description: Adobe [!DNL Target] をAdobe Campaignと共に使用して電子メールコンテンツを最適化する方法を学びます。
title: ' [!DNL Target] をAdobe Campaignと統合する方法'
feature: 統合
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
translation-type: tm+mt
source-git-commit: f3a9ee9827d635d335cb9707d3d92d0de1bd0304
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 36%

---

# [!DNL Target]をAdobe Campaignと統合

[!DNL Target]を[!DNL Adobe Campaign]と共に使用して、電子メールコンテンツを最適化します。

電子メールコンテンツを最適化するには、[!DNL Target]でリダイレクトオファーを作成し、[!DNL Adobe Campaign]を使用して電子メールオファーを管理します。 例えば、男性と女性の受信者に異なるオファーを表示できます。

電子メールを開いた際に、統合が実施されます。顧客が電子メールを開くと、[!DNL Target]への呼び出しが行われ、コンテンツの動的なバージョンが表示されます。 コンテンツは、すべてのブラウザーでサポートされる静的な画像で構成されます。[!DNL Target] は、オーディエンスまたはセッションレベルでオファーに対する反応を追跡し、そのデータは、 のレポートで利用できます。[!DNL Target]

[!DNL Target] は、次のデータを追跡できます。

* ユーザーエージェント
* IP アドレス
* 地理的な場所
* [!DNL Target]内の訪問者のIDに関連付けられたセグメント（法的な承認を受ける場合）
* [!DNL Campaign] Datamartからのデータ

いくつかの制限があります。

* 使用できるのは画像のみなので、コンテンツはパーソナライズできません。
* トラッキングは[!DNL Adobe Campaign]に統合されていません。
* 統一されたユーザーエクスペリエンスはありません。

[!DNL Target]と[!DNL Campaign]の両方を使用して、統合の異なる部分を設定します。

    * raw boxとエクスペリエンスは、 [!DNL Target]
    
    >[!NOTE]
    >
    >rawboxと [!DNL Target], see the important security notice under [Create allowlists that specify hosts that are authorized to send mbox calls to Target](/help/administrating-target/hosts.md#許可リスト)で使用します。
    
    * [!DNL Campaign]

## 始める前に{#section_FF19BF1BCA064260930BF6C141313B0E}

[!DNL Adobe Campaign]を使用してターゲットの電子メールオファーを設定する前に、[!DNL Target]に次の設定を行ってください。

* 2つ以上の[!DNL Target]リダイレクトオファー

   「[リダイレクトオファーの作成](/help/c-experiences/c-manage-content/offer-redirect.md)」を参照してください。

* 各オファーのエクスペリエンスと目的の[成功指標](/help/c-activities/r-success-metrics/success-metrics.md)を含む[!DNL Target]アクティビティ。

   [URL にリダイレクト](/help/c-experiences/c-visual-experience-composer/redirect-offer.md)を参照してください。

統合の[!DNL Campaign]部分を設定する前に、[!DNL Target]にアクティビティを開始します。

## [!DNL Target]オファーを[!DNL Adobe Campaign]電子メールに含める{#section_B201BBE27A704E18AF0D553F35695837}

1. [!DNL Adobe Campaign]に電子メールを作成します。
1. 電子メールのプロパティで、**[!UICONTROL 含める]**／**[!UICONTROL Adobe Target によって提供される動的画像]**&#x200B;をクリックします。
1. 共有アセットからデフォルト画像を選択します。
1. 場所（rawbox）を指定します。
1. 受信者の性別など、その他の決定パラメーターを追加します。
1. 各オファーに少なくとも 1 人の受信者を選択して（この場合、男性および女性）、電子メールをプレビューします。
1. [!DNL Campaign]に、テナントのアクティビティと名前を制御するために使用する[!DNL Target] Edgeサーバーを定義します。
1. [!DNL Adobe Experience Cloud]の外部アカウントにアクセスできるように、[!DNL Experience Cloud]に使用するリソースを指定します。

詳しくは、[!DNL Adobe Campaign]のドキュメントを参照してください。

## ビデオ：[!DNL Target]と[!DNL Campaign]を統合

>[!VIDEO](https://video.tv.adobe.com/v/35149)
