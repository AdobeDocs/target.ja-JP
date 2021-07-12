---
keywords: visual experience composer;vec；デフォルトURL；拡張experience composer;eec；混合コンテンツ；エクスペリエンススナップショット；モバイルビューポート；css;cssセレクター
description: Adobe [!DNL Target] Visual Experience Composer(VEC)の一般的な設定、モバイルビューポート設定およびCSSセレクターを指定して、セレクターを設定する方法について説明します。
title: Visual Experience Composer(VEC)の設定方法を教えてください。
feature: 管理と設定
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 50%

---

# Visual Experience Composer の設定

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer](VEC)を設定するには、一般設定、モバイルビューポート設定およびCSSセレクターを指定します。

[!UICONTROL Visual Experience Composer]設定ページにアクセスするには、**[!UICONTROL 管理]** / **[!UICONTROL Visual Experience Composer].**&#x200B;をクリックします。

>[!NOTE]
>
>このページの設定は[!DNL Target]アカウント全体に適用されることに注意してください。

![Visual Experience Composerの設定ページ](/help/administrating-target/assets/vec.png)

## 一般的な設定

Visual Experience Composerに対して一般的な設定を指定できます。

![「一般設定」セクション](/help/administrating-target/assets/general-settings.png)

以下の設定を使用できます。

### デフォルトURL

[!UICONTROL Visual Experience Composer] で使用されるデフォルトの URL を設定します。これは、新しいアクティビティのそれぞれに対してエクスペリエンスをセットアップするときに必ず使用される、ホームページのようなデフォルトのページです。デフォルトの URL を設定しない場合は、各アクティビティを作成するたびに URL を入力する必要があります。

### 拡張された Experience Composer を有効にする {#eec}

iframe バスティングのサイトおよび混合コンテンツを使用したサイトでの編集を許可します。一部のサイトは、拡張版と互換性がない場合があります。 元の[!UICONTROL Visual Experience Composer]に戻す場合は、このオプションの選択を解除します。 サイトでのアクティビティの配信はこの選択の影響を受けません。

詳しくは、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

また、アクティビティレベルで[!UICONTROL 拡張Experience Composer]を有効にすることもできます。

### 混在コンテンツの読み込み

[!UICONTROL 拡張Experience Composer](EEC)を使用してWebサイトを開く際に混合コンテンツを有効にします。 このオプションを有効にすると、[!DNL Target]プロキシサーバーを介して静的リソースを読み込む余分なオーバーヘッドを回避できます。

このオプションは、次の場合に便利です。

* EECを有効にしたプロキシサーバーを使用しなくても、コンテンツセキュリティポリシー(CSP)ヘッダーを使用して混合コンテンツを読み込むことができます。
* HTTP Webサイトは、EECの読み込み時間の増加に直面し、JavaScriptや画像などがプロキシ経由での読み込みに時間がかかります。

### アクティビティフロー図でエクスペリエンスのスナップショットを生成する

エクスペリエンススナップショットを有効にすると、アクティビティワークフローダイアグラムでエクスペリエンスのサムネールが生成されます。スナップショットを無効にすると、一部のユーザーでパフォーマンスが向上する場合があります。

## ![Premium badgeモバ](/help/assets/premium.png) イルビューポート設定

エクスペリエンスのプレビュー時に、使用するデバイスを追加できます。各デバイスにはオーディエンスが関連付けられています。

![モバイルビューポート設定セクション](/help/administrating-target/assets/mobile-viewport-configuration.png)

「**[!UICONTROL 追加]**」をクリックし、モバイルビューポートのわかりやすい名前を指定し、幅と高さを指定して、目的のオペレーティングシステムを選択してから、「[!UICONTROL 保存]」をクリックします。

モバイルビューポートの追加方法に関する情報については、[モバイルビューポート設定](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)を参照してください。

## CSS セレクター {#css}

[!DNL Target]で CSS セレクターを生成する方法を指定します。

![CSSセレクターの節](/help/administrating-target/assets/css-selectors.png)

これらのオプションを使用すると、[!DNL Target]に対してサイトの構造を指定して、コンテンツ配信により適した CSS セレクターを生成できます。デフォルトで、[!DNL Target]はページ上の要素 ID に基づいてセレクターを生成します。サイトで使用されている ID が少ない場合、または同じページ上に重複する ID が存在する場合は、クラスを使用することをお勧めします。

次のオプションのいずれかまたは両方を選択できます。

### 要素 ID を使用

複数の要素で同じ ID を使用する場合、またはページの読み込みで要素 ID が変更される場合は、このオプションの選択を解除します。

### 要素クラスを使用

デフォルトで、[!DNL Target]は要素 ID のみを使用します。ただし、ページでクラスを使用して要素を指定している場合は（[!DNL Adobe Experience Manager] を使用して作成されたページなど）、「[!UICONTROL 要素クラスを使用]」も選択する必要があります。

>[!NOTE]
>
>すべての処理は正確性を確保するためにおこなわれていますが、クラスを使用するとエラーが発生する可能性があることに注意してください。 いずれのオプションも選択しない場合も、正確性が低下します。正確性は、ID > クラス > オプション指定なしの順番です。必ずページをテストして、セレクターが正しいことを確認してください。

アクティビティごとにこの設定を上書きできます（[!UICONTROL 設定]歯車アイコンをクリックして、「[!UICONTROL CSS セレクター]」を選択します）。この機能は、別々の設定をおこなう複数のサイトがある場合に特に役立ちます。

>[!NOTE]
>
>アクティビティごとの設定の上書きは、[!UICONTROL Automated Personalization]および[!UICONTROL Multivariate Testing]アクティビティでは使用できません。  セレクターについて詳しくは、[Visual Experience Composer で使用される要素セレクター](/help/c-experiences/c-visual-experience-composer/vec-selectors.md)を参照してください。

## トレーニングビデオ：アカウントの環境設定(7:33) ![概要バッジ](/help/assets/overview.png)

このビデオでは、アカウント設定に関する情報を説明します。

* [!DNL Target Standard]でのアカウント設定に関する説明

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]メニューUI（旧称[!UICONTROL セットアップ]）が再設計され、パフォーマンスの向上、新機能のリリースに要するメンテナンス時間の短縮、製品全体でのユーザーエクスペリエンスの向上が実現しました。 次のビデオの情報は、一般に正しい。ただし、オプションの位置は若干異なる場合があります。 更新されたビデオは近日中に投稿されます。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
