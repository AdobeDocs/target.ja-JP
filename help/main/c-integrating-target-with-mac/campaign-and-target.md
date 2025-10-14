---
keywords: 概要およびリファレンス
description: AdobeをAdobe Campaignと共に使用してメールコ  [!DNL Target]  テンツを最適化する方法を説明します。
title: をAdobe Campaign [!DNL Target]  統合する方法
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 32%

---

# [!DNL Target] とAdobe Campaignの統合

[!DNL Target] と [!DNL Adobe Campaign] を使用すると、メールコンテンツを最適化できます。

メールコンテンツを最適化するには、[!DNL Target] でリダイレクトオファーを作成した後、[!DNL Adobe Campaign] れを使用してメールオファーを管理します。 例えば、男性の受信者と女性の受信者に異なるオファーを表示できます。

電子メールを開いた際に、統合が実施されます。顧客がメールを開くと、[!DNL Target] に対する呼び出しが行われて、コンテンツの動的バージョンが表示されます。 コンテンツは、すべてのブラウザーでサポートされる静的な画像で構成されます。[!DNL Target] は、オファーに対する反応をオーディエンスレベルまたはセッションレベルでトラッキングし、そのデータは [!DNL Target] のレポートで使用できます。

次のデータを追跡で [!DNL Target] ます。

* ユーザーエージェント
* IP アドレス
* 地理的な場所
* [!DNL Target] 内の訪問者の ID に関連付けられたセグメント （法的承認の対象）
* データマートから [!DNL Campaign] データ

いくつかの制限があります。

* 使用できるのは画像のみなので、コンテンツはパーソナライズできません。
* トラッキングは、[!DNL Adobe Campaign] では統合されません。
* 統一されたユーザーエクスペリエンスはありません。

[!DNL Target] と [!DNL Campaign] の両方を使用して、統合の様々な部分を設定します。

* 生のボックスと [!DNL Target] のエクスペリエンス

>[!NOTE]
>
>rawboxと[!DNL Target]を使用する場合は、[Target に mbox 呼び出しを送信する権限のあるホストを指定する許可リストの作成](/help/main/administrating-target/hosts.md#allowlist)の重要なセキュリティ通知を参照してください。

* [!DNL Campaign] の配信

## 始める前に {#section_FF19BF1BCA064260930BF6C141313B0E}

[!DNL Adobe Campaign] を使用してターゲットメールオファーを設定する前に、[!DNL Target] で以下を設定します。

* 2 つ以上の [!DNL Target] リダイレクトオファー

  [&#x200B; リダイレクトオファーの作成 &#x200B;](/help/main/c-experiences/c-manage-content/offer-redirect.md) を参照してください。

* 各オファーのエクスペリエンスと目的の [!DNL Target] 成功指標 [&#x200B; を持つ &#x200B;](/help/main/c-activities/r-success-metrics/success-metrics.md) アクティビティ。

  [URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)を参照してください。

統合の [!DNL Target] の部分を設定する前に、[!DNL Campaign] でアクティビティを開始します。

## [!DNL Target] E メールへの [!DNL Adobe Campaign] オファーの組み込み {#section_B201BBE27A704E18AF0D553F35695837}

1. [!DNL Adobe Campaign] でメールを作成します。
1. メールのプロパティで、**[!UICONTROL Include]**/**[!UICONTROL Dynamic image served by Adobe Target]** をクリックします。
1. 共有アセットからデフォルト画像を選択します。
1. 場所（rawbox）を指定します。
1. 受信者の性別など、その他の決定パラメーターを追加します。
1. 各オファーに少なくとも 1 人の受信者を選択して（この場合、男性および女性）、電子メールをプレビューします。
1. [!DNL Campaign] では、アクティビティとテナントの名前の制御に使用する [!DNL Target] Edge サーバーを定義します。
1. [!DNL Adobe Experience Cloud] で使用する外部アカウントを指定して、[!DNL Experience Cloud] のリソースにアクセスできるようにします。

詳しくは、[!DNL Adobe Campaign] ドキュメントを参照してください。

## ビデオ：[!DNL Target] と [!DNL Campaign] の統合

>[!VIDEO](https://video.tv.adobe.com/v/35149)
