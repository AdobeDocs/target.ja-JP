---
keywords: ajo;adobe journey optimizer;adobe journey optimizer targetとの統合；レコメンデーション；ターゲットレコメンデーション；統合
description: ' [!DNL Adobe Target Recommendations] を [!DNL Adobe Journey Optimizer]と統合します。'
title: ' [!DNL Target Recommendations] を使用するカスタマージャーニーで [!DNL Adobe Journey Optimizer]を使用するにはどうすればよいですか？'
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: f6034e83564a9a386e21e4e57279c66cc3c94537
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# [!DNL Adobe Target Recommendations]と[!DNL Adobe Journey Optimizer]の統合

この記事では、[!DNL Adobe Target Recommendations]を[!DNL Adobe Journey Optimizer]と統合するためのユースケースとガイダンスを提供し、連続性のある、コンテキストに沿った、パーソナライズされた顧客体験を提供できるようにします。

この統合により、コンバージョンを促進し、パーソナライズされたレコメンデーションを含むメールメッセージの効果を確認することができます。

## 前提条件

[!DNL Target Recommendations]と[!DNL Adobe Journey Optimizer]の統合を使用するには、次のものが必要です。

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium)は[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}を使用して実装されました。

  この機能は、[!DNL Target Standard] ライセンスでは利用できません。また、[!DNL Target]をat.jsまたはその他の[!DNL Target] SDKで実装する場合も利用できません。

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target=_blank} をクリックしてレポートスイートを変更することもできます。

## 使用例

これらのユースケースは、[!DNL Target Recommendations]と[!DNL Adobe Journey Optimizer]を統合する場合の考えられるユースケースの一部にすぎません。

* **[!DNL Adobe Journey Optimizer]は、カート放棄後にパーソナライズされたメールを送信します**：このユースケースは、顧客がweb サイトを訪問し、ショッピングカートに商品を入れ、購入プロセスを完了せずにサイトを離れることに基づいています。

  例えば、訪問者がアパレル企業のweb サイトを訪問し、ショッピングカートに2つの冬用コートとスウェットシャツを配置したとします。 訪問者はその後、気が散ってweb サイトを離れたり、購入に自信がなくブラウザーやアプリを閉じたりします。

  指定された期間（数時間または1日）が経過すると、[!DNL Journey Optimizer]のカスタムアクションは、[!DNL Target Recommendations]に電話して、[&#x200B; カートベースのレコメンデーション &#x200B;](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) アルゴリズムを使用して、放棄されたショッピングカートの内容を決定します。 その後、[!DNL Journey Optimizer]は、購入プロセスが完了しなかったことを知らせるパーソナライズされた電子メールを、放棄されたアイテムの画像とリンクとともに訪問者に送信します。

* **[!DNL Adobe Journey Optimizer]は、サイト訪問後に一括メールを送信して、どの項目が閲覧されたかを訪問者に通知します**：このユースケースは、訪問者がweb サイトを訪問し、様々な項目を表示し、ショッピングカートに項目を配置せずにサイトまたはアプリを離れることに基づいています。

  指定された期間が経過すると、[!DNL Journey Optimizer]のカスタムアクションは[!DNL Target Recommendations]を呼び出して、各訪問者の[!DNL Adobe Experience Cloud Identifier] （EDID）、訪問者の[!DNL Target] プロファイル、および[&#x200B; ユーザーベースの](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) アルゴリズムを使用して、各訪問者が閲覧した項目を決定します。 次に、[!DNL Adobe Journey Optimizer]は、適格なオーディエンスの各メンバーに対して、各訪問者の閲覧アイテムへの画像とリンクを含むパーソナライズされた電子メールを送信し、訪問者に再購入を依頼します。

  このシナリオでは、[!UICONTROL Experience Cloud Visitor ID] （ECID）と各訪問者の[!DNL Target] プロファイルのコンテンツを使用して、最近表示されたアルゴリズムに基づいてレコメンデーションを生成します。

  例えば、訪問者が小売web サイトにアクセスし、複数の腕時計を閲覧したとします。 この訪問者の[!DNL Target] プロファイルは、閲覧済み時計のリストで更新されます。 ECIDと訪問者の[!DNL Target] プロファイルを使用して、[!DNL Target]様が[!DNL Journey Optimizer]様にレコメンデーションを送信します。 次に、[!DNL Journey Optimizer]は、最近閲覧したアルゴリズムを使用して、この訪問者が閲覧した時計の画像とリンクを含むメールを送信します。 別の訪問者には、その訪問者が閲覧したアイテムの画像とリンクが含まれたパーソナライズされたメールが届きます。 各メールメッセージは、訪問者一人ひとりにパーソナライズされています。

* **[!DNL Adobe Journey Optimizer]は、サイト訪問後に適格な訪問者に一括メールを送信して、人気のあるアイテムを提案します**：このユースケースは、web サイトを訪問した訪問者に基づいていますが、特定のアイテムを表示していません。 電子メールは、特定のオーディエンスに適格なすべての訪問者に一括で送信されます。例：

  訪問者が特定の時計を見ていないと仮定します。 例えば、訪問者がサイト内をクリックし、カテゴリーページやブログ記事を閲覧したとします。 その結果、[!DNL Target] プロファイルには、最近閲覧した項目に関する特定の情報がありません。 このような状況では、[!DNL Target Recommendations]は[&#x200B; バックアップの推奨事項](/help/main/c-recommendations/c-algorithms/backup-recs.md)を使用して、[!DNL Journey Optimizer]が画像とweb サイト上の人気アイテムへのリンクを含む電子メールを送信して、訪問者を再訪問させ、場合によっては購入できるようにします。
