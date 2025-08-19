---
keywords: Visual Experience Composer;VEC;カルーセル
description: Adobe [!DNL Target] Visual Experience Composer （VEC）で編集できるカルーセルを作成する方法を説明します。
title: Visual Experience Composer でカルーセルを作成する方法
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 71%

---

# Visual Experience Composer 内で動作するカルーセルの作成

このトピックでは、[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）で編集できるカルーセルの作成方法を説明します。

次の手順を使用すると、Visual Experience Composer 内で数秒後に変更された場合でも、選択スライドが正しいスライドの「セレクター」を持つことを [!DNL Target] が必ず認識するようになります。 

1. 静的 HTML プレースホルダーを作成します。

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. CSS を追加して外観と操作性をデザインします。

   これには JavaScript を使用しないでください。

   >[!NOTE]
   >
   >現在、Visual Experience Composer でカスタムコードと共に使用する場合は、「[!UICONTROL Render Using JavaScript]」オプションがサポートされません。

1. classNames の更新のみをおこなって、他を非表示にし、タイマーやアニメーションで次を表示するようにします。

   絶対に JavaScript で DOM の構造を更新しないでください。
