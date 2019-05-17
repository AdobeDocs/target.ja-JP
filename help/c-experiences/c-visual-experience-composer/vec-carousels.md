---
description: このトピックでは Visual Experience Composer（VEC）内で編集できるカルーセルの作成方法を説明します。
keywords: Visual Experience Composer;VEC;カルーセル
seo-description: このトピックでは Visual Experience Composer（VEC）内で編集できるカルーセルの作成方法を説明します。
seo-title: Visual Experience Composer 内で動作するカルーセルの作成
solution: 'Target '
subtopic: 多変量分析テスト
title: Visual Experience Composer 内で動作するカルーセルの作成
topic: Standard
uuid: 19538f6e-445c-49ca-9f0d-b49fc330b721
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Visual Experience Composer 内で動作するカルーセルの作成{#creating-carousels-that-work-in-the-visual-experience-composer}

このトピックでは Visual Experience Composer（VEC）内で編集できるカルーセルの作成方法を説明します。

次の手順を使用すると、Visual Experience Composer 内で数秒後に変更された場合でも、選択スライドが正しいスライドの「セレクター」を持つことを [!DNL Target] が必ず認識するようになります。 

1. 静的 HTML プレースホルダーを作成します。

   ```
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