---
keywords: Visual Experience Composer;VEC;カルーセル
description: Adobe TargetVisual Experience Composer(VEC)で編集できるカルーセルの作成方法を説明します。
title: Visual Experience Composerでカルーセルを作成する方法を教えてください。
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 70%

---


# Visual Experience Composer 内で動作するカルーセルの作成

このトピックでは、[!DNL Adobe Target] [!UICONTROL Visual Experience Composer](VEC)で編集できるカルーセルの作成方法を示します。

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
   >現在、Visual Experience Composer でカスタムコードとともに使用する場合は、「[!UICONTROL JavaScript を使用してレンダリング]」オプションがサポートされません。

1. classNames の更新のみをおこなって、他を非表示にし、タイマーやアニメーションで次を表示するようにします。

   絶対に JavaScript で DOM の構造を更新しないでください。