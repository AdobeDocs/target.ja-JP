---
keywords: order confirmation;orderConfirmPage
description: 注文の確認 mbox では、サイトでの注文に関する詳細が記録され、売上高および注文に基づくレポートが可能になります。また、注文の確認 mbox は、「商品 x および商品 y を購入した人」などのレコメンデーションアルゴリズムを駆動できます。
title: 注文の確認 mbox の作成 - mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 85%

---


# 注文の確認 mbox の作成 - mbox.js{#create-an-order-confirmation-mbox-mbox-js}

注文の確認 mbox では、サイトでの注文に関する詳細が記録され、売上高および注文に基づくレポートが可能になります。また、注文の確認 mbox は、「商品 x および商品 y を購入した人」などのレコメンデーションアルゴリズムを駆動できます。

>[!NOTE]
>
>* ユーザーが Web サイトで買い物をする場合、レポートに Analytics for Target（A4T）を使用している場合でも、注文の確認 mbox を実装することをお勧めします。
   >
   >
* at.js 1用に注文の確認mboxを作成することもできます。*同じ方法* を使用してただし、 [!DNL at.js] 方法をお勧めします。詳細については、「[コンバージョンの追跡](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)」を参照してください。
   >
   >
* at.js 2を使用している場合。*x*、 `mboxCreate` はサポートされなくなりました。at.js 2を使用した注文確認。*x*、次のトラッキング関連APIを使用します。 [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) および [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)。


1. 注文の詳細ページで、以下のモデルに示す mbox スクリプトを挿入します。
1. 大文字のテキストを、カタログの動的値または静的値に置き換えます。

   >[!NOTE]
   >
   >複数の製品 ID を区切るには、コンマを使用してください。

   **ヒント：**&#x200B;任意の mbox に注文情報を渡すこともできます（`orderConfirmPage` という名前にする必要はありません）。また、同じキャンペーン内の複数の mbox に注文情報を渡すこともできます。

   ```
   <div class="mboxDefault"> 
      <!-- CONTENT TO SHOW IF NO OFFERS AVAILABLE. --> 
   </div> 
   <script type="text/javascript">    
      mboxCreate('orderConfirmPage', 
      'productPurchasedId=PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3', 
      'orderTotal=ORDER TOTAL FROM YOUR ORDER PAGE', 
      'orderId=ORDER ID FROM YOUR ORDER PAGE'); 
   </script> 
   ```

注文の確認 mbox では、次のパラメーターを使用します。

| パラメーター | 説明 |
|--- |--- |
| `orderId` | 注文を識別する一意の値（コンバージョンのカウントに使用）。<br>`orderId` は一意である必要があります。重複する注文はレポートで無視されます。 |
| `orderTotal` | 購入金額。<br>通貨記号を渡さないでください。（コンマではなく）小数点を使用して、10 進数値を示します。 |
| `productPurchasedId`（オプション） | この注文で購入された製品 ID のコンマ区切りのリスト。<br>これらの製品 ID は監査レポートに表示され、さらに詳細なレポート分析ができます。 |