---
keywords: 概要およびリファレンス
description: ' [!DNL Adobe Target]で訪問者プロファイルの有効期限が切れるタイミングについて詳しく説明します。'
title: 訪問者プロファイルの有効期間と延長は何ですか？
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
TQID: https://experienceleague.adobe.com/yMfacKgQthOmpfhFiuO-jGGPWZh5VrliOSi0TQ-uis0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 62%

---

# 訪問者プロファイルの有効期間

デフォルトでは、[!DNL Adobe Target]の訪問者プロファイルは、その訪問者の非アクティブ状態が14日後に期限切れになります。 このプロファイル有効期間は延長できます。

追加費用なしにプロファイル有効期間を延長するには、[ClientCare またはアドビのコンサルタントにお問い合わせ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)ください。 有効期間は最長で 90 日間に設定できます。

プロファイルがデフォルトを超えて拡張されている場合、新しい[!DNL Platform Web SDK] ファイルまたはat.js ファイルをダウンロードする必要はありません。

既存のプロファイルの有効期限はリセットされません。 以前の訪問者が 15 日間再訪しなかった場合は、プロファイルが期限切れになります。 以前の訪問者が元の 2 週間のプロファイルの有効期限が切れる前に再訪した場合は、プロファイルの有効期間が延長後のものにリセットされます。 新しい訪問者プロファイルには、延長後のプロファイル有効期間が適用されます。
