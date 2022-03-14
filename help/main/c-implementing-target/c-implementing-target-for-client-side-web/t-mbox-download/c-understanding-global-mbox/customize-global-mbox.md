---
keywords: グローバル mbox；グローバル mbox のカスタマイズ；at.js の編集；at.js;at.js の実装
description: at.js のグローバル mbox をカスタマイズする方法については、Adobe Targetの管理 — 実装ページを参照してください。
title: グローバル mbox のカスタマイズ方法
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 17%

---

# グローバル mbox のカスタマイズ

次の項目をカスタマイズするのに役立つ情報： [!DNL Adobe Target] at.js のグローバル mbox。

1. **[!UICONTROL 管理]**／**[!UICONTROL 実装]**&#x200B;をクリックします。

1. 無効にする **[!UICONTROL ページ読み込みが有効（グローバル mbox を自動作成）]**&#x200B;次に、からアクティビティを配信する際に使用するカスタムグローバル mbox の名前を追加します。 [!DNL Target].

   >[!IMPORTANT]
   >
   >別のグローバル mbox を選択した場合、変更は自動的に保存されます。

   このカスタムグローバル mbox は、クリック追跡にも使用されます。

   ![custom-global-mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. の実装 [!DNL at.js] ライブラリを参照してください。

   詳しくは、 [at.js のデプロイ方法](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) を参照してください。

1. リリースへの移行のタイミングをはかります。

   準備が整ったら、 [!DNL Target] 今後、すべてのアクティビティでグローバル mbox を使用し始めるには、次の手順に進みます。

   カスタムグローバル mbox の名前が前述の手順 2 で使用した名前に一致するよう更新します。

   >[!IMPORTANT]
   >
   >アカウント内のすべてのアクティビティがこの mbox と同期します。 アクティビティが引き続き機能するように、グローバル mbox がサイトに存在することを確認します。 この mbox と同期する Visual Experience Composer(VEC) で作成した、影響を受けるアクティビティを必ず編集し、保存し直してください。 フォームベースの Experience Composer で作成したアクティビティを再保存する必要はありません。また、API を使用する必要もありません。

