---
description: Target を Adobe Campaign と共に使用して、電子メールコンテンツを最適化します。
keywords: 概要およびリファレンス
seo-description: Target を Adobe Campaign と共に使用して、電子メールコンテンツを最適化します。
seo-title: Target と Adobe Campaign の統合
solution: 'Target '
title: Target と Adobe Campaign の統合
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Target と Adobe Campaign の統合{#integrate-target-with-adobe-campaign}

Target を Adobe Campaign と共に使用して、電子メールコンテンツを最適化します。

電子メールコンテンツを最適化する（例えば、男性と女性の受信者で異なるオファーを提示する）ために、Target でリダイレクトオファーを作成し、Adobe Campaign を使用して電子メールオファーを管理できます。

電子メールを開いた際に、統合が実施されます。顧客が電子メールを開くと、Target に対する呼び出しがおこなわれて、コンテンツの動的なバージョンが表示されます。コンテンツは、すべてのブラウザーでサポートされる静的な画像で構成されます。Target は、オーディエンスまたはセッションレベルでオファーに対する反応を追跡し、そのデータは、Target のレポートで利用できます。

Target は、次のデータを追跡できます。

* ユーザーエージェント
* IP アドレス
* 地理的な場所
* Target で訪問者の ID に関連付けられたセグメント（法的な承認を必要とします）
* Campaign Datamart からのデータ

いくつかの制限があります。

* 使用できるのは画像のみなので、コンテンツはパーソナライズできません。
* 追跡は、Adobe Campaign と統合されません。
* 統一されたユーザーエクスペリエンスはありません。

   統合の異なる部分を設定するために、Target と Campaign の両方を使用する必要があります。

   * Target の rawbox およびエクスペリエンス
   * Campaign の配信

## 始める前に {#section_FF19BF1BCA064260930BF6C141313B0E}

Adobe Campaign を使用してターゲット化された電子メールオファーを設定する前に、Target で次の設定をおこないます。

* 2 つ以上の Target リダイレクトオファー

   [リダイレクトオファーの作成](https://marketing.adobe.com/resources/help/en_US/target/target/t_offer_redirect.html)を参照してください。
* 各オファーのエクスペリエンスと目的の[成功指標](https://marketing.adobe.com/resources/help/en_US/target/target/r_success_metrics.html)を含む Target アクティビティ

   [URL にリダイレクト](https://marketing.adobe.com/resources/help/en_US/target/target/t_redirect_offer.html)を参照してください。

統合の Campaign 部分を設定し始める前に、Target でアクティビティを開始します。

## Adobe Campaign 電子メールに Target オファーを含める {#section_B201BBE27A704E18AF0D553F35695837}

1. Adobe Campaign で電子メールを作成します。
1. 電子メールのプロパティで、「**[!UICONTROL 含める]**」／「**[!UICONTROL Adobe Target によって提供される動的画像]**」の順にクリックします。
1. 共有アセットからデフォルト画像を選択します。
1. 場所（rawbox）を指定します。
1. 受信者の性別など、その他の決定パラメーターを追加します。
1. 各オファーに少なくとも 1 人の受信者を選択して（この場合、男性および女性）、電子メールをプレビューします。
1. Campaign で、アクティビティおよびテナントの名前を制御するのに使用する Target Edge サーバーを定義します。
1. Experience Cloud で使用する外部アカウントを指定して、Experience Cloud のリソースにアクセスできるようにします。

詳しくは、Adobe Campaign のドキュメントを参照してください。
