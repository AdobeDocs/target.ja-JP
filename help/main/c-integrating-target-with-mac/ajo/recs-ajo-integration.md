---
keywords: ajo;adobe journey optimizer;adobe journey optimizer target 統合；レコメンデーション；target レコメンデーション；統合
description: 統合 [!DNL Adobe Target Recommendations] 次を使用 [!DNL Adobe Journey Optimizer].
title: 使用方法 [!DNL Target Recommendations] を使用してカスタマージャーニーで [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
source-git-commit: d93e58540568fb685bd18ee5e39ad2917323bce4
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 3%

---

# 統合 [!DNL Adobe Target Recommendations] および [!DNL Adobe Journey Optimizer]

この記事では、の統合を設定するのに役立つ使用例と情報を説明します。 [!DNL Adobe Target Recommendations] および [!DNL Adobe Journey Optimizer] つながり、状況に応じて、パーソナライズされたエクスペリエンスを顧客に提供するのに役立ちます。

この統合により、より多くのコンバージョンを促進し、パーソナライズされたレコメンデーションを含む電子メールメッセージの影響を確認できます。

## 前提条件

次の手順で [!DNL Target Recommendations] および [!DNL Adobe Journey Optimizer] 統合には、以下が必要です。

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) を使用して実装 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}.

  この機能は、 [!DNL Target Standard] ライセンス、または実装時 [!DNL Target] at.js またはその他の [!DNL Target] SDK.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## 使用例

これらは、 [!DNL Target Recommendations] 次を使用 [!DNL Adobe Journey Optimizer]:

* **[!DNL Adobe Journey Optimizer]買い物かごが放棄された後にパーソナライズされた電子メールを送信**：この使用例は、Web サイトに訪問する顧客が品目を買い物かごに入れて、購入プロセスを完了せずにサイトを離れた場合に基づきます。

  例えば、訪問者が衣料品会社の Web サイトを訪問し、2 枚の冬用コートと 1 枚のトレーナーを買い物かごに入れたとします。 その後、訪問者は気が散って Web サイトを離れるか、購入が不明でブラウザーまたはアプリを閉じます。

  指定した期間の後、おそらく数時間または 1 日後に、 [!DNL Adobe Journey Optimizer] に電話をかける [!DNL Target Recommendations] を使用して、放棄された買い物かごの内容を判断するには [買い物かごベースのレコメンデーション](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) アルゴリズム。 [!DNL Adobe Journey Optimizer] 次に、この訪問者にパーソナライズされた電子メールを、購入プロセスが完了していないこと、および破棄された品目への画像やリンクをリマインダーとして送信します。

* **[!DNL Adobe Journey Optimizer]サイト訪問後に一括電子メールを送信して、どの項目が閲覧されたかを訪問者に通知します。**：この使用例は、Web サイトを訪問し、様々な品目を表示した後、サイトまたはアプリを離れた訪問者が買い物かごに品目を入れずにそのまま移動した場合に基づきます。

  指定した期間の後、 [!DNL Adobe Journey Optimizer] に電話をかける [!DNL Target Recommendations] 各訪問者の [!DNL Adobe Experience Cloud Identifier] (EDID)、訪問者の [!DNL Target] プロファイル、および [ユーザーベース](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) アルゴリズム。 [!DNL Adobe Journey Optimizer] 次に、対象オーディエンスの各メンバーに、各訪問者の閲覧項目に関する画像とリンクを含むパーソナライズされた電子メールを送信して、訪問者が再訪して購入をおこなえるようにします。

  このシナリオでは、 [!UICONTROL Experience Cloud訪問者 ID] (ECID) および各ユーザーの [!DNL Target] プロファイルは、最近表示されたアルゴリズムに基づいてレコメンデーションを生成するために使用されます。

  例えば、訪問者が小売 Web サイトを訪問し、複数の腕時計を表示したとします。 この訪問者の [!DNL Target] プロファイルが更新され、表示されたウォッチのリストが表示されます。 ECID と訪問者の [!DNL Target] プロファイル、 [!DNL Target] レコメンデーションをに送信します。 [!DNL Adobe Journey Optimizer]. [!DNL Adobe Journey Optimizer] 次に、最近閲覧されたアルゴリズムを使用して、この訪問者が閲覧した腕時計の画像とリンクを含む電子メールを送信します。 別の訪問者は、この訪問者が閲覧した画像と項目へのリンクを含む、パーソナライズされた E メールを受け取ります。 各電子メールメッセージはパーソナライズされます。

* **[!DNL Adobe Journey Optimizer]サイト訪問後に適格訪問者に一括電子メールを送信して、人気の高い品目を提案する**：このユースケースは、Web サイトにアクセスする訪問者に基づいたものですが、特定の項目は表示しません。 特定のオーディエンスの資格を持つすべてのユーザーに対して、次のように E メールが一括で送信されます。

  訪問者が特定のウォッチポイントを表示しないとします。 おそらく、訪問者は単にサイトをクリックして、カテゴリページやブログエントリを閲覧しただけでしょう。 その結果、 [!DNL Target] プロファイルには、最近表示された項目に関する特定の情報はありません。 この状況では、 [!DNL Target Recommendations] は、 [代替レコメンデーション](/help/main/c-recommendations/c-algorithms/backup-recs.md) そのため [!DNL Adobe Journey Optimizer] は、Web サイトで人気のある商品へのリンクを含む電子メールを送信して、訪問者に戻って購入してもらうことができます。


