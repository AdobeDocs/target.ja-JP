---
keywords: レスポンシブ；モバイルビューポート；ビューポート；デバイス；モバイル；レスポンシブ web デザイン；rwd
description: モバイルビューポートを使用すると、Adobe [!DNL Target] アクティビティは、様々なサイズの Screens を参照します。 一般的なデバイスの表示域のサイズと解像度のリストを見つけます。
title: レスポンシブエクスペリエンスでモバイルビューポートを使用する方法を教えてください。
feature: Visual Experience Composer (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 37%

---

# レスポンシブエクスペリエンスのためのモバイルビューポート

モバイルビューポートを使用すると、 [!DNL Adobe Target] 様々なサイズの画面でのアクティビティ。

モバイルビューポートプレビュー機能は、様々なデバイス、ウィンドウ、画面サイズで適切にレンダリングされるレスポンシブサイト用に設計されています。 レスポンシブサイトは、デスクトップ、ノートパソコン、タブレット、携帯電話を含む、あらゆる画面サイズに自動的に調整および適応します。

>[!NOTE]
>
> * サイトがレスポンシブで、デスクトップページと同じ要素が異なる設定でモバイルページに使用されている場合、モバイルビューポートを使用します。別の構造を持つ別のモバイルサイトがある場合 ( 例： `m.mysite.com`、 [複数ページアクティビティ](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) 代わりに、
>
>* リダイレクトオファーのオーバーレイと重複する場合、モバイルビューポートは利用できません。


ビューポートは、画面いっぱいに広げられた Web ページの長方形のサイズで定義されます。ビューポートは、ブラウザーウィンドウのサイズからスクロールバーとツールバーを引いたサイズです。 ブラウザーは、「CSS ピクセル」を使用します。Retina ディスプレイを備えたデバイスなど、多くのデバイスでは、ビューポートは、宣伝されているデバイスの解像度より小さくなります。

一般的なデバイスのビューポートと解像度を次に示します。 必ずでビューポートサイズを [!DNL Target].

>[!NOTE]
>
>人気のデバイスのビューポートのサイズは様々な web サイトに表記されています。例えば、 `https://viewportsizer.com/devices/`. 最も正確で最新の情報については、デバイスメーカーの Web サイトを参照してください。

| デバイス | ビューポートサイズ（幅 x 高さ） | デバイスの解像度（幅 x 高さ） |
|---|---|---|
| iPhone 12 | 390 x 844 | 1170 x 2532 |
| iPhone 12 Mini | 360 x 780 | 1080 x 2340 |
| iPhone 12 Pro | 390 x 844 | 1170 x 2532 |
| iPhone 12 Pro Max | 428 x 926 | 1248 x 2778 |
| iPhone SE | 214 x 379 | 640 x 1136 |
| iPhone 11 Pro Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 Xs Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 | 414 x 896 | 828 x 1792 |
| iPhone 11 Xr | 414 x 896 | 828 x 1792 |
| iPhone 11 Pro | 375 x 812 | 1125 x 2436 |
| iPhone 11 X | 375 x 812 | 1125 x 2436 |
| iPhone 11 Xs | 375 x 812 | 1125 x 2436 |
| iPhone X | 375 x 812 | 1125 x 2436 |
| iPhone 8 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 8 | 375 x 667 | 750 x 1334 |
| iPhone 7 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 7 | 375 x 667 | 750 x 1334 |
| iPhone 6s Plus | 414 x 736 | 1080 x 1920 |
| iPhone 6s | 375 x 667 | 750 x 1334 |
| iPhone 6 Plus | 414 736 倍 | 1080 x 1920 |
| iPhone 6 | 375 x 667 | 750 x 1334 |
| iPad Pro | 1024 x 1366 | 2048 x 2732 |
| iPad 第 3 ＆第 4 世代 | 768 x 1024 | 1536 x 2048 |
| iPad Air 1 &amp; 2 | 768 x 1024 | 1536 x 2048 |
| iPad Mini | 768 x 1024 | 768 x 1024 |
| iPad Mini 2 &amp; 3 | 768 x 1024 | 1536 x 2048 |
| Nexus 6P | 411 x 731 | 1440 x 2560 |
| Nexus 5X | 411 x 731 | 1080 x 1920 |
| Google Pixel | 411 x 731 | 1080 x 1920 |
| Google Pixel XL | 411 x 731 | 1440 x 2560 |
| Google Pixel 2 | 411 x 731 | 1080 x 1920 |
| Google Pixel 2 XL | 411 x 823 | 1440 x 2880 |
| Samsung Galaxy Note 5 | 480 x 853 | 1440 x 2560 |
| LG G5 | 360w x 640 | 1440 x 2560 |
| LG G4 | 360w x 640 | 1440 x 2560 |
| LG G3 | 360w x 640 | 1440 x 2560 |
| One Plus 3 | 480 x 853 | 1080 x 1920 |
| Samsung Galaxy S9 | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S9+ | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S8 | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S8+ | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S7 | 360 x 640 | 1440 x 2560 |
| Samsung Galaxy S7 Edge | 360 x 640 | 1440 x 2560 |
| Nexus 7 (2013) | 600 x 960 | 1200 x 1920 |
| Nexus 9 | 768 x 1024 | 1536 x 2048 |
| Samsung Galaxy Tab 10 | 800 x 1280 | 800 x 1280 |
| Chromebook Pixel | 1280 x 850 | 2560 x 1700 |

特定のデバイスの訪問者にアクティビティを配信するには、アクティビティダイアグラムでそのデバイスに適したオーディエンスを選択します。 Mobile Web Composer を使用して、そのデバイスのアクティビティのページを編集します。すべてのデバイスで適切に表示されるように、デジタルエクスペリエンス全体でアクティビティを実行する場合は、ターゲティングを適用しないでください。 代わりに、モバイルビューポートを使用して、各画面サイズでアクティビティをプレビューします。

レスポンシブサイトの場合、通常、サイトは、特定の画面サイズを持つデバイスからアクセスされたときに別の表示で開くように設計されています。 新しいビューをトリガーするこれらの画面サイズは、CSS ブレークポイントとも呼ばれます。CSS ブレークポイントとは、訪問者に最適なレイアウトを表示するために、Web サイトのコンテンツがデバイスの幅に応じて応答するポイントです。 CSS ブレークポイントは、 [メディアクエリ](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries).

に CSS ブレークポイントを保存する [!DNL Target] 定義した各ビューでエクスペリエンスをプレビューできます。 各エクスペリエンスは、 [!DNL Target] インターフェイス。 ディスプレイの上部にあるビューポートをクリックして、各画面サイズのビューを開きます。

サイトがレスポンシブでない場合、アクティビティのターゲットが特定のデバイスである場合は、モバイル Web コンポーザーを使用してサイトを表示します。

>[!IMPORTANT]
>
>モバイルビューポート内からエクスペリエンスを編集できます。 ただし、これらの変更は、作業中のビューポートだけでなく、すべてのビューポートとデバイスに適用されます。 同様に、通常のデスクトップビューでのエクスペリエンスの編集は、そのデスクトップビューだけでなく、すべての画面サイズのページを変更します。現在、 [!DNL Target] は、ビューポート固有のページの変更をサポートしていません。

## モバイルビューポート設定 {#task_B4B161499DC0470584ED922A4D20FCAB}

エクスペリエンスを作成する際に、使用可能にするモバイルビューポートを設定します。

1. クリック **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]**.
1. 内 **[!UICONTROL モバイルビューポート設定]** セクションで、 **[!UICONTROL 追加]**.

   ![ビューポートを追加](/help/main/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   または

   既存のモバイルビューポートの設定を変更するには、そのビューポートを選択し、 [!UICONTROL 編集] （鉛筆）アイコンを使用します。

1. モバイルビューポートの名前を入力します。

   モバイルビューポートに認識しやすい説明的な名前を付けます。名前は、36 文字まで入力できます。

1. モバイルデバイスの画面サイズの幅と高さを指定します。

   幅は、150 ～ 968 ピクセルにする必要があります。 高さは 150 ～ 1280 ピクセルにする必要があります。

1. （オプション）デバイスのオペレーティングシステムを選択します。

   オプション：

   * Android
   * iOS
   * Windows
   * Symbian
   * BlackBerry

   [拡張 Experience Composer](/help/main/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) を使用してオペレーティングシステムを選択する場合、 は、ページを表示する際にデバイスをエミュレートします。[!DNL Target]例えば、レスポンシブサイト上のiOSとは異なる Android のルックアンドフィールがある場合、 [!DNL Target] はその行動を模倣します。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>使用中のモバイルビューポートを削除しようとすると、次のメッセージが表示されます。「このビューポートは、現在、1 つ以上のアクティビティに関連付けられています。 ビューポートを削除する前に、これらのアクティビティからビューポートを削除する必要があります。」

## レスポンシブエクスペリエンスの作成 {#task_D6332438B5EE48CCA8AF199270F1CAEF}

にモバイルビューポートを追加する [!DNL Target] アクティビティを使用してモバイル画面用のレスポンシブエクスペリエンスを作成します。

1. を作成します。 [望ましい活動](/help/main/c-activities/activities.md).
1. 内 [!UICONTROL Visual Experience Composer] (VEC)、 **[!UICONTROL 設定]** 歯車アイコンをクリックし、 **[!UICONTROL モバイルビューポートを追加]**.

   ![「モバイルビューポートを追加」オプション](/help/main/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 「**[!UICONTROL デバイス]**」アイコンをクリックし、モバイルビューポートの設定が必要な各デバイスを有効にします。

   ![モバイルビューポートを有効にする](/help/main/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   モバイルビューポートは、幅が最小のものから最大のものへと順番にリストされます。

1. 必要に応じて、モバイルビューポートを編集します。

   エクスペリエンスに加えた変更は、すべてのデバイスのエクスペリエンスに適用されます。 例えば、見出しのテキストを変更するとします。

   ビューポート名の上にマウスポインターを置くと、ビューポートのサイズが表示されます。

   ![iPhone 11 Pro Max レスポンシブエクスペリエンス](/help/main/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. 必要に応じて、目的の向きアイコンをクリックして、縦長モードと横長モードを切り替えます。

   ![向きオプション](/help/main/c-experiences/c-visual-experience-composer/assets/orientation.png)

## トレーニングビデオ

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### Visual Experience Composer（2／2）（7：29）![概要バッジ](/help/main/assets/overview.png)

以下のデモビデオには、Visual Experience Composer を使用したモバイルビューポートとの連携に関する情報が含まれています。

* エクスペリエンスの名前の変更と複製
* リダイレクトエクスペリエンスの作成
* 単一の URL または URL のグループに対するアクティビティのターゲット化
* 複数ページのアクティビティの作成
* レスポンシブ Web サイト用のエクスペリエンスのプレビューおよび構築
* オーバーレイを使用した要素のタイプのハイライト

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Adobe Targetのアカウント環境設定 ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、4:40 から始まる、モバイルビューポートの設定に関する情報を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
