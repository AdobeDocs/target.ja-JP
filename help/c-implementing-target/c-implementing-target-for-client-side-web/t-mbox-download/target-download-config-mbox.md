---
description: Target Standard および Premium では Adobe Target mbox.js ファイルの修正バージョンを使用します。
keywords: 実装;Mbox;mbox.js;mbox.js のダウンロード;mbox.js の設定
seo-description: Target Standard および Premium では Adobe Target mbox.js ファイルの修正バージョンを使用します。
seo-title: mbox.js のダウンロード
solution: 'Target '
subtopic: 導入
title: mbox.js のダウンロード
topic: Standard
uuid: b2a46321-cac7-4924-92dd-a80b50e27cee
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# mbox.js のダウンロード{#download-mbox-js}

Target Standard および Premium では Adobe Target mbox.js ファイルの修正バージョンを使用します。

新しい [!DNL Adobe Target][!UICONTROL  Visual Experience Editor] を使用するには、[!DNL mbox.js] ファイルの一部に JavaScript の行を追加する必要があります。

1. [!DNL Target Standard] で「**[!UICONTROL セットアップ]**」／「**[!UICONTROL 実装]**」の順にクリックします。
1. 「**[!UICONTROL mbox.js をダウンロード]**」をクリックし、プロンプトに従ってファイルを保存します。
1. （条件付き）[!DNL mbox.js] バージョン 60 以降を使用する場合、mbox がレスポンシブサイトのフリッカーをロードするまでデフォルトでページのコンテンツを自動的に表示にするようライブラリを設定します。

   詳細については、「[mbox. js の詳細設定](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C)」の「ページ読み込み時のちらつきを抑える」を参照してください。

1. Web サイトに [!DNL mbox.js] の参照を作成します。

   [!DNL mbox.js] バージョン 57 以降、[!DNL mbox.js] 参照はページの `<head>` セクション内の任意の場所に配置できます。

   >[!IMPORTANT]
   >
   >バージョン 57 未満のバージョンの [!DNL mbox.js] を使用する場合、参照はページの `<head>` セクションの最後の項目として配置する必要があります。mbox.js 参照が最後の項目になっていないと、表示またはパフォーマンス上の深刻な問題が発生する可能性があります。詳しく [は、mbox.jsの機能を参照してください](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) 。

1. 保存した [!DNL mbox.js] ファイルを、コード内で指定したホスティング環境の場所にアップロードします。
