---
description: ページからの呼び出しに Target がどのように応答するかは、使用する Target ライブラリのバージョン、Experience Cloud 訪問者 ID 実装が存在するかどうか、および訪問者 ID があるかどうかによって異なります。
seo-description: ページからの呼び出しに Target がどのように応答するかは、使用する Target ライブラリのバージョン、Experience Cloud 訪問者 ID 実装が存在するかどうか、および訪問者 ID があるかどうかによって異なります。
seo-title: mbox.js ライブラリバージョンによる Target ページ手法
title: mbox.js ライブラリバージョンによる Target ページ手法
uuid: 66f7753e-d9c1-4efa-8b10-fd637c8f53f6
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# mbox.js ライブラリバージョンによる Target ページ手法{#target-page-methods-by-mbox-js-library-version}

ページからの呼び出しに Target がどのように応答するかは、使用する Target ライブラリのバージョン、Experience Cloud 訪問者 ID 実装が存在するかどうか、および訪問者 ID があるかどうかによって異なります。

>[!NOTE]
>
>[!DNL at.js] を使用する場合、すべての呼び出しには JSON が使用されます。このページでは、[!DNL mbox.js] ライブラリバージョンの詳細について説明します。以下のシナリオで説明する動作は、[!DNL at.js] には適用されません。

このセクションでは、次の各シナリオで、ページからの [!DNL Target] 呼び出しに対して [!DNL Target] ライブラリの各バージョンがどのように応答するかに関する情報を提供します。

実装およびライブラリバージョンに応じて、いくつかのタイプまたはエンドポイントがあります。各タイプに精通して、各シナリオで [!DNL Target] がどのように呼び出しに応答するかを理解する必要があります。

| タイプ／エンドポイント | 呼び出し方法 | 応答内容 |
|--- |--- |--- |
| グローバル mbox 自動作成 - 同期 | document.write で呼び出す | document.write() なしの JavaScript |
| グローバル mbox 自動作成 - 非同期 | createElement() で本文に呼び出しを追加 | document.write() なしの JavaScript |
| Standard | document.write で呼び出す | document.write() を含む JavaScript |
| ajax | createElement() で本文に呼び出しを追加 | document.write() なしの JavaScript |
| json | XMLHTTPrequest() で呼び出す | JSON 応答を返す |

>[!IMPORTANT]
>
>標準以外のタイプについて、すべてのカスタムコードおよびオファーは、ajax 環境をサポートするように記述されている必要があります。例えば `document.write()` を含む JavaScript を使用すると、スクリプトは期待どおりに動作しません。

## 訪問者 ID が実装されていない {#section_C6F7213FDE4D48E8BBCB1A9A26310FEE}

[!DNL Target Standard] または [!DNL Premium] を [!DNL mbox.js] と共に使用し、アカウントで[!UICONTROL グローバル mbox の作成]を有効にしている場合、**のバージョンにかかわらず、呼び出しと応答の** グローバル mbox 自動作成（同期）[!DNL mbox.js]タイプが作成されます。

[!UICONTROL Visual Experience Composer] のアクションを使用する代わりに独自のカスタムコードを記述する場合、コードが ajax 環境にふさわしいことを確認してください。例えば `document.write()` を含む JavaScript を使用すると、スクリプトは期待どおりに動作しません。

>[!NOTE]
>
>同じ mbox 名で異なるパラメーターを持つ複数の ajax mbox 呼び出しは、同じページでは動作しません。最初の呼び出しのみ作成されます。

「グローバル mbox 自動作成」を使用しているが、ページに `mboxCreate` 呼び出しもある場合（例えば、レガシー実装で以前使用していたページに [!DNL Target Standard] または [!DNL Premium] を実装している場合）、グローバル mbox 呼び出しはグローバル mbox 自動作成 - 標準エンドポイントを使用して作成され、`mboxCreate` 呼び出しは **標準** エンドポイントを使用して作成されます。**標準** エンドポイントは、`document.write()` を使用して呼び出しおよび応答します。これにより、すべての情報がダウンロードされるまで、ajax 応答で配信されるコンテンツを含むページ読み込みをブロックします。

