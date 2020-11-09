---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: at.jsのグローバルmboxをカスタマイズするのに役立つ情報です。
title: グローバル mbox のカスタマイズ
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 59%

---


# グローバル mbox のカスタマイズ{#customize-a-global-mbox}

at.jsのグローバルmboxをカスタマイズするのに役立つ情報です。

1. [ **[!UICONTROL 管理]** ] > [ **[!UICONTROL 実装]**]の順にクリックします。

1. Disable **[!UICONTROL Page load enabled (Auto create global mbox)]**, then add the name of the custom global mbox that you would like to use to deliver activities from [!DNL Target].

   このカスタムグローバル mbox は、クリック追跡にも使用されます。

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。

1. Implement the [!DNL at.js] library on your site.

   詳しくは、at.jsのデプロイ [方法](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) を参照してください。

1. リリースへの移行のタイミングをはかります。

   [!DNL Target] がすべてのアクティビティについてグローバル mbox を使用し始める準備が整ったら、次の手順をおこないます。

   カスタムグローバル mbox の名前が前述の手順 2 で使用した名前に一致するよう更新します。

   >[!IMPORTANT]
   >
   >保存すると、アカウント内のすべてのアクティビティがこの mbox に同期します。この mbox がサイト上になかった場合、すべてのアクティビティが機能しなくなります。

