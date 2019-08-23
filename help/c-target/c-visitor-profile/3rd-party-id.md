---
description: mbox3rdPartyIDは、会社のロイヤルティプログラムのメンバーシップIDなど、会社の訪問者IDです。
keywords: mbox;mbox3rdPartyID;プロファイル同期;プロファイル同期;PCID
seo-description: 'リアルタイムプロファイルに関する情報 '
seo-title: Adobe Targetのmbox3rdPartyIDのリアルタイムプロファイル同期
solution: Target
title: mbox3rdPartyIDのリアルタイムプロファイル同期
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyIDは、会社のロイヤルティプログラムのメンバーシップIDなど、会社の訪問者IDです。

訪問者が会社のサイトにログインすると、通常、会社は訪問者のアカウント、ロイヤルティカード、メンバーシップ番号またはその会社で適用できるその他の識別子に結び付けられる ID を作成します。

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

3 ～ 5 分ごとに、更新がデータベースと同期されます。訪問者がログアウトすると、mbox3rdPartyIDに関連付けられた以前のデータが結合されたデータに置き換えられ、その訪問者のアクションの完全な記録が作成されます。同じ属性が両方のIDに存在する場合——例えば、PCIDにcategory= hatsがあり、mbox3rdPartyIDにcategory= skisがあり、訪問者がログイン前にエクスペリエンスAを閲覧した場合、エクスペリエンスBはmbox3rdPartyIDに保存されます——mbox3rdPartyIDに保存されている属性は、PCIDから属性を上書きします。訪問者がログイン前に1つのアクティビティまたはエクスペリエンスに含まれていた場合、異なるアクティビティとエクスペリエンスがmbox3rdPartyIDに保存され、その訪問者はmbox3rdPartyIDアクティビティおよびエクスペリエンスに配置されます。

| PCID（ログインなし） | mbox3rdPartyID（ログイン済み） | mbox3rdPartyIDに結合および保存 |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| アクティビティ 1、エクスペリエンス A | アクティビティ 1、エクスペリエンス B | アクティビティ 1、エクスペリエンス B |
| アクティビティ 1 |  | アクティビティ 1 |

訪問者がログアウトしても、結合されたプロファイルは維持されます。

>[!NOTE]
>
>[!DNL Adobe Analytics] 目標（MID）が変更された場合（例えば、訪問者 [!DNL Adobe Experience Cloud] がデバイスを変更した場合）、プロファイルが [!DNL Target] mbox3rdPartyIDに基づいて結合され、まだアクティビティ情報がある場合でも、目標が追跡されません。同じ MID で識別される訪問者（同じデバイスでページにアクセスした訪問者）の場合、[!DNL Analytics for Target]（A4T）は想定どおりに動作します。

## 注意点 {#considerations}

ページに複数のmboxが含まれており、一部のmboxのみが使用されている場合、Targetには各訪問者リクエストの個別訪問者プロファイル/コンテキストがありません。3rdPartyIDコンテキストはPCIDコンテキストより優先されます。PCIDより優先されるように、1つのmboxに対して3rdPartyIDを渡す必要があります。

例えば、訪問者がログインしてエクスペリエンスを表示する前に、あるページにアクセスしたとします。グローバルmboxでは、3rdPartyIDは使用されません。ログインした後、訪問者には子mboxと共に3つのエクスペリエンスのいずれかが表示され、そのうちの一部は3rdPartyIDを使用します。訪問者はサイトのさまざまなページを訪問し、「戻る」ボタンを使用してログインしてから別のエクスペリエンスを閲覧する前に、アクセスしたメインページに戻ることができます。このシナリオでは、グローバルmboxが3rdPartyIDを渡していませんが、1つ以上の子mboxが発生しました。3rdPartyIDはPCIDより優先されます。
