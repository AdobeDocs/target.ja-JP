---
keywords: global mbox;target classic;use global mbox from target classic
description: Target Standard は、デフォルトで target-global-mbox というグローバル mbox を作成します。この mbox は、Target Standard で作成されるアクティビティの実行に使用されます。ただし、レガシー実装のページで既にグローバル mbox を作成している場合は、その mbox を Target Standard アクティビティで使用できます。
title: レガシー実装のグローバル mbox の使用
subtopic: Getting Started
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 91%

---


# レガシー実装のグローバル mbox の使用{#use-a-global-mbox-from-a-legacy-implementation}

Target Standard は、デフォルトで target-global-mbox というグローバル mbox を作成します。この mbox は、Target Standard で作成されるアクティビティの実行に使用されます。ただし、レガシー実装のページで既にグローバル mbox を作成している場合は、その mbox を Target Standard アクティビティで使用できます。

>[!NOTE]
>
>グローバル mbox は、各アカウントにつき 1 つのみ作成できます。

[!DNL Target Standard] とレガシー実装の両方で既存のグローバル mbox を使用するには、いくつかのパラメーターを設定する必要があります。

1. Go to [!DNL Target Standard], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   デフォルトで、「[!UICONTROL グローバル mbox 自動作成]」が有効になっており、カスタムグローバル mbox の名前が `target-global-mbox` になっています。
1. 既存の mbox を使用する場合は、「[!UICONTROL グローバル mbox 自動作成]」を無効にして、以前に作成したグローバル mbox の名前を「[!UICONTROL カスタムグローバル mbox]」フィールドに指定します。

   [!UICONTROL カスタムグローバル mbox] ドロップダウンリストに、アカウント内のすべての mbox が一覧表示されます。存在しない mbox を使用する場合は、Target Classic で mbox を作成します。
1. 「**[!UICONTROL 保存]**」をクリックします。

   アカウントの mbox.js 設定が更新されます。
1. 新しい mbox.js ファイルをダウンロードして、サイトで参照します。

   本稼動サイトを新しい mbox.js ファイルで更新した後、環境設定を設定します。
1. **[!UICONTROL 管理]** / **[!UICONTROL Visual Experience Composer]**&#x200B;をクリックします。
1. In the [!UICONTROL Global Mbox] field, specify the name of the global mbox you selected on the Implementation page.
1. 「**[!UICONTROL 送信]**」をクリックします。

   作成済みおよび実装済みのアクティビティを含むすべての既存のアクティビティが、指定したグローバル mbox を使用するように更新されます。
   **グローバル mbox 実装のトラブルシューティング** *グローバル mbox が読み込まれない理由、ページ読み込み時にグローバル mbox を読み込む時間に遅延が発生する理由を調べます。*

mbox.js 参照が、ページ上で最初の JavaScript 呼び出しであることを確認してください。この問題に対する他の解決策については、「[mbox.jsの実装](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420)」を参照してください。