mboxCreate のみを使用する場合（例えば、[!DNL Target Classic] を使用して作成されたページで）、そのページは通常どおりに動作します。

| 作成方法 | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| グローバル mbox 自動作成 | グローバル mbox 自動作成 - 同期 | グローバル mbox 自動作成 - 同期 | グローバル mbox 自動作成 - 同期 | グローバル mbox 自動作成 - 同期 |
| mboxCreate | Standard | Standard | Standard | Standard |

## 訪問者 ID 実装が存在するが、訪問者 ID が設定されていない {#section_29888A119C7A4753AD287FC845AA63F4}

訪問者 ID が設定されていない場合、そのユーザー用の [!DNL Experience Cloud] 訪問者 cookie はありません。ページは、訪問者 ID サービスを呼び出して訪問者 ID を取得します。は、[!DNL Target]Target を呼び出す ID を持つ応答を待ちます。

>[!NOTE]
>
>[!DNL Mbox.js] v58 では、Target 呼び出しがおこなわれる前に、訪問者 ID が確実に返されるようにすることを強くお勧めします。

[!DNL mbox.js] バージョン 57 をこのシナリオで使用している場合で訪問者 ID 実装がない場合は、前のシナリオで説明したように、通常どおりに動作します。[!DNL mbox.js] バージョン 58 以降は、[!DNL Target] の呼び出しがおこなわれる前に、[!DNL Experience Cloud Visitor ID] サービスが訪問者 ID を返します。これにより、プロファイルおよびオーディエンスコアサービスによって共有されるオーディエンスデータを、訪問者のセッションの最初の [!DNL Target] 呼び出しで利用できるようになります。テストコンテンツが返される前にデフォルトコンテンツのちらつきを防ぐために、[!DNL Target] は、訪問者 ID サービスが返されるまで `<BODY>` を非表示にします。バージョン 58 では、`display:none` を使用してページを非表示にします。これがレスポンシブサイトで問題を発生させるので、バージョン 59 以降は、`opacity:0` を使用してコンテンツを非表示にします。

| 作成方法 | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| グローバル mbox 自動作成 | グローバル mbox 自動作成 - 同期 | グローバル mbox 自動作成 - 非同期 | グローバル mbox 自動作成 - 非同期 | グローバル mbox 自動作成 - 非同期 |
| mboxCreate | Standard | ajax | ajax | ajax |

## 訪問者 ID 実装が存在し、訪問者 ID がある {#section_9CD4AE4C8186425D886398BC3CE6C46D}

訪問者 ID cookie がある場合、[!DNL Target] は訪問者 ID サービスを呼び出す必要はありません。この場合、コンテンツを表示する前に訪問者 ID サービスを待機する必要がありません。バージョン 57～59 では、**グローバル mbox 自動作成 - 同期** タイプが使用されるので、ページは、読み込みが続行される前に、 を呼び出して返されるのを待ちます。[!DNL Target]これにより、デフォルトコンテンツがちらつくことがなくなります。v60 では、**グローバル mbox 非同期タイプ** が使用され、[!DNL Target] は、[!DNL Experience Cloud] オプトアウトサービスの応答を待ちます。オプトアウトサービスは、2016 年秋にリリースされる Data Co-op の一部です。すべての呼び出しが ajax を使用して返されるので、`document.write()` は [!DNL mbox.js] バージョン 60 では使用できません。

| 作成方法 | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| グローバル mbox 自動作成 | グローバル mbox 自動作成 - 同期 | グローバル mbox 自動作成 - 同期 | グローバル mbox 自動作成 - 同期 | グローバル mbox 自動作成 - 非同期（2016 年後半にリリースされる Data Co-op の開発をサポート） |
| mboxCreate | Standard | Standard | Standard | ajax |