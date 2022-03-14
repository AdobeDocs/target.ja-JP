---
keywords: 概要およびリファレンス
description: Adobe [!DNL Target] Adobe Campaignと連携して、e メールコンテンツを最適化できます。
title: 統合方法 [!DNL Target] Adobe Campaignと？
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 41%

---

# 統合 [!DNL Target] Adobe Campaign

用途 [!DNL Target] と [!DNL Adobe Campaign] 電子メールコンテンツを最適化します。

E メールのコンテンツを最適化するには、 [!DNL Target]その後、 [!DNL Adobe Campaign] ：電子メールオファーを管理します。 例えば、男性の受信者と女性の受信者に異なるオファーを表示できます。

電子メールを開いた際に、統合が実施されます。顧客が E メールを開くと、 [!DNL Target] コンテンツの動的バージョンが表示されます。 コンテンツは、すべてのブラウザーでサポートされる静的な画像で構成されます。[!DNL Target] は、オーディエンスまたはセッションレベルでオファーに対する反応を追跡し、そのデータは、 のレポートで利用できます。[!DNL Target]

[!DNL Target] は、次のデータを追跡できます。

* ユーザーエージェント
* IP アドレス
* 地理的な場所
* 訪問者の ID に関連付けられたセグメント ( [!DNL Target] （法的承認を受ける場合）
* データの取得元 [!DNL Campaign] データマート

いくつかの制限があります。

* 使用できるのは画像のみなので、コンテンツはパーソナライズできません。
* トラッキングは、 [!DNL Adobe Campaign].
* 統一されたユーザーエクスペリエンスはありません。

両方を使用 [!DNL Target] および [!DNL Campaign] 統合の様々な部分を設定するには、次の手順に従います。

* 生のボックスと [!DNL Target]

>[!NOTE]
>
>rawboxと[!DNL Target]を使用する場合は、[Target に mbox 呼び出しを送信する権限のあるホストを指定する許可リストの作成](/help/main/administrating-target/hosts.md#allowlist)の重要なセキュリティ通知を参照してください。

* 配信 [!DNL Campaign]

## 始める前に {#section_FF19BF1BCA064260930BF6C141313B0E}

事前準備 [!DNL Adobe Campaign] ターゲット設定した電子メールオファーを設定するには、 [!DNL Target]:

* 2 つ以上 [!DNL Target] リダイレクトオファー

   詳しくは、 [リダイレクトオファーを作成](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* A [!DNL Target] 各オファーのエクスペリエンスと目的の [成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md).

   [URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md)を参照してください。

でアクティビティを開始します。 [!DNL Target] 設定前に [!DNL Campaign] の一部が含まれています。

## 次を含む： [!DNL Target] ～でのオファー [!DNL Adobe Campaign] 電子メール {#section_B201BBE27A704E18AF0D553F35695837}

1. での E メールの作成 [!DNL Adobe Campaign].
1. 電子メールのプロパティで、**[!UICONTROL 含める]**／**[!UICONTROL Adobe Target によって提供される動的画像]**&#x200B;をクリックします。
1. 共有アセットからデフォルト画像を選択します。
1. 場所（rawbox）を指定します。
1. 受信者の性別など、その他の決定パラメーターを追加します。
1. 各オファーに少なくとも 1 人の受信者を選択して（この場合、男性および女性）、電子メールをプレビューします。
1. In [!DNL Campaign]、 [!DNL Target] アクティビティとテナント名の制御に使用するエッジサーバー。
1. に使用する外部アカウントを指定します。 [!DNL Adobe Experience Cloud] その場合、 [!DNL Experience Cloud].

詳しくは、 [!DNL Adobe Campaign] ドキュメント。

## ビデオ：統合 [!DNL Target] と [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
