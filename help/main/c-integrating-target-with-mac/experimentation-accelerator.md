---
keywords: experimentation accelerator;target workspace；サンドボックス割り当て；adobe journey optimizer；統合
description: Adobe TargetのワークスペースをExperimentation Accelerator サンドボックスにマッピングして、Adobe TargetとAdobe Journey Optimizerのテストを1か所で確認できるようにする方法を説明します。
title: ' [!DNL Target] をExperimentation Acceleratorと統合するにはどうすればよいですか？'
feature: Integrations
source-git-commit: e6c1d1799a27130524b1965acaffc07e1d08377f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# [!DNL Target]とExperimentation Acceleratorの統合

Experimentation Acceleratorは、管理者が[!DNL Adobe Target]個のワークスペース アクティビティを整理し、アプリケーションに表示する方法を管理するのに役立ちます。 各[!DNL Target] ワークスペースを適切なExperimentation Accelerator サンドボックスにマッピングすることで、[!DNL Adobe Target]と[!DNL Adobe Journey Optimizer]のテストを1か所で表示できます。

➡️ [Adobe Experimentation Acceleratorについて詳しく見る](https://experienceleague.adobe.com/ja/docs/experimentation-accelerator/using/overview)

## 始める前に

サンドボックスの割り当てを設定する前に、必要な権限があることを確認してください。 Experimentation Acceleratorの&#x200B;**[!UICONTROL Administration]**&#x200B;にアクセスするには、**[!UICONTROL Manage configuration]**&#x200B;権限が必要です。

ユーザーは、両方の条件が満たされた場合にのみ、サンドボックスに[!DNL Target] ワークスペースを割り当てることができます。

* ユーザーはExperimentation Acceleratorで&#x200B;**[!UICONTROL Manage configuration]**&#x200B;権限を持っています。
* ユーザーは[!DNL Target]製品管理者です。

## [!DNL Target] ワークスペースのサンドボックス割り当てを設定

ワークスペースを割り当てる前に、[!DNL Target] ワークスペースを1つのサンドボックスにのみ割り当てることで、同じテストのエントリが重複するのを防ぐことができます。

各[!DNL Target] ワークスペースを表示するサンドボックスを選択するには：

1. Experimentation Acceleratorで、**[!UICONTROL Administration]**&#x200B;を開きます。

   ![](assets/experimentation-1.png)

1. 現在の[!DNL Target]個のワークスペースからサンドボックスへの割り当てのテーブルを確認します。

   ![](assets/experimentation-2.png)

1. **[!UICONTROL Edit]** をクリックします。

   ![](assets/experimentation-3.png)

1. サンドボックスごとに、適切な[!DNL Target] ワークスペースを割り当てます。

   ![](assets/experimentation-4.png)

1. **[!UICONTROL Save]**&#x200B;をクリックして変更を適用します。

[!DNL Target] ワークスペースに対して最初の接続を作成した後、更新をシステム全体に反映するには、最大30分かかります。
