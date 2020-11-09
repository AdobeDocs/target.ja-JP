---
keywords: Implementation;Mbox;mbox.js;download mbox.js;configure mbox.js
description: Target Standard および Premium では Adobe Target mbox.js ファイルの修正バージョンを使用します。
title: mbox.js のダウンロード
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 94%

---


# mbox.js のダウンロード{#download-mbox-js}

Target Standard および Premium では Adobe Target mbox.js ファイルの修正バージョンを使用します。

新しい [!DNL Adobe Target][!UICONTROL  Visual Experience Editor] を使用するには、[!DNL mbox.js] ファイルの一部に JavaScript の行を追加する必要があります。

1. で **[!UICONTROL 管理]** / **[!UICONTROL 実装]** をクリック [!DNL Target Standard]します。
1. 「**[!UICONTROL mbox.js をダウンロード]**」をクリックし、プロンプトに従ってファイルを保存します。
1. （条件付き）[!DNL mbox.js] バージョン 60 以降を使用する場合、mbox がレスポンシブサイトのフリッカーをロードするまでデフォルトでページのコンテンツを自動的に表示にするようライブラリを設定します。

   詳細については、「[mbox. js の詳細設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C)」の「ページ読み込み時のちらつきを抑える」を参照してください。

1. Web サイトに [!DNL mbox.js] の参照を作成します。

   [!DNL mbox.js] バージョン 57 以降、[!DNL mbox.js] 参照はページの `<head>` セクション内の任意の場所に配置できます。

   >[!IMPORTANT]
   >
   >バージョン 57 未満のバージョンの [!DNL mbox.js] を使用する場合、参照はページの `<head>` セクションの最後の項目として配置する必要があります。mbox.js 参照が最後の項目になっていないと、表示またはパフォーマンス上の深刻な問題が発生する可能性があります。詳しくは、 [mbox.jsの機能を参照してください](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) 。

1. 保存した [!DNL mbox.js] ファイルを、コード内で指定したホスティング環境の場所にアップロードします。
