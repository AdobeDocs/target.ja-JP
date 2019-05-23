---
description: mbox3rdPartyID は、会社のロイヤルティプログラムのメンバーシップ ID などの、会社の訪問者 ID です。
keywords: mbox、mbox3rdPartyID、プロファイル同期、プロファイルの同期
seo-description: mbox3rdPartyID は、会社のロイヤルティプログラムのメンバーシップ ID などの、会社の訪問者 ID です。
seo-title: mbox3rdPartyID のリアルタイムプロファイル同期
solution: 'Target '
title: mbox3rdPartyID のリアルタイムプロファイル同期
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 17f0612559bae335d261ebc7654bc5d7fe3c0d12

---


# mbox3rdPartyID のリアルタイムプロファイル同期{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyID は、会社のロイヤルティプログラムのメンバーシップ ID などの、会社の訪問者 ID です。

訪問者が会社のサイトにログインすると、通常、会社は訪問者のアカウント、ロイヤルティカード、メンバーシップ番号またはその会社で適用できるその他の識別子に結び付けられる ID を作成します。

訪問者が Target が有効なページにアクセスすると、その訪問者に Target PCID が割り当てられます。訪問者がその後ログインすると、実装は mbox3rdPartyID を Target に渡し、Target はその訪問者の mbox3rdPartyID に Target PCID を使用して接続します。

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
>[!DNL Adobe Analytics] 目標（MID）が変更された場合（例えば、訪問者 [!DNL Adobe Experience Cloud] がデバイスを変更した場合）、プロファイルが [!DNL Target] mbox3rdPartyIDに基づいて結合され、まだアクティビティ情報がある場合でも、目標が追跡されません。同じMID（同じデバイスでページにアクセスした訪問者）で識別される訪問者の場合、（A4T） [!DNL Analytics for Target] は期待どおりに動作します。
