---
keywords: visual experience composer;vec；デフォルト url；拡張 experience composer;eec；混在コンテンツ；エクスペリエンススナップショット；モバイルビューポート；css;css セレクター
description: 一般設定、モバイルビューポート設定、CSS セレクターを指定して、Adobe [!DNL Target] Visual Experience Composer （VEC）を設定する方法を説明します。
title: Visual Experience Composer （VEC）の設定方法
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 49%

---

# [!UICONTROL Visual Experience Composer] の設定

一般設定、モバイルビューポート設定、CSS セレクターを指定して、[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）を設定します。

[!UICONTROL Visual Experience Composer] 設定ページにアクセスするには、**[!UICONTROL Administration]**/**[!UICONTROL Visual Experience Composer]をクリックします。**

{{permissions-update}}

>[!NOTE]
>
>このページの設定は、[!DNL Target] アカウント全体に適用されることに注意してください。

## 一般的な設定

[!UICONTROL Visual Experience Composer] ージに対して一般設定を指定できます。

![ 一般設定セクション ](/help/main/administrating-target/assets/general-settings.png)

以下の設定を使用できます。

### デフォルトの URL

[!UICONTROL Visual Experience Composer] で使用されるデフォルトの URL を設定します。 これは、新しいアクティビティのそれぞれに対してエクスペリエンスをセットアップするときに必ず使用される、ホームページのようなデフォルトのページです。デフォルトの URL を設定しない場合は、各アクティビティを作成するたびに URL を入力する必要があります。

### 拡張された Experience Composer を有効にする {#eec}

iframe バスティングのサイトおよび混合コンテンツを使用したサイトでの編集を許可します。一部のサイトは、拡張バージョンと互換性がない場合があります。 元の [!UICONTROL Visual Experience Composer] に戻すには、このオプションの選択を解除します。 サイトでのアクティビティの配信はこの選択の影響を受けません。

詳しくは、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

アクティビティレベルで [!UICONTROL Enhanced Experience Composer] を有効にすることもできます。

### 混在コンテンツの読み込み

[!UICONTROL Enhanced Experience Composer] （EEC）を使用して web サイトを開く際に、混在したコンテンツを有効にします。 このオプションを有効にすると、[!DNL Target] プロキシサーバー経由で静的リソースを読み込む余分なオーバーヘッドを回避できます。

このオプションは、例えば次のような場合に役立ちます。

* コンテンツセキュリティポリシー（CSP）ヘッダーを使用すると、EEC が有効なプロキシサーバーを使用せずに、混在したコンテンツを読み込むことができます。
* HTTP web サイトの EEC での読み込み時間が長くなります。JavaScriptや画像などの読み込みにプロキシを使用すると、時間がかかります。

### アクティビティのフロー図でのエクスペリエンススナップショットの生成

エクスペリエンススナップショットを有効にすると、アクティビティワークフローダイアグラムでエクスペリエンスのサムネールが生成されます。スナップショットを無効にすると、一部のユーザーでパフォーマンスが向上する場合があります。

## モバイルビューポート設定

>[!NOTE]
>
>[!UICONTROL Mobile Viewport Configuration] 設定は [Target Premium](/help/main/c-intro/intro.md#premium) 機能です。


エクスペリエンスのプレビュー時に、使用するデバイスを追加できます。各デバイスにはオーディエンスが関連付けられています。

![ モバイルビューポート設定セクション ](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

「**[!UICONTROL Add]**」をクリックし、モバイルビューポートのわかりやすい名前を指定します。次に、幅と高さを指定し、目的のオペレーティングシステムを選択して「[!UICONTROL Save]」をクリックします。

モバイルビューポートの追加方法に関する情報については、[モバイルビューポート設定](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)を参照してください。

## CSS セレクター {#css}

[!DNL Target]で CSS セレクターを生成する方法を指定します。

![CSS セレクターセクション ](/help/main/administrating-target/assets/css-selectors.png)

これらのオプションを使用すると、[!DNL Target]に対してサイトの構造を指定して、コンテンツ配信により適した CSS セレクターを生成できます。デフォルトで、[!DNL Target]はページ上の要素 ID に基づいてセレクターを生成します。サイトで使用されている ID が少ない場合、または同じページ上に重複する ID が存在する場合は、クラスを使用することをお勧めします。

次のオプションのいずれかまたは両方を選択できます。

### 要素 ID を使用

複数の要素で同じ ID を使用する場合、またはページの読み込みで要素 ID が変更される場合は、このオプションの選択を解除します。

### 要素クラスを使用

デフォルトで、[!DNL Target]は要素 ID のみを使用します。ただし、[!DNL Adobe Experience Manager] で作成されたページなど、クラスを使用して要素を識別するようにページを設計している場合は、[!UICONTROL Use element classes] も選択する必要があります。

>[!NOTE]
>
>精度を確保するためにはすべて行われていますが、クラスを使用するとエラーが発生する可能性があることに注意してください。 いずれのオプションも選択しない場合も、正確性が低下します。正確性は、ID > クラス > オプション指定なしの順番です。必ずページをテストして、セレクターが正しいことを確認してください。

この設定は、アクティビティごとに上書きできます（[!UICONTROL Settings] 歯車アイコンをクリックして「[!UICONTROL CSS Selectors]」を選択します）。 この機能は、別々の設定をおこなう複数のサイトがある場合に特に役立ちます。

>[!NOTE]
>
>アクティビティごとに設定を上書きする機能は、[!UICONTROL Automated Personalization] アクティビティと [!UICONTROL Multivariate Testing] アクティビティでは使用できません。  セレクターについて詳しくは、[Visual Experience Composer で使用される要素セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md)を参照してください。

## トレーニングビデオ：アカウント環境設定（7:33） ![ 概要バッジ ](/help/main/assets/overview.png)

このビデオでは、アカウント設定に関する情報を説明します。

* [!DNL Target Standard]でのアカウント設定に関する説明

>[!NOTE]
>
>パフォーマンスを向上、新機能のリリースに要するメンテナンス時間を短縮、製品全体でのユーザーエクスペリエンスが向上するため、[!DNL Target] [!UICONTROL Administration] メニュー（以前の [!UICONTROL Setup]）のデザインが一新されました。 次のビデオの情報は、一般的には正確ですが、オプションの場所が若干異なる場合があります。更新されたビデオは間もなく投稿される予定です。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
