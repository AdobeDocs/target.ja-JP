---
keywords: グローバルmbox；グローバルmboxのカスタマイズ；at.jsの編集；at.js;at.jsの実装
description: Adobe Targetの管理 — 実装ページで、at.jsのグローバルmboxをカスタマイズする方法を説明します。
title: グローバルmboxのカスタマイズ方法
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: bc5fd0695121ff99838b3df2a59b36b3a89b2cac
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 18%

---

# グローバル mbox のカスタマイズ

at.jsの[!DNL Adobe Target]グローバルmboxをカスタマイズするのに役立つ情報を紹介します。

1. **[!UICONTROL 管理]**／**[!UICONTROL 実装]**&#x200B;をクリックします。

1. **[!UICONTROL ページ読み込みが有効（グローバルmbox自動作成）]**&#x200B;を無効にし、[!DNL Target]からアクティビティを配信する際に使用するカスタムグローバルmboxの名前を追加します。

   >[!IMPORTANT]
   >
   >別のグローバルmboxを選択すると、変更内容が自動的に保存されます。

   このカスタムグローバル mbox は、クリック追跡にも使用されます。

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. サイトに[!DNL at.js]ライブラリを実装します。

   詳しくは、[at.jsのデプロイ方法](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md)を参照してください。

1. リリースへの移行のタイミングをはかります。

   [!DNL Target]が将来のすべてのアクティビティに対してグローバルmboxを使用し始める準備が整ったら、次の手順に進みます。

   カスタムグローバル mbox の名前が前述の手順 2 で使用した名前に一致するよう更新します。

   >[!IMPORTANT]
   >
   >アカウント内のすべてのアクティビティがこのmboxと同期します。 アクティビティが引き続き機能するように、グローバルmboxがサイトに存在することを確認します。 このmboxと同期するVisual Experience Composer(VEC)で作成した、影響を受けるアクティビティを必ず編集し、再保存してください。 フォームベースのExperience Composerで作成されたアクティビティを再保存する必要はありません。また、APIを使用する必要もありません。

