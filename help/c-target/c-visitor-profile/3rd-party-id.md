---
description: mbox3rdPartyID は、会社のロイヤルティプログラムのメンバーシップ ID などの、会社の訪問者 ID です。
keywords: mbox、mbox3rdPartyID、プロファイル同期、プロファイルの同期;;PCID
seo-description: 'リアルタイムプロファイルに関する情報 '
seo-title: Adobe Targetのmbox3rdPartyIDのリアルタイムプロファイル同期
solution: 'Target '
title: mbox3rdPartyID のリアルタイムプロファイル同期
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 647776170531230a0d0f0aa3d97565fbb75bc963

---


# mbox3rdPartyID のリアルタイムプロファイル同期{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyID は、会社のロイヤルティプログラムのメンバーシップ ID などの、会社の訪問者 ID です。

訪問者が会社のサイトにログインすると、通常、会社は訪問者のアカウント、ロイヤルティカード、メンバーシップ番号またはその会社で適用できるその他の識別子に結び付けられる ID を作成します。

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyID to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyID with the [!DNL Target] PCID.

3 ～ 5 分ごとに、更新がデータベースと同期されます。訪問者がログアウトすると、結合されたデータが mbox3rdPartyID に関連付けられた以前のデータを置き換え、その訪問者の行動のより完全な記録を作成します。両方の ID に同じ属性が存在する場合（例えば、PCID が category=hats を持ち、mbox3rdPartyID が category=skis を持つ）、またはログインする前に訪問者にエクスペリエンス A が表示されたがエクスペリエンス B が mbox3rdPartyID に保存されている場合、mbox3rdPartyID に保存されている属性が PCID からの属性を上書きします。訪問者がログイン前に 1 つのアクティビティまたはエクスペリエンスにいたが、別のアクティビティおよびエクスペリエンスが mbox3rdPartyID に保存されている場合、ログイン後、その訪問者は mbox3rdPartyID アクティビティおよびエクスペリエンスに配置されます。

| PCID（ログインしていない） | mbox3rdPartyID（ログイン中） | 結合され mbox3rdPartyID に保存 |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| アクティビティ 1、エクスペリエンス A | アクティビティ 1、エクスペリエンス B | アクティビティ 1、エクスペリエンス B |
| アクティビティ 1 |  | アクティビティ 1 |

訪問者がログアウトしても、結合されたプロファイルは維持されます。

>[!NOTE]
>
>[!DNL Target] プロファイルが mbox3rdPartyID に基づいて結合され、プロファイルにまだアクティビティ情報がある場合でも、[!DNL Adobe Experience Cloud] ID（MID）が変更された場合（例えば、訪問者がデバイスを変更した場合など）は、[!DNL Adobe Analytics] 目標は追跡されません。同じ MID で識別される訪問者（同じデバイスでページにアクセスした訪問者）の場合、[!DNL Analytics for Target]（A4T）は想定どおりに動作します。

## 注意点 {#considerations}

ページに複数のmboxが含まれており、一部のmboxのみが使用されている場合、Targetには各訪問者リクエストの個別訪問者プロファイル/コンテキストがありません。3rdPartyIDコンテキストはPCIDコンテキストより優先されます。PCIDより優先されるように、1つのmboxに対して3rdPartyIDを渡す必要があります。

例えば、訪問者がログインしてエクスペリエンスを表示する前に、あるページにアクセスしたとします。グローバルmboxでは、3rdPartyIDは使用されません。ログインした後、訪問者には子mboxと共に3つのエクスペリエンスのいずれかが表示され、そのうちの一部は3rdPartyIDを使用します。訪問者はサイトのさまざまなページを訪問し、「戻る」ボタンを使用してログインしてから別のエクスペリエンスを閲覧する前に、アクセスしたメインページに戻ることができます。このシナリオでは、グローバルmboxが3rdPartyIDを渡していませんが、1つ以上の子mboxが発生しました。3rdPartyIDはPCIDより優先されます。
