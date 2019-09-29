---
description: mbox3rdPartyIdは、会社の忠誠度プログラムのメンバーシップIDなど、会社の訪問者IDです。
keywords: mbox;mbox3rdPartyId;profile syncing;profile synch;PCID
seo-description: 'リアルタイムプロファイルに関する情報 '
seo-title: Adobe targetのmbox3rdPartyIdのリアルタイムプロファイル同期
solution: Target
title: mbox3rdPartyIdのリアルタイムプロファイル同期
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyIdは、会社の忠誠度プログラムのメンバーシップIDなど、会社の訪問者IDです。

訪問者が会社のサイトにログインすると、通常、会社は訪問者のアカウント、ロイヤルティカード、メンバーシップ番号またはその会社で適用できるその他の識別子に結び付けられる ID を作成します。

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

3 ～ 5 分ごとに、更新がデータベースと同期されます。訪問者がログアウトすると、mbox3rdPartyIdに関連付けられた以前のデータが結合されたデータに置き換えられ、訪問者のアクションのより完全な記録が作成されます。 同じ属性が両方のIDに存在する場合（例えば、PCIDにcategory=hats、mbox3rdPartyIdにcategory=skis、訪問者がログイン前にエクスペリエンスAを見たが、エクスペリエンスBはmbox3rdPartyIdに保存され、mbox3rdPartyIdに保存された属性がPCIDからの属性を上書きする場合）. 訪問者がログイン前に1つのアクティビティまたはエクスペリエンスにいたが、別のアクティビティとエクスペリエンスがmbox3rdPartyIdに保存される場合、その訪問者のログイン後はmbox3rdPartyIdアクティビティとエクスペリエンスに配置されます。

| PCID（ログインなし） | mbox3rdPartyId（ログイン済み） | mbox3rdPartyIdに結合および保存 |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| アクティビティ 1、エクスペリエンス A | アクティビティ 1、エクスペリエンス B | アクティビティ 1、エクスペリエンス B |
| アクティビティ 1 |  | アクティビティ 1 |

訪問者がログアウトしても、結合されたプロファイルは維持されます。

>[!NOTE]
>
>[!DNL Adobe Analytics] プロファイルがmbox3rdPartyIdに基づいて結合され、アクティビティ情報がまだある場合でも、 [!DNL Adobe Experience Cloud] ID(MID)が変更される場合（訪問者がデバイスを変更する場合など）は、目標は追跡されません [!DNL Target] 。 同じ MID で識別される訪問者（同じデバイスでページにアクセスした訪問者）の場合、[!DNL Analytics for Target]（A4T）は想定どおりに動作します。

## 注意点 {#considerations}

ページに複数のmboxが含まれ、サードパーティIDのみを使用する場合、Targetには、各訪問者リクエストに対して個別の訪問者プロファイル/コンテキストがありません。 サードパーティIDコンテキストは、PCIDコンテキストよりも優先されます。 1つのmboxで、コンテキストの優先順位がPCIDよりも高くなるように、3rdPartyIdを渡すだけで十分です。

例えば、訪問者がログインする前にページにアクセスし、エクスペリエンスを表示したとします。 グローバルmboxは、3rdPartyIDを使用しません。 ログイン後、訪問者には子mboxを持つ3つのエクスペリエンスの1つが表示され、その中には3rdPartyIDを使用するものもあります。 訪問者は、サイトの様々なページを訪問し、[戻る]ボタンを使用してアクセスしたメインページに戻り、ログインして別のエクスペリエンスを確認します。 このシナリオでは、グローバルmboxは3rdPartyIDを渡しませんでしたが、1つ以上の子mboxが渡しました。 サードパーティIDがPCIDよりも優先されました。
