---
keywords: 電子メール；adbox；電子メール画像 adbox
description: Adobe [!DNL Target] 電子メール内の画像を動的にテストし、電子メールが開かれたときにそれらの画像をその場で変更することも可能にする。
title: 電子メール画像 adbox のテスト方法を教えてください。
feature: Implement Email
role: Developer
exl-id: 87a918d7-83dc-4277-821b-d90302c59736
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 89%

---

# 電子メール画像 adbox のテスト

電子メール内の画像を動的にテストし、電子メールが開かれたときにそれらの画像をその場で変更することもできます。

電子メールでリダイレクターを使用してクリックをトラッキングし、訪問者が到達するランディングページを動的に制御できます。

電子メールの画像テストは、修正バージョンの adbox を使用して実施されます。電子メールクライアントでは cookie の 設定ができないので、電子メールごとに一意の ID を生成する必要があります。この数字は、電子メールからのクリックをトラッキングするために、電子メールで使用する adbox の URL およびすべてのリダイレクターに追加されます。

>[!NOTE]
>
>Target は、画像が開かれたときにその最適化を技術的に処理できますが、各電子メールクライアントはキャッシュを異なる方法で処理するため、正常に処理できるかどうかはクライアントによります。電子メールサービスプロバイダーにかかわらず、画像が開かれたときに実際に取得されるかどうかは、エンドユーザーが電子メールを開くために使用する電子メールクライアント（Gmail アプリ、Outlook、Hotmail など）によって決まります。例えば、Gmail ではほとんどすべてのものをキャッシュするので、エンドユーザーに表示される画像は、Gmail が画像を呼び出してキャッシュするタイミングによって異なります。

**電子メール画像 adbox のサンプルコード：**

```
<img src="https://{clientcode}.tt.omtrdc.net/m2/​{clientcode}/ubox/​image?
mbox={email_header}&
mboxDefault=​{http%3A%2F%2Fwww.domain.com%2Fheader.jpg}&
mboxXDomain=disabled&
mboxSession={123456}&
mboxPC={123456}” border=:"0"/>
```

ここで、以下の値はユーザー特有の値です。

| 値 | 説明 |
|--- |--- |
| clientcode | お客様のクライアントコード。at.js の次のリストでこれを見つけます。 `clientCode='yourclientcode'`. このコードはすべて小文字で表され、特殊文字は含みません。 |
| image | オファータイプ。常に、グラフィック広告の場合は「image」、リダイレクターの場合は「page」になります。 |
| email_header | adbox の名前。 |
| `mboxDefault=http%3A%2F%2Fwww.domain.com%2Fheader.jpg` | 必須。URL を adbox の適切なデフォルトコンテンツに置き換えます。これには絶対参照を指定し、URL エンコードする必要があります。 |
| `mboxXDomain=disabled` | cookie を設定しないよう Target に指示します。 |
| `mboxSession=123456` および `mboxPC=123456` | このユーザーのプロファイルをサイトの既存のプロファイルと結合するために Target で必要な 2 つの値です。123456 は、電子メールごとに生成される一意の識別子です。この値は、すべての adbox およびリダイレクターの URL に動的に挿入します。この数字は、各受信者に送信される電子メールごとに一意である必要があります。毎週 1,000 人の受信者に電子メールを送信する場合は、一意の ID を 1,000 個生成する必要があります。<br>それぞれの電子メールの一意の識別子を、各 adbox およびリダイレクターの URL の mboxSession と mboxPC に割り当てる必要があります。この識別子に推奨される形式は、timestamp-NNNNN です。NNNNN はランダムな 5 桁の数字ですが、任意の英数字の形式も使用できます。大規模な電子メールサービスおよびプログラミング言語の中には、この一意の識別子を生成できるものがあります。 |
