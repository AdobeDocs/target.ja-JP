---
keywords: visual experience composer;vec；デフォルトurl;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;cssセレクター
description: 一般的な設定、モバイルビューポート設定、CSSセレクターを指定して、Adobe TargetVisual Experience Composer(VEC)を設定する方法を説明します。
title: Visual Experience Composer(VEC)の設定方法を教えてください。
feature: Administration & Configuration
role: Administrator
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 49%

---


# Visual Experience Composerの設定

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer](VEC)を設定します。そのためには、一般的な設定、モバイルビューポート設定、CSSセレクターを指定します。

[!UICONTROL Visual Experience Composer]設定ページにアクセスするには、**[!UICONTROL 管理]**/**[!UICONTROL Visual Experience Composer]をクリックします。**

>[!NOTE]
>
>このページの設定は[!DNL Target]アカウント全体に適用されることに注意してください。

![Visual Experience Composer設定ページ](/help/administrating-target/assets/vec.png)

## 一般的な設定

Visual Experience Composerの一般設定を指定できます。

![一般設定セクション](/help/administrating-target/assets/general-settings.png)

以下の設定を使用できます。

### デフォルトURL

[!UICONTROL Visual Experience Composer] で使用されるデフォルトの URL を設定します。これは、新しいアクティビティのそれぞれに対してエクスペリエンスをセットアップするときに必ず使用される、ホームページのようなデフォルトのページです。デフォルトの URL を設定しない場合は、各アクティビティを作成するたびに URL を入力する必要があります。

### 拡張された Experience Composer を有効にする {#eec}

iframe バスティングのサイトおよび混合コンテンツを使用したサイトでの編集を許可します。一部のサイトは、拡張版と互換性がない場合があります。 元の[!UICONTROL Visual Experience Composer]に戻すには、このオプションの選択を解除します。 サイトでのアクティビティの配信はこの選択の影響を受けません。

詳しくは、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

また、[!UICONTROL 拡張Experience Composer]をアクティビティレベルで有効にすることもできます。

### 混在コンテンツの読み込み

[!UICONTROL 拡張Experience Composer](EEC)を使用してWebサイトを開く際に混合コンテンツを有効にします。 このオプションを有効にすると、[!DNL Target]プロキシサーバを介して静的なリソースを読み込む際に発生する余分なオーバーヘッドを回避できます。

このオプションは、次のような場合に役立ちます。

* コンテンツセキュリティポリシー(CSP)のヘッダーを使用すると、EECが有効なプロキシサーバーを使用せずに、混合コンテンツを読み込むことができます。
* HTTP WebサイトのEECでの読み込み時間が長くなり、JavaScriptや画像などがプロキシ経由で読み込まれるまでに時間がかかります。

### アクティビティフロー図でのエクスペリエンスのスナップショットの生成

エクスペリエンススナップショットを有効にすると、アクティビティワークフローダイアグラムでエクスペリエンスのサムネールが生成されます。スナップショットを無効にすると、一部のユーザーでパフォーマンスが向上する場合があります。

## ![プレミアム](/help/assets/premium.png) バッジモバイルビューポートの設定

エクスペリエンスのプレビュー時に、使用するデバイスを追加できます。各デバイスにはオーディエンスが関連付けられています。

![モバイルビューポート設定セクション](/help/administrating-target/assets/mobile-viewport-configuration.png)

**[!UICONTROL 追加]**&#x200B;をクリックし、モバイルビューポートの説明的な名前を指定し、幅と高さを指定し、目的のオペレーティングシステムを選択して、[!UICONTROL 保存]をクリックします。

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
>アクティビティごとの設定を上書きすることは、[!UICONTROL Automated Personalization]アクティビティと[!UICONTROL Multivariate Testing]フォルダーでは使用できません。  セレクターについて詳しくは、[Visual Experience Composer で使用される要素セレクター](/help/c-experiences/c-visual-experience-composer/vec-selectors.md)を参照してください。

## トレーニングビデオ：アカウント設定(7:33) ![概要バッジ](/help/assets/overview.png)

このビデオでは、アカウント設定に関する情報を説明します。

* [!DNL Target Standard]でのアカウント設定に関する説明

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]メニューUI（旧称[!UICONTROL セットアップ]）の設計が一新され、パフォーマンスが向上し、新機能のリリース時に必要なメンテナンス時間が短縮され、製品全体でのユーザーエクスペリエンスが向上しました。 次のビデオの情報は、一般的に正しいです。ただし、オプションが少し異なる場所にある場合もあります。 更新されたビデオは近日中に投稿されます。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
