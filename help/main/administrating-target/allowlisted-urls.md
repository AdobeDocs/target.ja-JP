---
keywords: 許可リスト；リモートオファー；管理；URL パターン；検証；アクティビティ；オファー；ワイルドカード；正規表現
description: 検証動作やアカウント全体の範囲など、Adobe Targetの管理セクションで、リモートオファーの許可リストに加えるURLを表示、検索、追加、削除する方法について説明します。
title: 許可リストに加えるされたリモートオファーURLの管理
feature: Administration & Configuration
topic: Implementation
role: Admin
level: Intermediate
solution: Target
product: Target
source-git-commit: 882c91244e5dae0977c8a6a1e5878525f497a720
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# 許可リストに加えるURL

許可リストに加えるURLは、リモートまたはリダイレクトのオファーを使用する場合を含め、組織が[!DNL Adobe Target] エクスペリエンスを作成および実行できる信頼できるURL パターンを定義します。 このリストは、[ ホスト管理](/help/main/administrating-target/hosts.md)および[環境](/help/main/administrating-target/environments.md)と並行して機能しますが、許可されたリモートオファーのURL パターンと関連する検証に特に適用されます。

許可リストに加えるされたURLを管理するには、**[!UICONTROL Administration]** > **[!UICONTROL Allowlisted URLs]**&#x200B;をクリックします。

![URL リスト、検索フィールドおよびURL コントロールを許可リストに加える](../administrating-target/assets/allowlist-1.png)するURL ページを追加しました

## 許可リストに加えるしたURLを管理 {#add-url}

メインテーブルには、1つの列に許可リストに加えるされた各パターンが一覧表示されます。 サポートされるエントリには、正確なURL、ワイルドカードパス、リモートエクスペリエンスに対して組織が受け入れるパターン形式などが含まれます。

1. **[!UICONTROL Add URL]** をクリックします。

   ![](../administrating-target/assets/allowlist-2.png)

1. ダイアログで、組織で許可する必要があるURLまたはパターンを入力します。

   ![](../administrating-target/assets/allowlist-3.png)

1. 変更を保存します。

   パターンを許可リストに加えるした後、他の[!DNL Target] ルールに従って、そのURLに依存するアクティビティとオファーを作成または実行できます。

1. **[!UICONTROL Search URLs]** フィールドを使用して、テーブルをフィルタリングします。

1. URLを削除するには、不要になったパターンの行を見つけて、![削除](../administrating-target/assets/do-not-localize/Smock_Delete_18_N.svg) アイコンをクリックします。

   ![](../administrating-target/assets/allowlist-4.png)


