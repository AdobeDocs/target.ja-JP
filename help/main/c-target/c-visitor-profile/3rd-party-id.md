---
keywords: mbox;mbox3rdPartyId;プロファイル同期;PCID
description: メンバーシップ ID や組織のロイヤルティプログラムなど、組織の訪問者 ID である mbox3rdPartyId の使用方法を説明します。
title: mbox3rdPartyId にリアルタイムプロファイル同期を使用する方法
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 80%

---

# mbox3rdPartyId のリアルタイムプロファイル同期

[!DNL Adobe Target] の `mbox3rdPartyId` は、会社のロイヤルティプログラムのメンバーシップ ID などの、会社の訪問者 ID です。

訪問者が会社のサイトにログインすると、通常、会社は訪問者のアカウント、ロイヤルティカード、メンバーシップ番号またはその会社で適用できるその他の識別子に結び付けられる ID を作成します。

訪問者が [!DNL Target] が有効なページにアクセスすると、その訪問者に [!DNL Target] PCID が割り当てられます。訪問者がその後ログインし、実装が `mbox3rdPartyId` を [!DNL Target] に渡すと、[!DNL Target] は、その訪問者の `mbox3rdPartyId` を [!DNL Target] PCID に関連付けます。

アップデートは、5～10 分ごとにプロファイルストアと同期されます。 訪問者のセッションが終了すると、`mbox3rdPartyId` ージに関連付けられた以前のデータが、結合されたデータに置き換わり、その訪問者の行動の完全な記録が作成されます。 両方の ID に同じ属性が存在する場合（例えば、PCID で category=hats、`mbox3rdPartyId` で category=skis になっている場合や、ログイン前には訪問者にエクスペリエンス A が表示されたが、`mbox3rdPartyId` にはエクスペリエンス B が格納されているような場合）、 `mbox3rdPartyId` に格納されている属性は、PCID の属性を上書きします。ログイン前に訪問者がいたアクティビティまたはエクスペリエンスとは異なるアクティビティまたはエクスペリエンスが `mbox3rdPartyId` に格納されている場合、その訪問者はログイン後に `mbox3rdPartyId` のアクティビティとエクスペリエンスに移動します。

| PCID（ログインなし） | mbox3rdPartyId（ログインしている） | 結合されて mbox3rdPartyId に保存 |
|---|---|---|
| category=hats | category=skis | category=skis |
|   | store=94103 | store=94103 |
| アクティビティ 1、エクスペリエンス A | アクティビティ 1、エクスペリエンス B | アクティビティ 1、エクスペリエンス B |
| アクティビティ 1 |  | アクティビティ 1 |

訪問者がログアウトしても、結合されたプロファイルは維持されます。

>[!NOTE]
>
>認証済み（ログイン済み）ユーザーと非認証ユーザーを区別する場合は、mbox3rdPartyID ではなく [!DNL Adobe Experience Cloud Identity Service]（ECID）を使用します。ユーザーと mbox3rdPartyID を関連付けたら、ログアウト後も、そのユーザーとの関連付けは維持されます。

>[!NOTE]
>
>[!DNL Adobe Analytics] プロファイルが mbox3rdPartyId に基づいて結合され、まだアクティビティ情報がある場合でも、[!DNL Adobe Experience Cloud] ID （ECID）が変更された場合（例えば、訪問者がデバイスを変更した場合など）は、[!DNL Target] の目標指標は追跡されません。 同じ ECID で識別される訪問者（同じデバイスでページにアクセスした訪問者）の場合、[!DNL Analytics for Target] （A4T）は想定どおりに動作します。

## 注意点 {#considerations}

* ページに複数の mbox が含まれ、一部のみが `3rdPartyID` を使用する場合、[!DNL Target] では、訪問者リクエストごとに別の訪問者プロファイル／コンテキストになることはありません。`3rdPartyID` コンテキストは、PCID コンテキストよりも優先されます。PCID よりも優先させるには、1 つの mbox がそのコンテキストの `3rdPartyId` を渡すだけで十分です。

  例えば、訪問者がログインする前にページにアクセスしてエクスペリエンスを表示するとします。グローバル mbox は `3rdPartyID` を使用しません。ログイン後、訪問者には子 mbox を持つ 3 つのエクスペリエンス（一部は `3rdPartyID` を使用）のいずれかが表示されます。訪問者は、サイトの様々なページを訪問してから、戻るボタンを使用してログイン前にアクセスしたメインページに戻り、様々なエクスペリエンスを表示します。このシナリオでは、グローバル mbox は `3rdPartyID` を渡しませんが、1 つ以上の子 mbox から渡されています。`3rdPartyID` が PCID よりも優先されています。

* 訪問者の顧客 ID を [!DNL Target] に送信するには、次の 2 つの方法があります。

   1. `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` は、`targetPageParams` または `targetPageParamsAll` を使用する場合のパラメーター名です。
      * `thirdPartyId` は、Delivery API ペイロードに直接設定したパラメーター名です。
      * このパラメーターで送信できる値は 1 つだけです。

   1. ECID サービスの `setCustomerId`／`customerIds` 関数を使用します。

      * `setCustomerId` は、VisitorAPI.js がページで使用可能な場合に、クライアント側（ブラウザー）実装で使用できる関数です。
      * `customerIds` は、Delivery API ペイロードで直接設定する際に使用されるパラメーター名で、通常はサーバー側または IOT（Internet of Things）実装で使用されます。
      * `mbox3rdPartyId`／`thirdPartyId` とは異なり、この方法では複数の ID をリストとして送信できますが、[!DNL Target] では TnT ID ごとに 1 つの顧客 ID のみをサポートするので、既知のエイリアス（顧客属性 UI で設定されたエイリアス）を持つリストの最初の ID を使用します。

  [!DNL Target] が唯一の [!DNL Adobe Experience Cloud] ソリューションであり、顧客属性を使用しない場合は、`mbox3rdPartyId`/`thirdPartyId` を使用できます。 それ以外の場合はすべて、顧客 ID の送信に `setCustomerId`/`customerIds` を使用することをお勧めします。

  >[!IMPORTANT]
  >
  > 上記の両方の方法を 1 人の訪問者に交互に使用すると、未認証と認証済みの [!DNL Target] プロファイルが誤って結合される可能性があります。
  >
  >アドビでは、`mbox3rdPartyId`／`thirdPartyId` と `setCustomerID`／`customerIds` の両方を一緒に使用することはお勧めしません。
  >
  >両方の方法を交互に使用する必要がある場合は、`setCustomerID`/`customerIds` で使用されるリストの最初の ID が `thirdPartyId`/`mbox3rdPartyId` で使用される ID であること、およびその逆も成り立つことを確認します。

