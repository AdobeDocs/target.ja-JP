---
keywords: visual experience composer;vec；デフォルト URL；拡張 experience composer;eec；混在コンテンツ；エクスペリエンススナップショット；モバイルビューポート；css;css セレクター
description: Adobe [!DNL Target] Visual Experience Composer(VEC) で、一般設定、モバイルビューポート設定および CSS セレクターを指定します。
title: Visual Experience Composer(VEC) の設定方法を教えてください。
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 58%

---

# Visual Experience Composer の設定

の設定 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) の一般設定、モバイルビューポート設定および CSS セレクターを指定する。

次の手順で [!UICONTROL Visual Experience Composer] 設定ページで、「 **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer].**

>[!NOTE]
>
>このページの設定は、 [!DNL Target] アカウント

![Visual Experience Composer の設定ページ](/help/main/administrating-target/assets/vec.png)

## 一般的な設定

Visual Experience Composer に対して一般的な設定を指定できます。

![「一般設定」セクション](/help/main/administrating-target/assets/general-settings.png)

以下の設定を使用できます。

### デフォルトの URL

[!UICONTROL Visual Experience Composer] で使用されるデフォルトの URL を設定します。これは、新しいアクティビティのそれぞれに対してエクスペリエンスをセットアップするときに必ず使用される、ホームページのようなデフォルトのページです。デフォルトの URL を設定しない場合は、各アクティビティを作成するたびに URL を入力する必要があります。

### 拡張された Experience Composer を有効にする {#eec}

iframe バスティングのサイトおよび混合コンテンツを使用したサイトでの編集を許可します。一部のサイトは、拡張バージョンと互換性がない場合があります。 元のアセットに戻すには、このオプションの選択を解除します [!UICONTROL Visual Experience Composer]. サイトでのアクティビティの配信はこの選択の影響を受けません。

詳しくは、[Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

また、 [!UICONTROL 拡張 Experience Composer] （アクティビティレベル）。

### 混在コンテンツの読み込み

Web サイトを開く際に、 [!UICONTROL 拡張 Experience Composer] (EEC)。 このオプションを有効にすると、を介して静的リソースを読み込む余分なオーバーヘッドを回避できます [!DNL Target] プロキシサーバー。

このオプションは、次のような場合に便利です。

* EEC を有効にしたプロキシサーバーを使用しなくても、コンテンツセキュリティポリシー (CSP) ヘッダーを使用して混合コンテンツを読み込むことができます。
* HTTP Web サイトは EEC の読み込み時間の増加に直面し、JavaScript や画像などがプロキシ経由の読み込みに時間がかかります。

### アクティビティフロー図でエクスペリエンスのスナップショットを生成

エクスペリエンススナップショットを有効にすると、アクティビティワークフローダイアグラムでエクスペリエンスのサムネールが生成されます。スナップショットを無効にすると、一部のユーザーでパフォーマンスが向上する場合があります。

## ![Premium バッジ](/help/main/assets/premium.png) モバイルビューポート設定

エクスペリエンスのプレビュー時に、使用するデバイスを追加できます。各デバイスにはオーディエンスが関連付けられています。

![モバイルビューポート設定セクション](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

クリック **[!UICONTROL 追加]**、モバイルビューポートのわかりやすい名前、幅と高さを指定し、目的のオペレーティングシステムを選択して、「 [!UICONTROL 保存].

モバイルビューポートの追加方法に関する情報については、[モバイルビューポート設定](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)を参照してください。

## CSS セレクター {#css}

[!DNL Target]で CSS セレクターを生成する方法を指定します。

![CSS セレクターの節](/help/main/administrating-target/assets/css-selectors.png)

これらのオプションを使用すると、[!DNL Target]に対してサイトの構造を指定して、コンテンツ配信により適した CSS セレクターを生成できます。デフォルトで、[!DNL Target]はページ上の要素 ID に基づいてセレクターを生成します。サイトで使用されている ID が少ない場合、または同じページ上に重複する ID が存在する場合は、クラスを使用することをお勧めします。

次のオプションのいずれかまたは両方を選択できます。

### 要素 ID を使用

複数の要素で同じ ID を使用する場合、またはページの読み込みで要素 ID が変更される場合は、このオプションの選択を解除します。

### 要素クラスを使用

デフォルトで、[!DNL Target]は要素 ID のみを使用します。ただし、ページでクラスを使用して要素を指定している場合は（[!DNL Adobe Experience Manager] を使用して作成されたページなど）、「[!UICONTROL 要素クラスを使用]」も選択する必要があります。

>[!NOTE]
>
>すべての機能は正確性を保つために実行されていますが、クラスを使用するとエラーが発生する場合があることに注意してください。 いずれのオプションも選択しない場合も、正確性が低下します。正確性は、ID > クラス > オプション指定なしの順番です。必ずページをテストして、セレクターが正しいことを確認してください。

アクティビティごとにこの設定を上書きできます（[!UICONTROL 設定]歯車アイコンをクリックして、「[!UICONTROL CSS セレクター]」を選択します）。この機能は、別々の設定をおこなう複数のサイトがある場合に特に役立ちます。

>[!NOTE]
>
>アクティビティごとの設定の上書きは、では使用できません。 [!UICONTROL Automated Personalization] および [!UICONTROL Multivariate Testing] アクティビティ。  セレクターについて詳しくは、[Visual Experience Composer で使用される要素セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md)を参照してください。

## トレーニングビデオ：アカウント設定(7:33) ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、アカウント設定に関する情報を説明します。

* [!DNL Target Standard]でのアカウント設定に関する説明

>[!NOTE]
>
>パフォーマンスを向上、新機能のリリースに要するメンテナンス時間を短縮、製品全体でのユーザーエクスペリエンスが向上するため、[!DNL Target] [!UICONTROL 管理]メニュー（以前の[!UICONTROL 設定]）のデザインが一新されました。次のビデオの情報は、一般的には正確ですが、オプションの場所が若干異なる場合があります。更新されたビデオは間もなく投稿される予定です。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
