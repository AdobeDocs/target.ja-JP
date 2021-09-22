---
keywords: mbox;mbox3rdPartyId;プロファイル同期;PCID
description: メンバーシップIDや組織のロイヤルティプログラムなど、組織の訪問者IDであるmbox3rdPartyIdの使用方法について説明します。
title: mbox3rdPartyIdでリアルタイムプロファイル同期を使用する方法を教えてください。
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 20%

---

# mbox3rdPartyId のリアルタイムプロファイル同期

[!DNL Adobe Target]の`mbox3rdPartyId`は、会社のロイヤルティプログラムのメンバーシップIDなど、会社の訪問者IDです。

訪問者が会社のサイトにログインすると、通常、会社は訪問者のアカウント、ロイヤルティカード、メンバーシップ番号またはその会社で適用できるその他の識別子に結び付けられる ID を作成します。

訪問者が [!DNL Target] が有効なページにアクセスすると、その訪問者に [!DNL Target] PCID が割り当てられます。訪問者がその後ログインし、実装が`mbox3rdPartyId`を[!DNL Target]に渡すと、[!DNL Target]はその訪問者の`mbox3rdPartyId`を[!DNL Target] PCIDで接続します。

3 ～ 5 分ごとに、更新がデータベースと同期されます。訪問者がログアウトすると、結合されたデータが`mbox3rdPartyId`に関連付けられた以前のデータを置き換え、その訪問者の行動の完全な記録を作成します。 両方のIDに同じ属性が存在する場合（例えば、PCIDにcategory=hats、`mbox3rdPartyId`にcategory=skis、または訪問者がログイン前にエクスペリエンスAを見たが、`mbox3rdPartyId`にエクスペリエンスBを格納した場合）、 `mbox3rdPartyId`に格納された属性は、PCIDの属性を上書きします。 ログイン前に訪問者が1つのアクティビティまたはエクスペリエンスにいたが、`mbox3rdPartyId`には別のアクティビティとエクスペリエンスが格納されている場合、ログイン後にその訪問者は`mbox3rdPartyId`アクティビティとエクスペリエンスに配置されます。

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

* ページに複数のmboxが含まれ、一部のmboxのみが`3rdPartyID`を使用する場合、 [!DNL Target]には各訪問者リクエストに対する個別の訪問者プロファイル/コンテキストがありません。 `3rdPartyID`コンテキストは、PCIDコンテキストよりも優先されます。 PCIDよりも優先されるのは、1つのmboxがそのコンテキストの`3rdPartyId`を渡すだけで十分です。

   例えば、訪問者がログインしてエクスペリエンスを表示する前にページにアクセスしたとします。 グローバルmboxは`3rdPartyID`を使用しません。 ログイン後、訪問者には子mboxを使用する3つのエクスペリエンス（一部は`3rdPartyID`を使用）のいずれかが表示されます。 訪問者は、サイトの様々なページを訪問してから、戻るボタンを使用してログイン前にアクセスしたメインページに戻り、様々なエクスペリエンスを表示します。このシナリオでは、グローバルmboxは`3rdPartyID`を渡しませんでしたが、1つ以上の子mboxが渡しました。 `3rdPartyID` がPCIDよりも優先される。

* 訪問者の顧客IDを[!DNL Target]に送信するには、次の2つの方法があります。

   1.  `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` は、またはを使用する際のパラメーター `targetPageParams` 名  `targetPageParamsAll`
      * `thirdPartyId` は、Delivery APIペイロードで直接設定したパラメーター名です。
      * このパラメーターで送信できる値は1つだけです。
   1. ECIDサービスの`setCustomerId`/`customerIds`関数を使用します。

      * `setCustomerId` は、VisitorAPI.jsがページ上で使用可能な場合に、クライアント側（ブラウザー）実装で使用できる関数です。
      * `customerIds` は、配信APIペイロードで直接設定する際に使用されるパラメーター名で、通常はサーバー側またはIOT(Internet of Things)実装でおこなわれます。
      * `mbox3rdPartyId`/`thirdPartyId`とは異なり、この方法ではリストとして複数のIDを送信できますが、 [!DNL Target]はTnT IDごとに1つの顧客IDのみをサポートするので、既知のエイリアス（顧客属性UIで設定されたエイリアス）を持つリストの最初のIDを使用します。

   >[!IMPORTANT]
   >
   > 1人の訪問者に対して、上記の両方の方法を同じ意味で使用すると、未認証と認証済みの[!DNL Target]プロファイルが正しくプロファイル結合されない可能性があります。
   >
   >Adobeでは、`mbox3rdPartyId`/`thirdPartyId`と`setCustomerID`/`customerIds`の両方を一緒に使用することはお勧めしません。
   >
   >両方の方法を同じ意味で使用する必要がある場合は、`setCustomerID`/`customerIds`で使用されるリストの最初のIDが`thirdPartyId`/`mbox3rdPartyId`で使用されるIDであることと、その逆であることを確認します。

