---
keywords: グローバル mbox;target classic;target classic からグローバル mbox を使用する
description: レガシー導入のページに既にグローバルmboxを作成している場合、Adobe [!DNL Target] アクティビティでレガシーのグローバルmboxを使用する方法を説明します。
title: レガシー導入のグローバルmboxを使用できますか。
feature: at.js
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 36%

---

# レガシー導入からのグローバルmboxの使用

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
