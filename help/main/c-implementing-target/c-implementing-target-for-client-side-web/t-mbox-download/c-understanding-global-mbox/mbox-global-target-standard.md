---
keywords: グローバル mbox;target classic;target classic からグローバル mbox を使用する
description: Adobeでレガシーグローバル mbox を使用する方法を説明します [!DNL Target] アクティビティを作成します（レガシー実装用にページ上で既にグローバル mbox を作成している場合）。
title: レガシー実装のグローバル mbox を使用できますか？
feature: at.js
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 35%

---

# レガシー実装のグローバル mbox の使用

デフォルトでは、 [!DNL Target] target-global-mbox というグローバル mbox を作成します。この mbox は、 [!DNL Target]. ただし、レガシー実装のページで既にグローバル mbox を作成している場合は、その mbox を [!DNL Target] アクティビティで使用できます。

>[!NOTE]
>
>グローバル mbox は、各アカウントにつき 1 つのみ作成できます。

[!DNL Target] とレガシー実装の両方で既存のグローバル mbox を使用するには、いくつかのパラメーターを設定する必要があります。

1. に移動します。 [!DNL Target]を選択し、「 **[!UICONTROL 管理]** > **[!UICONTROL 実装]**.

   デフォルトでは、 **[!UICONTROL ページ読み込みが有効（グローバル mbox を自動作成）]** が有効になっていて、カスタムグローバル mbox の名前が `target-global-mbox`.

1. 既存の mbox を使用する場合は、 **[!UICONTROL ページ読み込みが有効（グローバル mbox を自動作成）]**&#x200B;をクリックし、以前に作成したグローバル mbox の名前を **[!UICONTROL グローバル mbox]** フィールドに入力します。

   この [!UICONTROL グローバル mbox] ドロップダウンリストに、アカウント内のすべての mbox が表示されます。 存在しない mbox を使用する場合は、mbox を作成します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   アカウントの 設定が更新されます。

1. 新しい at.js ファイルをダウンロードし、サイトで参照します。

   作成済みおよび実装済みのアクティビティを含むすべての既存のアクティビティが、指定したグローバル mbox を使用するように更新されます。

## グローバル mbox 実装のトラブルシューティング

次の FAQ を使用して、グローバル mbox 実装のトラブルシューティングをおこなうことができます。

### グローバル mbox が読み込まれない理由、ページ読み込み時にグローバル mbox を読み込む時間に遅延が発生する理由を調べます。

at.js 参照が、ページ上で最初の JavaScript 呼び出しであることを確認します。 この問題に対する他の解決策については、 [グローバル mbox に関するよくある質問](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/global-mbox-faq/).
