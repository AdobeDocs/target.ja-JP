---
keywords: mbox;mbox3rdPartyId;profile syncing;profile synch;PCID
description: 'リアルタイムプロファイルについて説明します。 '
title: Adobe Target での mbox3rdPartyId のリアルタイムプロファイル同期
feature: visitor profiles
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 81%

---


# mbox3rdPartyId のリアルタイムプロファイル同期{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyId は、会社のロイヤルティプログラムのメンバーシップ ID などの、会社の訪問者 ID です。

訪問者が会社のサイトにログインすると、通常、会社は訪問者のアカウント、ロイヤルティカード、メンバーシップ番号またはその会社で適用できるその他の識別子に結び付けられる ID を作成します。

訪問者が [!DNL Target] が有効なページにアクセスすると、その訪問者に [!DNL Target] PCID が割り当てられます。訪問者がその後ログインすると、実装は mbox3rdPartyId を [!DNL Target] に渡し、[!DNL Target] はその訪問者の mbox3rdPartyId に [!DNL Target] PCID を使用して接続します。

3 ～ 5 分ごとに、更新がデータベースと同期されます。訪問者がログアウトすると、結合されたデータが mbox3rdPartyId に関連付けられた以前のデータを置き換え、その訪問者の行動のより完全な記録を作成します。両方の ID に同じ属性が存在する場合（例えば、PCID が category=hats を持ち、mbox3rdPartyId が category=skis を持つ）、またはログインする前に訪問者にエクスペリエンス A が表示されたがエクスペリエンス B が mbox3rdPartyId に保存されている場合、mbox3rdPartyId に保存されている属性が PCID からの属性を上書きします。訪問者がログイン前に 1 つのアクティビティまたはエクスペリエンスにいたが、別のアクティビティおよびエクスペリエンスが mbox3rdPartyId に保存されている場合、ログイン後、その訪問者は mbox3rdPartyId アクティビティおよびエクスペリエンスに配置されます。

| PCID（ログインなし） | mbox3rdPartyId（ログインしている） | 結合されて mbox3rdPartyId に保存 |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| アクティビティ 1、エクスペリエンス A | アクティビティ 1、エクスペリエンス B | アクティビティ 1、エクスペリエンス B |
| アクティビティ 1 |  | アクティビティ 1 |

訪問者がログアウトしても、結合されたプロファイルは維持されます。

>[!NOTE]
>
>認証済み（ログイン済み）ユーザーと非認証ユーザーを区別する場合は、mbox3rdPartyIDではなく、Adobe Experience CloudIDサービス(ECID)を使用します。 ユーザーがmbox3rdPartyIDに関連付けられた後は、サインアウト後もユーザーとの関連付けは維持されます。

>[!NOTE]
>
>[!DNL Adobe Analytics] mbox3rdPartyIdに基づいてプロファイルが結合され、引き続きアクティビティ情報が存在する場合でも、 [!DNL Adobe Experience Cloud][!DNL Target] ID(EDID)が変更される場合(例えば、訪問者がデバイスを変更する場合)、目標は追跡されません。 For visitors identified with the same EDID (those who access the page with the same device), [!DNL Analytics for Target] (A4T) should work as expected.

## 注意点 {#considerations}

ページにいくつかの mbox が含まれ、一部のみが 3rdPartyID を使用する場合、Target は、訪問者リクエストに対して、別の訪問者プロファイル／コンテキストを持ちません。3rdPartyID コンテキストは、PCID コンテキストよりも優先されます。PCID よりも優先させるには、1 つの mbox がそのコンテキストの 3rdPartyId を渡すだけで十分です。

例えば、訪問者がログインする前にページにアクセスしてエクスペリエンスを表示するとします。グローバル mbox は 3rdPartyID を使用しません。ログイン後、この訪問者が、子 mbox を使用する 3 つのエクスペリエンス（一部が 3rdPartyID を使用）のいずれかを表示します。訪問者は、サイトの様々なページを訪問してから、戻るボタンを使用してログイン前にアクセスしたメインページに戻り、様々なエクスペリエンスを表示します。このシナリオでは、グローバル mbox は 3rdPartyID を渡しませんが、1 つ以上の子 mbox が渡しています。3rdPartyID は、PCID よりも優先されています。
