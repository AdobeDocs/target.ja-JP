---
keywords: visual experience composer;vec；デフォルト url；強化されたexperience composer;eec；混在コンテンツ；experience スナップショット；モバイルビューポート；css;css セレクター
description: Adobe [!DNL Target] Visual Experience Composer （VEC）の一般的な設定、モバイル ビューポート設定、CSS セレクターを指定して設定する方法について説明します。
title: Visual Experience Composer （VEC）を設定する方法を教えてください。
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
TQID: https://experienceleague.adobe.com/E1ck4-aG4txqaFLs3t3-8bN-BQIoY8stRASTRJfhZMY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
subfeature_v2: id: b1d5cd6a-4ed3-43f6-9a52-2721acea1129id: c011fe9c-b94b-4a88-93d8-f2acece55112id: fc9c2184-9102-403f-bd6c-0055021e4bea
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 676
ht-degree: 49%

---

# [!UICONTROL Visual Experience Composer]の設定

一般設定、モバイルビューポート設定、CSS セレクターを指定して、[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）を設定します。

[!UICONTROL Visual Experience Composer]設定ページにアクセスするには、**[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer].**&#x200B;をクリックします

{{permissions-update}}

>[!NOTE]
>
>このページの設定は、[!DNL Target] アカウント全体に適用されます。

## 一般的な設定

一般設定を[!UICONTROL Visual Experience Composer]に指定できます。

![一般設定セクション ](/help/main/administrating-target/assets/general-settings.png)

以下の設定を使用できます。

### デフォルトの URL

[!UICONTROL Visual Experience Composer]で使用される既定のURLを設定します。 これは、新しいアクティビティのそれぞれに対してエクスペリエンスをセットアップするときに必ず使用される、ホームページのようなデフォルトのページです。 デフォルトの URL を設定しない場合は、各アクティビティを作成するたびに URL を入力する必要があります。

### 拡張された Experience Composer を有効にする {#eec}

iframe バスティングのサイトおよび混合コンテンツを使用したサイトでの編集を許可します。 一部のサイトは、拡張バージョンと互換性がない場合があります。 元の[!UICONTROL Visual Experience Composer]に戻すには、このオプションの選択を解除します。 サイトでのアクティビティの配信はこの選択の影響を受けません。

詳しくは、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

アクティビティレベルで[!UICONTROL Enhanced Experience Composer]を有効にすることもできます。

### 混在コンテンツの読み込み

[!UICONTROL Enhanced Experience Composer] （EEC）を使用してweb サイトを開く際に、混在コンテンツを有効にします。 このオプションを有効にすると、[!DNL Target] プロキシサーバーを介して静的リソースを読み込む際のオーバーヘッドを回避できます。

このオプションは、次のような場合に役立ちます。

* コンテンツセキュリティポリシー（CSP）ヘッダーでは、EECが有効になっているプロキシサーバーを使用せずに、混在コンテンツを読み込むことができます。
* HTTP web サイトでは、EECでの読み込み時間が増加します。JavaScriptや画像などのプロキシ経由で読み込みに時間がかかります。

### アクティビティフロー図でエクスペリエンススナップショットを生成する

エクスペリエンススナップショットを有効にすると、アクティビティワークフローダイアグラムでエクスペリエンスのサムネールが生成されます。 スナップショットを無効にすると、一部のユーザーでパフォーマンスが向上する場合があります。

## モバイルビューポート設定

>[!NOTE]
>
>[!UICONTROL Mobile Viewport Configuration]設定は[Target Premium](/help/main/c-intro/intro.md#premium)機能です。


エクスペリエンスのプレビュー時に、使用するデバイスを追加できます。 各デバイスにはオーディエンスが関連付けられています。

![ モバイルビューポート設定セクション ](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

**[!UICONTROL Add]**&#x200B;をクリックし、モバイルビューポートの記述的な名前を指定し、幅と高さを指定し、目的のオペレーティングシステムを選択してから、[!UICONTROL Save]をクリックします。

モバイルビューポートの追加方法に関する情報については、[モバイルビューポート設定](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)を参照してください。

## CSS セレクター {#css}

[!DNL Target]で CSS セレクターを生成する方法を指定します。

![CSS セレクターセクション ](/help/main/administrating-target/assets/css-selectors.png)

これらのオプションを使用すると、[!DNL Target]に対してサイトの構造を指定して、コンテンツ配信により適した CSS セレクターを生成できます。 デフォルトで、[!DNL Target]はページ上の要素 ID に基づいてセレクターを生成します。 サイトで使用されている ID が少ない場合、または同じページ上に重複する ID が存在する場合は、クラスを使用することをお勧めします。

次のオプションのいずれかまたは両方を選択できます。

### 要素 ID を使用

複数の要素で同じ ID を使用する場合、またはページの読み込みで要素 ID が変更される場合は、このオプションの選択を解除します。

### 要素クラスを使用

デフォルトで、[!DNL Target]は要素 ID のみを使用します。 ただし、ページが[!DNL Adobe Experience Manager]で構築されたページなど、要素を識別するためにクラスを使用するように設計されている場合は、[!UICONTROL Use element classes]も選択する必要があります。

>[!NOTE]
>
>精度を確保するためにすべてが行われましたが、クラスを使用するとエラーが発生する可能性があることに注意してください。 いずれのオプションも選択しない場合も、正確性が低下します。 正確性は、ID > クラス > オプション指定なしの順番です。 必ずページをテストして、セレクターが正しいことを確認してください。

アクティビティごとに、この設定を上書きできます（[!UICONTROL Settings] ギアアイコンをクリックしてから、[!UICONTROL CSS Selectors]を選択します）。 この機能は、別々の設定をおこなう複数のサイトがある場合に特に役立ちます。

>[!NOTE]
>
>アクティビティごとの設定を上書きすることは、[!UICONTROL Automated Personalization]および[!UICONTROL Multivariate Testing] アクティビティでは使用できません。  セレクターについて詳しくは、[Visual Experience Composer で使用される要素セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md)を参照してください。

## トレーニングビデオ：アカウント環境設定（7:33） ![概要バッジ ](/help/main/assets/overview.png)

このビデオでは、アカウント設定に関する情報を説明します。

* [!DNL Target Standard]でのアカウント設定に関する説明

>[!NOTE]
>
>[!DNL Target] [!UICONTROL Administration] メニューUI （旧称[!UICONTROL Setup]）は、パフォーマンスの向上、新機能のリリース時に必要なメンテナンス時間の短縮、製品全体でのユーザーエクスペリエンスの向上を目的として再設計されました。 次のビデオの情報は、一般的には正確ですが、オプションの場所が若干異なる場合があります。 更新されたビデオは間もなく投稿される予定です。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
