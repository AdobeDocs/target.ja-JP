---
keywords: vec;visual experience composer; vec;iframe；拡張機能；ブラウザー；faq
description: で一部の Web サイトを確実に開けない理由を見つける [!UICONTROL Visual Experience Composer] (VEC) を参照してください。 The [!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、VEC 内で確実に web サイトを読み込むことができます。
title: 使用方法 [!UICONTROL Visual Editing Helper] 拡張？
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 5df9ba6eb249dfc690279177ecb5936aaefa7bdd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 67%

---

# [!UICONTROL Visual Editing Helper] 拡張

The [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能 [!DNL Google Chrome] を使用すると、 [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) を使用して、Web エクスペリエンスを迅速に作成および QA できます。

>[!IMPORTANT]
>
>この新しい拡張機能は、以前の [Target VEC Helper ブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に代わるものです。この記事の上部にある重要なメモを参照してください。

## VEC で一部の web サイトを確実に開くことができない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。

The [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] お客様が現在依存しているサイトの読み込みの問題を解決するブラウザー拡張機能 [!DNL Target] [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) または Requestly などのサードパーティの拡張機能を使用できます。

## を使用するメリット [!UICONTROL Visual Editing Helper] 拡張

* すべての iframe バスティングヘッダー（`X-Frame-Options` や `Content-Security-Policy` など）は、web サイトから暗黙的に削除されます。複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target] at.js ライブラリがまだ含まれていない場合は、この拡張機能を使用してライブラリを挿入することにより、web サイトのエクスペリエンスを作成できます。その後に、アクティビティを作成し、プレビューリンクを使用してアクティビティの QA を実行できます。

  [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) を使用すると、拡張機能では at.js は挿入されませんが、SameSite Cookie 機能は引き続き存在します。Web ページに at.js を挿入するには、EEC をオフにします。

* [モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) は、 [!UICONTROL Enhanced Experience Composer] (EEC)。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## の取得とインストール [!UICONTROL Visual Editing Helper] ブラウザー拡張

1. 次に移動： [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] Chrome Web Store のブラウザー拡張機能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. クリック **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. [!DNL Target] で VEC を開きます。
1. 拡張機能を使用するには、 [!UICONTROL Visual Editing Helper] ブラウザー拡張アイコン ( ![ビジュアル編集拡張機能アイコン](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) を Chrome ブラウザーのツールバーに表示されるか、VEC または QA モードで表示されるかを確認します。

   The [!UICONTROL Visual Editing Helper] は、 [!UICONTROL Target] オーサリングを強化する VEC。 この拡張機能には、条件付き設定はありません。この拡張機能では、SameSite Cookie の設定を含むすべての設定を自動的に処理します。

   `SameSite=None` 属性に関するブラウザーの修正について詳しくは、「Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？」の節を参照してください。[Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。

## メモ

* の場合 [!DNL Target]の場合、拡張機能は、 [!DNL Target] の UI [!UICONTROL Administration] > [!UICONTROL Implementation] および at.js はオーサリングライブラリをダウンロードします。
* [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)でこの拡張機能を使用して at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ [!DNL Adobe Experience Cloud] 組織に対して認証されている必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、 [!UICONTROL Visual Editing Helper] ブラウザー拡張機能。
   * at.js または alloy.js が web サイトにまだ実装されていない場合、この拡張機能のインストールを勧めるメッセージが VEC に表示されます。
* 新しい拡張機能を使用してから[古い拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に戻り、[!DNL Target] が web サイトの読み込みに失敗した場合は、すべてのブラウザー データを消去し、新しい拡張機能を無効にします。

## よくある質問

### 拡張機能がアクティブな場合、の外部で使用された場合は何も実行しませんか。 [!DNL Adobe Target] または [!UICONTROL Adobe Journey Optimizer] (AJO)?

この拡張機能は、対象の web サイトが [!DNL Adobe] 製品（[!DNL Target]、[!DNL AJO]）の iFrame 内に読み込まれた場合にのみアクティブになります。このフロー以外では、拡張機能はヘッダーを追加、削除、変更せずに、web サイト内にコードを挿入しようとしません。

### 拡張機能が [!DNL Adobe Target] VEC でアクティブな場合、何を行いますか？

Web サイトが [!DNL Adobe] 製品（[!DNL Target]、[!DNL AJO]）の iFrame 内に読み込まれると、拡張機能は web サイトにコード（拡張機能にバンドルされている）を挿入し、[!DNL Adobe] CDN からヘルパーファイルをダウンロードしてビジュアルオーサリングを有効にします。
