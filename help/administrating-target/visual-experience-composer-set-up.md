---
keywords: visual experience composer;vec;default url;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;css selectors
description: 一般的な設定、モバイルビューポート設定、CSSセレクターを指定して、Adobe TargetVisual Experience Composer(VEC)を設定します。
title: Visual Experience Composerの設定
feature: null
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 51%

---


# Visual Experience Composerの設定

一般的な設定、モバイルビューポートの設定およびCSSセレクターを指定して、 [!DNL Adobe Target] Visual Experience Composer  (VEC)を設定します。

Visual Experience Composer [!UICONTROL 設定ページにアクセスするには、] 管理 **[!UICONTROL /]** Visual Experience Composer **をクリックします。**

>[!NOTE]
>
>このページの設定はアカウント全体に適用されることに注意してくだ [!DNL Target] さい。

![Visual Experience Composer設定ページ](/help/administrating-target/assets/vec.png)

## 一般的な設定

Visual Experience Composerの一般設定を指定できます。

![一般設定セクション](/help/administrating-target/assets/general-settings.png)

以下の設定を使用できます。

### デフォルトURL

[!UICONTROL Visual Experience Composer] で使用されるデフォルトの URL を設定します。これは、新しいアクティビティのそれぞれに対してエクスペリエンスをセットアップするときに必ず使用される、ホームページのようなデフォルトのページです。デフォルトの URL を設定しない場合は、各アクティビティを作成するたびに URL を入力する必要があります。

### 拡張された Experience Composer を有効にする

iframe バスティングのサイトおよび混合コンテンツを使用したサイトでの編集を許可します。一部のサイトは、拡張版と互換性がない場合があります。 Deselect this option to revert to the original [!UICONTROL Visual Experience Composer]. サイトでのアクティビティの配信はこの選択の影響を受けません。

詳しくは、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

You can also enable the [!UICONTROL Enhanced Experience Composer] at the activity level.

### 混在コンテンツの読み込み

[!UICONTROL 拡張Experience Composer] (EEC)を使用してWebサイトを開く際に混合コンテンツを有効にします。 Enabling this option avoids the extra overhead of loading static resources via [!DNL Target] proxy servers.

このオプションは、次のような場合に役立ちます。

* コンテンツセキュリティポリシー(CSP)のヘッダーを使用すると、EECが有効なプロキシサーバーを使用せずに、混合コンテンツを読み込むことができます。
* HTTP WebサイトのEECでの読み込み時間が長くなり、JavaScriptや画像などがプロキシ経由で読み込まれるまでに時間がかかります。

### アクティビティフロー図でのエクスペリエンスのスナップショットの生成

エクスペリエンススナップショットを有効にすると、アクティビティワークフローダイアグラムでエクスペリエンスのサムネールが生成されます。スナップショットを無効にすると、一部のユーザーでパフォーマンスが向上する場合があります。

## ![プレミアムバッジ](/help/assets/premium.png) — モバイルビューポートの設定

エクスペリエンスのプレビュー時に、使用するデバイスを追加できます。各デバイスにはオーディエンスが関連付けられています。

![モバイルビューポート設定セクション](/help/administrating-target/assets/mobile-viewport-configuration.png)

Click **[!UICONTROL Add]**, specify a descriptive name for the mobile viewport, specify the width and height, select the desired operating system, then click [!UICONTROL Save].

モバイルビューポートの追加方法に関する情報については、[モバイルビューポート設定](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)を参照してください。

## CSS セレクター {#css}

[!DNL Target]で CSS セレクターを生成する方法を指定します。

![CSSセレクターセクション](/help/administrating-target/assets/css-selectors.png)

これらのオプションを使用すると、[!DNL Target]に対してサイトの構造を指定して、コンテンツ配信により適した CSS セレクターを生成できます。デフォルトで、[!DNL Target]はページ上の要素 ID に基づいてセレクターを生成します。サイトで使用されている ID が少ない場合、または同じページ上に重複する ID が存在する場合は、クラスを使用することをお勧めします。

次のオプションのいずれかまたは両方を選択できます。

### 要素 ID を使用

複数の要素で同じ ID を使用する場合、またはページの読み込みで要素 ID が変更される場合は、このオプションの選択を解除します。

### 要素クラスを使用

デフォルトで、[!DNL Target]は要素 ID のみを使用します。ただし、ページでクラスを使用して要素を指定している場合は（[!DNL Adobe Experience Manager] を使用して作成されたページなど）、「[!UICONTROL 要素クラスを使用]」も選択する必要があります。

>[!NOTE]
>
>すべての処理は正確性を確保するために行われていますが、クラスを使用するとエラーが発生する可能性があることに注意してください。 いずれのオプションも選択しない場合も、正確性が低下します。正確性は、ID > クラス > オプション指定なしの順番です。必ずページをテストして、セレクターが正しいことを確認してください。

アクティビティごとにこの設定を上書きできます（[!UICONTROL 設定]歯車アイコンをクリックして、「[!UICONTROL CSS セレクター]」を選択します）。この機能は、別々の設定をおこなう複数のサイトがある場合に特に役立ちます。

>[!NOTE]
>
>Overriding the setting per activity is not available in [!UICONTROL Automated Personalization] and [!UICONTROL Multivariate Testing] activities.  セレクターについて詳しくは、[Visual Experience Composer で使用される要素セレクター](/help/c-experiences/c-visual-experience-composer/vec-selectors.md)を参照してください。

## トレーニングビデオ：アカウント設定(7:33) ![概要バッジ](/help/assets/overview.png)

このビデオでは、アカウント設定に関する情報を説明します。

* [!DNL Target Standard]でのアカウント設定に関する説明

>[!NOTE]
>
>パフォーマンスを向上し、新機能のリリース時に必要なメンテナンス時間を短縮し、製品全体でのユーザー操作性を向上させるために、 [!DNL Target] 管理 [!UICONTROL メニューUI(旧称] セットアップ )が再設計されました。 次のビデオの情報は、一般的に正しいです。ただし、オプションが少し異なる場所にある場合もあります。 更新されたビデオは近日中に投稿されます。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
