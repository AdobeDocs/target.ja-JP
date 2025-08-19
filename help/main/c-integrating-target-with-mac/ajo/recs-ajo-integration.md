---
keywords: ajo;adobe journey optimizer;adobe journey optimizer target 統合；recommendations;target recommendations；統合
description: ' [!DNL Adobe Target Recommendations]  と  [!DNL Adobe Journey Optimizer] の統合'
title: ' [!DNL Target Recommendations]  を使用したカ  [!DNL Adobe Journey Optimizer] タマージャーニーの使用方法'
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# [!DNL Adobe Target Recommendations] と [!DNL Adobe Journey Optimizer] の統合

この記事では、[!DNL Adobe Target Recommendations] と [!DNL Adobe Journey Optimizer] の統合に関するユースケースとガイダンスを説明し、連続性がありコンテキストに応じてパーソナライズされた顧客体験を提供できるようにします。

この統合により、より多くのコンバージョンを促進し、パーソナライズされたレコメンデーションを含むメールメッセージの影響を確認できます。

## 前提条件

[!DNL Target Recommendations] と [!DNL Adobe Journey Optimizer] の統合を使用するには、以下が必要です。

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) は、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} を使用して実装されます。

  この機能は、[!DNL Target Standard] ライセンスでは使用できません。また、at.js や他の [!DNL Target] SDK を使用して [!DNL Target] を実装する場合にも使用できません。

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target=_blank} をクリックしてレポートスイートを変更することもできます。

## サンプルユースケース

これらのユースケースは、[!DNL Target Recommendations] と [!DNL Adobe Journey Optimizer] を統合する際に考えられるユースケースのほんの一部です。

* **[!DNL Adobe Journey Optimizer]は、買い物かごの放棄の後にパーソナライズされたメールを送信します**：このユースケースは、Web サイトを訪問し、商品を買い物かごに配置した後、購入プロセスを完了せずにサイトを離れた顧客に基づいています。

  例えば、訪問者が衣料品会社の web サイトを訪問し、2 つの冬のコートと 1 つのスウェットシャツを買い物かごに入れたとします。 その後、訪問者は気を取られて web サイトを離れたり、購入を確信できずブラウザーやアプリを閉じてしまいます。

  [!DNL Journey Optimizer] のカスタムアクションは、指定した期間（数時間または 1 日など）の後、[!DNL Target Recommendations] 買い物かごベースの Recommendations[ アルゴリズムを使用して、放棄された買い物かごの内容を決定する ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) を呼び出します。 次に、[!DNL Journey Optimizer] は、購入プロセスが完了しなかったことを示すパーソナライズされたメールを、画像および破棄された項目へのリンクと共に、この訪問者に送信します。

* **[!DNL Adobe Journey Optimizer]は、サイト訪問後に一括メールを送信して、閲覧された項目を訪問者に思い出させます**：このユースケースは、Web サイトを訪問し、様々な項目を表示した後、買い物かごに項目を配置せずにサイトまたはアプリを離れた訪問者に基づきます。

  [!DNL Journey Optimizer] のカスタムアクションは、指定された期間が経過すると、[!DNL Target Recommendations] を呼び出し、各訪問者が閲覧した項目を判断します。これには、各訪問者の [!DNL Adobe Experience Cloud Identifier] （EDID）、訪問者の [!DNL Target] プロファイル、および [ ユーザーベース ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) アルゴリズムが使用されます。 [!DNL Adobe Journey Optimizer] の後、選定オーディエンスの各メンバーに、画像と各訪問者が閲覧した項目へのリンクを含むパーソナライズされたメールを送信し、訪問者が戻って購入を行えるようにします。

  このシナリオでは、各訪問者の [!UICONTROL Experience Cloud Visitor ID] プロファイルの [!DNL Target] （ECID）とコンテンツを使用して、最近表示されたアルゴリズムに基づいてレコメンデーションを生成します。

  例えば、訪問者が小売 web サイトを訪問し、複数のウォッチを表示したとします。 この訪問者の [!DNL Target] プロファイルは、閲覧されたウォッチのリストで更新されます。 [!DNL Target] は、ECID と訪問者の [!DNL Target] プロファイルを使用して、レコメンデーションを [!DNL Journey Optimizer] に送信します。 次に、[!DNL Journey Optimizer] は、最近閲覧されたアルゴリズムを使用して、この訪問者が閲覧した時計への画像とリンクを含むメールを送信します。 別の訪問者は、画像と、この訪問者が閲覧した項目へのリンクを含む、パーソナライズされたメールを受信します。 各メールメッセージは、訪問者ごとにパーソナライズされます。

* **[!DNL Adobe Journey Optimizer]は、サイト訪問後に資格のある訪問者に一括メールを送信して、人気のある項目を提案し** す。このユースケースは、Web サイトを訪問したが、特定の項目を表示しなかった訪問者に基づきます。 メールは、特定のオーディエンスに該当するすべての訪問者に一括で送信されます。以下に例を示します。

  訪問者が特定の時計を表示しないとします。 おそらく、訪問者はサイト内をクリックするだけで、カテゴリページやブログエントリを閲覧したのでしょう。 その結果、[!DNL Target] プロファイルには、最近表示したアイテムに関する特定の情報がありません。 この場合、[!DNL Target Recommendations] は [ 代替レコメンデーション ](/help/main/c-recommendations/c-algorithms/backup-recs.md) [!DNL Journey Optimizer] を使用して、画像と web サイト上の人気のアイテムへのリンクを含むメールを送信して、訪問者を再訪問させ、場合によっては購入を行わせることができます。
