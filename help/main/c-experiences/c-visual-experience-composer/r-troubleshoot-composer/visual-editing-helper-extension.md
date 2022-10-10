---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: で一部の Web サイトを確実に開けない理由を見つける [!UICONTROL Visual Experience Composer] (VEC) を参照してください。 この [!UICONTROL ビジュアル編集ヘルパー] ブラウザー拡張機能を使用すると、VEC 内で確実に web サイトを読み込むことができます。
title: 使用方法 [!UICONTROL ビジュアル編集ヘルパー] 拡張？
feature: Visual Experience Composer (VEC)
source-git-commit: 6fd90da68bfe9a78202e9289dc639d41e3daa48f
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 25%

---

# [!UICONTROL ビジュアル編集ヘルパー] 拡張

この [!DNL Adobe Experience Cloud] [!UICONTROL ビジュアル編集ヘルパー] Google Chrome のブラウザー拡張機能を使用すると、 [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) を使用して、Web エクスペリエンスを迅速に作成および QA できます。

>[!IMPORTANT]
>
>この新しい拡張機能は、以前の [Target VEC ヘルパーブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

## VEC で一部の Web サイトを確実に開けない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* お客様の QA またはステージサイトは、外部では使用できません（サイトは内部）。

この [!DNL Adobe Experience Cloud] [!UICONTROL ビジュアル編集ヘルパー] Chrome 用ブラウザー拡張機能は、顧客が [!DNL Target] [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) または Requestly などのサードパーティの拡張機能を使用できます。

## を使用するメリット [!UICONTROL ビジュアル編集ヘルパー] 拡張

* すべての iframe バスティングヘッダー（例： ） `X-Frame-Options` および `Content-Security-Policy`は、Web サイトから暗黙的に削除されます。 複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target]at.js ライブラリがまだ含まれていない場合は、拡張機能を使用してライブラリを挿入することにより、Web サイトのエクスペリエンスを作成できます。その後に、プレビューリンクを使用してアクティビティを作成し、QA を実行できます。

の使用 [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)の場合、拡張機能は at.js を挿入しませんが、SameSite Cookie 機能は引き続き存在します。 Web ページに at.js を挿入するには、EEC をオフにします。

* [モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) が [!UICONTROL 拡張 Experience Composer] (EEC)。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## の取得とインストール [!UICONTROL ビジュアル編集ヘルパー] ブラウザー拡張

1. 次に移動： [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] Chrome Web Store のブラウザー拡張機能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}。
1. クリック **[!UICONTROL Chrome に追加]** > **[!UICONTROL 拡張機能を追加]**.
1. で VEC を開きます。 [!DNL Target].
1. 拡張機能を使用するには、 [!UICONTROL ビジュアル編集ヘルパー] ブラウザー拡張アイコン ( ![ビジュアル編集拡張機能アイコン](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) を Chrome ブラウザーのツールバーに表示されるか、VEC または QA モードで表示されるかを確認します。

   この [!UICONTROL ビジュアル編集ヘルパー] は、 [!UICONTROL ターゲット] オーサリングを強化する VEC 拡張機能には条件付き設定はありません。 拡張機能は、SameSite cookie 設定を含むすべての設定を自動的に処理します。

   詳しくは、 `SameSite=None` 属性ブラウザーの修正については、「最近発表されたGoogle Chrome SameSite cookie の実施ポリシーが VEC および EEC に与える影響」を参照してください。 [Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。

## メモ

* の場合 [!DNL Target]の場合、拡張機能は、 [!DNL Target] の UI [!UICONTROL 管理] > [!UICONTROL 実装] および at.js はオーサリングライブラリをダウンロードします。
* 拡張機能を使用して [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)で at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは同じ認証を受ける必要があります [!DNL Adobe Experience Cloud] アクティビティを作成した組織。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、 [!UICONTROL ビジュアル編集ヘルパー] ブラウザー拡張機能。
   * at.js または alloy.js が Web サイトにまだ実装されていない場合、拡張機能のインストールを勧めるメッセージが VEC に表示されます。
* 新しい拡張機能を使用しようとした場合は、 [古い拡張子](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) および [!DNL Target] web サイトの読み込みに失敗し、すべてのブラウザーデータを消去して、新しい拡張機能を無効にします。




