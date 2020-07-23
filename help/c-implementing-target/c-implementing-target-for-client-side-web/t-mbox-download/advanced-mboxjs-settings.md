---
keywords: advanced mbox.js settings;client;server domain;xdomain;compression level;client session id support;secureOnly;client pc id support;pass page;referring url;traffic level;traffic duration;mboxParameters() function body;mboxSupported() function body;mboxCookieDomain() function body;Extra JavaScript;SiteCatalyst plug-in;Get mbox.js as self-extracting JavaScript;flicker;body hiding;hide body
description: mbox.js の設定ページでいくつかの設定をおこなう方法を説明します。
title: mbox.js を設定
uuid: e79c7af7-f8bd-4e2b-8e67-b04eddf0c65d
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 91%

---


# mbox.js を設定{#configure-mbox-js}

mbox.js の設定ページでいくつかの設定をおこなう方法を説明します。

[!DNL mbox.js] 関数ライブラリのデフォルト設定は、ほとんどの [!DNL Target] 顧客のニーズに対応しています。

[!DNL mbox.js] の設定を変更する必要がある場合は、アカウント担当者に相談してください。

以下の設定を使用できます。

## クライアント

アカウントのクライアントコード。

When viewing [!UICONTROL Administration > Implementation], the Client at the top is the client code for your account.

## タイムアウト

Target リクエストのタイムアウト。

[!UICONTROL 管理/実装を表示する場合]、「タイムアウト（秒）」設定はTargetリクエストのタイムアウトになります。 デフォルトでこの値は 15 秒に設定されますが、2～5 秒の間に設定することをお勧めします。

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