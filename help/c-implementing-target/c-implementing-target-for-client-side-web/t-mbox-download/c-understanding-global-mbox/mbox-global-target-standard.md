---
keywords: global mbox;target classic;use global mbox from target classic
description: Target Standard は、デフォルトで target-global-mbox というグローバル mbox を作成します。この mbox は、Target Standard で作成されるアクティビティの実行に使用されます。ただし、レガシー実装のページで既にグローバル mbox を作成している場合は、その mbox を Target Standard アクティビティで使用できます。
title: レガシー実装のグローバル mbox の使用
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---


# レガシー実装のグローバル mbox の使用{#use-a-global-mbox-from-a-legacy-implementation}

デフォルトでは、[!DNL Target]は、[!DNL Target]で作成されたアクティビティを実行するために使用する、ターゲット — グローバルmboxというグローバルmboxを作成します。 ただし、レガシー実装のページで既にグローバル mbox を作成している場合は、その mbox を [!DNL Target] アクティビティで使用できます。

>[!NOTE]
>
>グローバル mbox は、各アカウントにつき 1 つのみ作成できます。

[!DNL Target] とレガシー実装の両方で既存のグローバル mbox を使用するには、いくつかのパラメーターを設定する必要があります。

1. [!DNL Target]に移動し、**[!UICONTROL 管理]**/**[!UICONTROL 実装]**&#x200B;をクリックします。

   デフォルトでは、**[!UICONTROL ページ読み込みが有効です(グローバルmbox]**&#x200B;を自動作成が有効で、カスタムグローバルmboxの名前は`target-global-mbox`です。

1. 既存のmboxを使用する場合は、**[!UICONTROL ページ読み込み有効（グローバルmbox]**&#x200B;を自動作成）を無効にし、以前に作成したグローバルmboxの名前を&#x200B;**[!UICONTROL グローバルmbox]**&#x200B;フィールドに指定します。

   [!UICONTROL グローバルmbox]ドロップダウンリストは、アカウント内のすべてのmboxを指定します。 存在しないmboxを使用する場合は、mboxを作成します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   アカウントの mbox.js 設定が更新されます。

1. 新しいat.jsファイルをダウンロードし、サイトで参照します。

   作成済みおよび実装済みのアクティビティを含むすべての既存のアクティビティが、指定したグローバル mbox を使用するように更新されます。

## グローバルmbox実装のトラブルシューティング

次のFAQを使用して、グローバルmbox実装のトラブルシューティングを行うことができます。

### グローバル mbox が読み込まれない理由、ページ読み込み時にグローバル mbox を読み込む時間に遅延が発生する理由を調べます。

at.js参照が、ページ上で最初のJavaScript呼び出しであることを確認します。 この問題の他の解決策については、[グローバルmboxに関するよくある質問](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)を参照してください。
