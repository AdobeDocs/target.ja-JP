---
keywords: advanced mbox.js settings;client;server domain;xdomain;compression level;client session id support;secureOnly;client pc id support;pass page;referring url;traffic level;traffic duration;mboxParameters() function body;mboxSupported() function body;mboxCookieDomain() function body;Extra JavaScript;SiteCatalyst plug-in;Get mbox.js as self-extracting JavaScript;flicker;body hiding;hide body
description: mbox.js の設定ページでいくつかの設定をおこなう方法を説明します。
title: mbox.js を設定
feature: at.js
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 74%

---


# mbox.js を設定

mbox.js の設定ページでいくつかの設定をおこなう方法を説明します。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリ [!DNL Adobe Target] はサポートされなくなります。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

[!DNL mbox.js] 関数ライブラリのデフォルト設定は、ほとんどの [!DNL Target] 顧客のニーズに対応しています。

[!DNL mbox.js] の設定を変更する必要がある場合は、アカウント担当者に相談してください。

以下の設定を使用できます。

## クライアント

アカウントのクライアントコード。

[!UICONTROL 管理/導入]を表示すると、上部のクライアントは、アカウントのクライアントコードです。

## タイムアウト

Target リクエストのタイムアウト。

[!UICONTROL 管理/導入]を表示した場合、「タイムアウト（秒）」設定は、ターゲットリクエストのタイムアウトになります。 デフォルトでこの値は 15 秒に設定されますが、2～5 秒の間に設定することをお勧めします。

## XDomain

ブラウザーで Cookie を設定する場合、お客様独自のドメインで設定するか（ファーストパーティ Cookie）、Target のドメインで設定するか、またはその両方で設定するかどうかを指定します。

この設定を変更すると、mbox.js と at.js の両方に影響があります。

## 圧縮レベル

mbox.js ライブラリファイルをどの程度圧縮するかを指定します。圧縮レベルを高くすると、ページロード時間が短くなります。

## mboxParameters() 関数本体

各 mbox の呼び出しに渡される追加のパラメーターを返します。

次に例を示します。

return &quot;test=123&quot;;

## mboxSupported() 関数本体

特定のユーザーを除外するために、false を返します。

次に例を示します。

return !navigator.userAgent.indexOf(&#39;Safari&#39;) ! = -1;

以下のブラウザーを受け入れるか、または除外することができます。

* IE 5.0 以降（Windows）
* Netscape 5.0 以降（Windows、Mac OS、Linux）
* Safari 1.2.4 以降（Mac OS）
* Mozilla Firefox 1.0 以降（Windows、Mac OS、Linux）

## mboxCookieDomain() 関数本体

ファーストパーティ Cookie を設定するためのドメインを説明する文字列を返します。

次に例を示します。

return &quot;YOUR-DOMAIN&quot;;

## 追加の JavaScript

各ページで実行するすべての追加の JavaScript が含まれます。

## SiteCatalyst プラグイン

Analytics Target プラグインを有効にします。

有効にすると、Analytics プラグインによって mbox.js 内にプラグインコードが生成されます。このコードにより、Analytics でタグ付けされたすべてのページで、Analytics のタグ情報が mbox リクエストとして Target サーバーに送信されます。

Analytics プラグインはページ上で引き続き参照されている必要があります。

## secureOnly

mbox.js で HTTPS のみを使用するか、ページのプロトコルに基づいて HTTP と HTTPS との切り替えを許可するかを示します。これは詳細設定で、デフォルトでは False に設定されています。