---
keywords: mbox;mbox3rdPartyId;プロファイル同期;PCID
description: メンバーシップIDや組織のロイヤルティプログラムなど、組織の訪問者IDであるmbox3rdPartyIdの使用方法について説明します。
title: mbox3rdPartyIdでリアルタイムプロファイル同期を使用する方法を教えてください。
feature: オーディエンス
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 61%

---

# mbox3rdPartyId のリアルタイムプロファイル同期

[!DNL Adobe Target]のmbox3rdPartyIdは、会社のロイヤルティプログラムのメンバーシップIDなど、会社の訪問者IDです。

訪問者が会社のサイトにログインすると、通常、会社は訪問者のアカウント、ロイヤルティカード、メンバーシップ番号またはその会社で適用できるその他の識別子に結び付けられる ID を作成します。

訪問者が [!DNL Target] が有効なページにアクセスすると、その訪問者に [!DNL Target] PCID が割り当てられます。訪問者がその後ログインすると、実装は mbox3rdPartyId を [!DNL Target] に渡し、[!DNL Target] はその訪問者の mbox3rdPartyId に [!DNL Target] PCID を使用して接続します。

3 ～ 5 分ごとに、更新がデータベースと同期されます。訪問者がログアウトすると、結合されたデータがmbox3rdPartyIdに関連付けられた以前のデータを置き換え、その訪問者の行動の完全な記録を作成します。 両方の ID に同じ属性が存在する場合（例えば、PCID が category=hats を持ち、mbox3rdPartyId が category=skis を持つ）、またはログインする前に訪問者にエクスペリエンス A が表示されたがエクスペリエンス B が mbox3rdPartyId に保存されている場合、mbox3rdPartyId に保存されている属性が PCID からの属性を上書きします。訪問者がログイン前に 1 つのアクティビティまたはエクスペリエンスにいたが、別のアクティビティおよびエクスペリエンスが mbox3rdPartyId に保存されている場合、ログイン後、その訪問者は mbox3rdPartyId アクティビティおよびエクスペリエンスに配置されます。

| PCID（ログインなし） | mbox3rdPartyId（ログインしている） | 結合されて mbox3rdPartyId に保存 |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| アクティビティ 1、エクスペリエンス A | アクティビティ 1、エクスペリエンス B | アクティビティ 1、エクスペリエンス B |
| アクティビティ 1 |  | アクティビティ 1 |

訪問者がログアウトしても、結合されたプロファイルは維持されます。

>[!NOTE]
>
>認証済み（ログイン済み）ユーザーと非認証ユーザーを区別する場合は、mbox3rdPartyIDの代わりに[!DNL Adobe Experience Cloud Identity Service](ECID)を使用します。 ユーザーとmbox3rdPartyIDを関連付けた後は、サインアウト後もそのユーザーとの関連付けは維持されます。

>[!NOTE]
>
>[!DNL Adobe Analytics] プロファイルがmbox3rdPartyIdに基づいて結合され、まだアクティビティ情報がある場合でも、 [!DNL Adobe Experience Cloud] ID(EDID)が変更された場合（例えば、訪問者がデバイスを変更した場合など） [!DNL Target] は、目標は追跡されません。同じEDIDで識別される訪問者（同じデバイスでページにアクセスした訪問者）の場合、 [!DNL Analytics for Target] (A4T)は期待どおりに動作します。

## 注意点 {#considerations}

ページに複数のmboxが含まれ、一部のmboxのみが3rdPartyIDを使用する場合、 [!DNL Target]には訪問者リクエストごとに個別の訪問者プロファイル/コンテキストはありません。 3rdPartyID コンテキストは、PCID コンテキストよりも優先されます。PCID よりも優先させるには、1 つの mbox がそのコンテキストの 3rdPartyId を渡すだけで十分です。

例えば、訪問者がログインしてエクスペリエンスを表示する前にページにアクセスしたとします。 グローバル mbox は 3rdPartyID を使用しません。ログイン後、この訪問者が、子 mbox を使用する 3 つのエクスペリエンス（一部が 3rdPartyID を使用）のいずれかを表示します。訪問者は、サイトの様々なページを訪問してから、戻るボタンを使用してログイン前にアクセスしたメインページに戻り、様々なエクスペリエンスを表示します。このシナリオでは、グローバル mbox は 3rdPartyID を渡しませんが、1 つ以上の子 mbox が渡しています。3rdPartyID は、PCID よりも優先されています。
