---
keywords: vec;visual experience composer; vec;iframe;extension;browser;faq
description: で一部の web サイトを確実に開くことができない可能性がある理由を明らかにします [!UICONTROL Visual Experience Composer] （VEC）。 この [!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、VEC 内に web サイトを確実に読み込むことができます。
title: の使用方法 [!UICONTROL Visual Editing Helper] 延長？
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 8edae6a197a3ac82b85fcce4d99c8b0d5f45c712
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 64%

---

# [!UICONTROL Visual Editing Helper] 拡張子

この [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] のブラウザー拡張機能 [!DNL Google Chrome] では、内に web サイトを確実に読み込むことができます [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）を使用して、web エクスペリエンスを迅速に作成および QA できます。

>[!IMPORTANT]
>
>この新しい拡張機能は、以前の [Target VEC Helper ブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に代わるものです。この記事の上部にある重要なメモを参照してください。 Manifest v3 のセキュリティ強化により、 [!DNL Adobe] で web サイトのビジュアル作成を続行するには、この新しい拡張機能をダウンロードする必要があります [!DNL Target].

## VEC で一部の web サイトを確実に開くことができない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。

この [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] のブラウザー拡張機能は、顧客がに依存するようになった、サイト読み込みの問題を解決します [!DNL Target] [Experience Composer の強化](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) またはサードパーティの拡張機能（Requestly など）。

## を使用するメリット [!UICONTROL Visual Editing Helper] 拡張子

* すべての iframe バスティングヘッダー（`X-Frame-Options` や `Content-Security-Policy` など）は、web サイトから暗黙的に削除されます。複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target] at.js ライブラリがまだ含まれていない場合は、この拡張機能を使用してライブラリを挿入することにより、web サイトのエクスペリエンスを作成できます。その後に、アクティビティを作成し、プレビューリンクを使用してアクティビティの QA を実行できます。

  [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) を使用すると、拡張機能では at.js は挿入されませんが、SameSite Cookie 機能は引き続き存在します。Web ページに at.js を挿入するには、EEC をオフにします。

* [モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) がサポートされていない [!UICONTROL Enhanced Experience Composer] （EEC）。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## の取得とインストール [!UICONTROL Visual Editing Helper] ブラウザー拡張機能

1. に移動します。 [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] chrome ウェブストアのブラウザー拡張機能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. クリック **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. [!DNL Target] で VEC を開きます。
1. 拡張機能を使用するには、 [!UICONTROL Visual Editing Helper] ブラウザー拡張機能アイコン（ ![Visual Editing 拡張機能アイコン](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ）、VEC または QA モードの場合は、Chrome ブラウザーのツールバーを使用します。

   この [!UICONTROL Visual Editing Helper] で web サイトを開くと、が自動的に有効になります。 [!UICONTROL Target] VEC でオーサリングを強化。 この拡張機能には、条件付き設定はありません。この拡張機能では、SameSite Cookie の設定を含むすべての設定を自動的に処理します。

   `SameSite=None` 属性に関するブラウザーの修正について詳しくは、「Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？」の節を参照してください。[Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。

## メモ

* の場合 [!DNL Target]：この拡張機能は、から利用可能な最新バージョンの at.js を読み込みます。 [!DNL Target] の UI [!UICONTROL Administration] > [!UICONTROL Implementation] さらに at.js がオーサリングライブラリをダウンロードします。
* [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)でこの拡張機能を使用して at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ [!DNL Adobe Experience Cloud] 組織に対して認証されている必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * 読み込みに失敗した VEC を使用して web サイトを読み込もうとすると、 [!UICONTROL Visual Editing Helper] ブラウザー拡張機能。
   * at.js または alloy.js が web サイトにまだ実装されていない場合、この拡張機能のインストールを勧めるメッセージが VEC に表示されます。
* 新しい拡張機能を使用してから[古い拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に戻り、[!DNL Target] が web サイトの読み込みに失敗した場合は、すべてのブラウザー データを消去し、新しい拡張機能を無効にします。

## よくある質問

### 拡張機能がアクティブな場合、以外で使用したときに何も実行しません [!DNL Adobe Target] または [!UICONTROL Adobe Journey Optimizer] （AJO）?

この拡張機能は、対象の web サイトが [!DNL Adobe] 製品（[!DNL Target]、[!DNL AJO]）の iFrame 内に読み込まれた場合にのみアクティブになります。このフロー以外では、拡張機能はヘッダーを追加、削除、変更せずに、web サイト内にコードを挿入しようとしません。

### 拡張機能が [!DNL Adobe Target] VEC でアクティブな場合、何を行いますか？

Web サイトが [!DNL Adobe] 製品（[!DNL Target]、[!DNL AJO]）の iFrame 内に読み込まれると、拡張機能は web サイトにコード（拡張機能にバンドルされている）を挿入し、[!DNL Adobe] CDN からヘルパーファイルをダウンロードしてビジュアルオーサリングを有効にします。
