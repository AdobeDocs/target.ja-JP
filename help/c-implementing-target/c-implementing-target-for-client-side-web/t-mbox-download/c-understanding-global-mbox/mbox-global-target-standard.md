---
keywords: global mbox;target classic;use global mbox from target classic
description: Target Standard は、デフォルトで target-global-mbox というグローバル mbox を作成します。この mbox は、Target Standard で作成されるアクティビティの実行に使用されます。ただし、レガシー実装のページで既にグローバル mbox を作成している場合は、その mbox を Target Standard アクティビティで使用できます。
title: レガシー実装のグローバル mbox の使用
feature: null
subtopic: Getting Started
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 6922b80c88cbd2947c3bfd0cc9d8409ff5dcdcd0
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---


# レガシー実装のグローバル mbox の使用{#use-a-global-mbox-from-a-legacy-implementation}

By default, [!DNL Target] creates a global mbox called target-global-mbox, which is used to run activities created in [!DNL Target]. ただし、レガシー実装のページで既にグローバル mbox を作成している場合は、その mbox を [!DNL Target] アクティビティで使用できます。

>[!NOTE]
>
>グローバル mbox は、各アカウントにつき 1 つのみ作成できます。

[!DNL Target] とレガシー実装の両方で既存のグローバル mbox を使用するには、いくつかのパラメーターを設定する必要があります。

1. Go to [!DNL Target], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   By default, **[!UICONTROL Page load enabled (Auto-create global mbox]** is enabled, and the custom global mbox is named `target-global-mbox`.

1. If you want to use an existing mbox, disable **[!UICONTROL Page load enabled (Auto-create global mbox]**, and specify the name of a previously created global mbox in the **[!UICONTROL Global Mbox]** field.

   The [!UICONTROL Global Mbox] drop-down lists all mboxes in your account. 存在しないmboxを使用する場合は、mboxを作成します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   アカウントの mbox.js 設定が更新されます。

1. 新しいat.jsファイルをダウンロードし、サイトで参照します。

   作成済みおよび実装済みのアクティビティを含むすべての既存のアクティビティが、指定したグローバル mbox を使用するように更新されます。

## グローバルmbox実装のトラブルシューティング

次のFAQを使用して、グローバルmbox実装のトラブルシューティングを行うことができます。

### グローバル mbox が読み込まれない理由、ページ読み込み時にグローバル mbox を読み込む時間に遅延が発生する理由を調べます。

at.js参照が、ページ上で最初のJavaScript呼び出しであることを確認します。 この問題の他の解決策については、「 [グローバルmboxに関するよくある質問](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)」を参照してください。
