---
keywords: 実装;Mbox;mbox.js;mbox.js のダウンロード;mbox.js の設定
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience PlatformWeb SDK(AEP Web SDK)またはat.jsの最新バージョンに移行します。
title: ターゲットmbox.jsライブラリのダウンロード方法
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 58%

---


# mbox.js のダウンロード{#download-mbox-js}

Target Standard および Premium では Adobe Target mbox.js ファイルの修正バージョンを使用します。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリ [!DNL Adobe Target] はサポートされなくなります。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

新しい [!DNL Adobe Target][!UICONTROL  Visual Experience Editor] を使用するには、[!DNL mbox.js] ファイルの一部に JavaScript の行を追加する必要があります。

1. [!DNL Target Standard]の&#x200B;**[!UICONTROL 管理]**/**[!UICONTROL 実装]**&#x200B;をクリックします。
1. 「**[!UICONTROL mbox.js をダウンロード]**」をクリックし、プロンプトに従ってファイルを保存します。
1. （条件付き）[!DNL mbox.js] バージョン 60 以降を使用する場合、mbox がレスポンシブサイトのフリッカーをロードするまでデフォルトでページのコンテンツを自動的に表示にするようライブラリを設定します。

   詳細については、「[mbox. js の詳細設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C)」の「ページ読み込み時のちらつきを抑える」を参照してください。

1. Web サイトに [!DNL mbox.js] の参照を作成します。

   [!DNL mbox.js] バージョン 57 以降、[!DNL mbox.js] 参照はページの `<head>` セクション内の任意の場所に配置できます。

   >[!IMPORTANT]
   >
   >バージョン 57 未満のバージョンの [!DNL mbox.js] を使用する場合、参照はページの `<head>` セクションの最後の項目として配置する必要があります。mbox.js 参照が最後の項目になっていないと、表示またはパフォーマンス上の深刻な問題が発生する可能性があります。詳しくは、[mbox.jsの機能](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md)を参照してください。

1. 保存した [!DNL mbox.js] ファイルを、コード内で指定したホスティング環境の場所にアップロードします。
