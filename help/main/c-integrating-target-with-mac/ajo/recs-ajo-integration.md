---
keywords: ajo;adobe journey optimizer;adobe journey optimizer target 統合；レコメンデーション；target レコメンデーション；統合
description: 統合 [!DNL Adobe Target Recommendations] 次を使用 [!DNL Adobe Journey Optimizer].
title: 使用方法 [!DNL Target Recommendations] を使用してカスタマージャーニーで [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
source-git-commit: 1faedc44c4f8f95000b666af8eecaf1eca5bf48d
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 6%

---

# 統合 [!DNL Adobe Target Recommendations] および [!DNL Adobe Journey Optimizer]

この記事では、の統合を設定するのに役立つ使用例と情報を説明します。 [!DNL Adobe Target Recommendation] および [!DNL Adobe Journey Optimizer] つながり、状況に応じて、パーソナライズされたエクスペリエンスを顧客に提供するのに役立ちます。

## 前提条件

次の手順で [!DNL Target Recommendations] および [!DNL Adobe Journey Optimizer] 統合には、以下が必要です。

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) を使用して実装 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}.

  この機能は、 [!DNL Target Standard] ライセンス、または実装時 [!DNL Target] at.js またはその他の [!DNL Target] SDK.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## 使用例

次に、統合の使用例を 2 つ示します。 [!DNL Target Recommendations] 次を使用 [!DNL Adobe Journey Optimizer]:

* **[!DNL Customer Journey Optimizer]買い物かごが放棄された後にパーソナライズされた電子メールを送信**：この使用例は、Web サイトに訪問する顧客が品目を買い物かごに入れて、購入プロセスを完了せずにサイトを離れた場合に基づきます。

  例えば、訪問者が衣料品会社の Web サイトを訪問し、2 枚の冬用コートと 1 枚のトレーナーを買い物かごに入れたとします。 その後、訪問者は気が散って Web サイトを離れるか、購入が不明でブラウザーまたはアプリを閉じます。

  指定した期間の後、おそらく数時間または 1 日後に、 [!DNL Adobe Journey Optimizer] に電話をかける [!DNL Target Recommendations] をクリックして、放棄された買い物かごの内容を判断します。 [!DNL Adobe Journey Optimizer] 次に、この訪問者にパーソナライズされた電子メールを、購入プロセスが完了していないこと、および破棄された品目への画像やリンクをリマインダーとして送信します。

* **[!DNL Customer Journey Optimizer]は、ユーザープロファイルを使用してサイト訪問後に電子メールを送信します**：この使用例は、Web サイトにアクセスし、様々な品目を表示して、買い物かごに品目を入れずにサイトを離れた顧客に基づいています。

  指定した期間が経過した後、 [!DNL Adobe Journey Optimizer] に電話をかける [!DNL Target Recommendations] 訪問者が訪問者の [!DNL Adobe Experience Cloud Identifier] (EDID)。 [!DNL Adobe Journey Optimizer] 次に、この訪問者にパーソナライズされた電子メールを、購入プロセスが完了していないこと、および破棄された品目への画像やリンクをリマインダーとして送信します。

