---
keywords: Visual Experience Composer;VEC;カルーセル
description: Adobe [!DNL Target] Visual Experience Composer （VEC）で編集できるカルーセルの作成方法について説明します。
title: Visual Experience Composerでカルーセルを作成するにはどうすればよいですか？
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
TQID: 'https://experienceleague.adobe.com/RN04MJgC49BI2-h2e-i-kgSRTejpLHzKACm-hOv2VCE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 2%
---
# [!UICONTROL Visual Experience Composer]で動作するカルーセルを作成しています {#vec-carousels}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL Visual Experience Composer]** （VEC）で編集できるカルーセルを作成する方法を説明します。

>[!ENDSHADEBOX]

次の構造で作成されたカルーセルは、[!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** （VEC）で編集できます。 構造は各スライドのセレクターを有効に保つため、[!DNL Target]は、ページがVECに読み込まれてから数秒後に表示されるスライドが変更された場合でも、常に正しいスライドを識別します。

1. スライドを静的なHTMLのプレースホルダーとして作成し、1つのスライドを表示し、他のスライドをクラスで非表示にします。

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. CSSのみでルックアンドフィールをデザインできます。 これにはJavaScriptを使用しないでください。

   >[!NOTE]
   >
   >**[!UICONTROL JavaScriptを使用したレンダリング]** オプションは、現在、**[!UICONTROL Visual Experience Composer]**&#x200B;でカスタムコードと一緒に使用する場合はサポートされていません。

1. クラス名のみを更新して、次のスライドを表示します。他のスライドを非表示にし、タイマーまたはアニメーションで次のスライドを表示します。 JavaScriptでDOM構造を更新しないでください。
