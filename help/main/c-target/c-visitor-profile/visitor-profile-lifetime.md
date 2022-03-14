---
keywords: 概要およびリファレンス
description: 訪問者プロファイルの有効期限を次の期間に設定する： [!DNL Adobe Target].
title: 訪問者プロファイルの有効期間とは何ですか？また、延長することはできますか？
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 62%

---

# 訪問者プロファイルの有効期間

デフォルトでは、 [!DNL Adobe Target] は、その訪問者の無操作状態が 14 日間続くと有効期限が切れます。 このプロファイル有効期間は延長できます。

追加費用なしにプロファイル有効期間を延長するには、[ClientCare またはアドビのコンサルタントにお問い合わせ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)ください。有効期間は最長で 90 日間に設定できます。

新しい [!DNL Platform Web SDK] ファイルまたは at.js ファイル（プロファイルがデフォルトを超えて拡張されている場合）

既存のプロファイルの有効期限はリセットされません。以前の訪問者が 15 日間再訪しなかった場合は、プロファイルが期限切れになります。以前の訪問者が元の 2 週間のプロファイルの有効期限が切れる前に再訪した場合は、プロファイルの有効期間が延長後のものにリセットされます。新しい訪問者プロファイルには、延長後のプロファイル有効期間が適用されます。
