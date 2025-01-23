---
keywords: vec;visual experience composer; vec;iframe;extension;browser;faq
description: '[!UICONTROL Visual Experience Composer]（VEC）で一部の web サイトを確実に開くことができない理由を明らかにします。[!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、VEC 内に web サイトを確実に読み込むことができます。'
title: '[!UICONTROL Visual Editing Helper] 拡張機能の使用方法'
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: c41580bcbecf2eb2c14f13ce8e66e854c655d059
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 100%

---

# [!UICONTROL Visual Editing Helper] 拡張機能

[!DNL Google Chrome] の [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、[!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer]（VEC）内に web サイトを確実に読み込んで、web エクスペリエンスを迅速に作成し、QA を実行できます。

>[!IMPORTANT]
>
>* この新しい拡張機能は、以前の [Target VEC Helper ブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に代わるものです。この記事の上部にある重要なメモを参照してください。Manifest v3 のセキュリティ強化のため、[!DNL Target] では、[!DNL Adobe] で web サイトを視覚的に引き続き作成するために、この新しい拡張機能をダウンロードする必要があります。

## VEC で一部の web サイトを確実に開くことができない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。

[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能は、お客様が [!DNL Target] [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) またはサードパーティ拡張機能（Requestly など）に依存するようになったサイトの読み込みの問題を解決します。

## [!UICONTROL Visual Editing Helper] 拡張機能を使用する利点

* すべての iframe バスティングヘッダー（`X-Frame-Options` や `Content-Security-Policy` など）は、web サイトから暗黙的に削除されます。複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target] at.js ライブラリがまだ含まれていない場合は、この拡張機能を使用してライブラリを挿入することにより、web サイトのエクスペリエンスを作成できます。その後に、アクティビティを作成し、プレビューリンクを使用してアクティビティの QA を実行できます。

  [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) を使用すると、拡張機能では at.js は挿入されませんが、SameSite Cookie 機能は引き続き存在します。Web ページに at.js を挿入するには、EEC をオフにします。

* [モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)は、[!UICONTROL Enhanced Experience Composer]（EEC）がなくてもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## [!UICONTROL Visual Editing Helper] ブラウザー拡張機能の取得とインストール

1. [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] Chrome web ストアのブラウザー拡張機能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}に移動します。
1. **[!UICONTROL Add to Chrome]**／**[!UICONTROL Add Extension]**&#x200B;をクリックします。
1. [!DNL Target] で VEC を開きます。
1. この拡張機能を使用するには、VEC または QA モードで、Chrome ブラウザーのツールバーにある「[!UICONTROL Visual Editing Helper]」ブラウザー拡張機能アイコン（![Visual Editing 拡張機能アイコン](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png)）をクリックします。

   [!UICONTROL Target] VEC で web サイトを開くと、[!UICONTROL Visual Editing Helper] が自動的に有効になり、オーサリング機能が強化されます。この拡張機能には、条件付き設定はありません。この拡張機能では、SameSite Cookie の設定を含むすべての設定を自動的に処理します。

   `SameSite=None` 属性に関するブラウザーの修正について詳しくは、「Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？」の節を参照してください。[Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。

## メモ

* [!DNL Target] の場合、この拡張機能が、[!DNL Target] UI の [!UICONTROL Administration]／[!UICONTROL Implementation] から利用可能な最新版の at.js を読み込み、at.js がオーサリングライブラリをダウンロードします。
* [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)でこの拡張機能を使用して at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ [!DNL Adobe Experience Cloud] 組織に対して認証されている必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * 読み込みに失敗した VEC を使用して web サイトを読み込もうとすると、[!UICONTROL Visual Editing Helper] ブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js または alloy.js が web サイトにまだ実装されていない場合、この拡張機能のインストールを勧めるメッセージが VEC に表示されます。
* 新しい拡張機能を使用してから[古い拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に戻り、[!DNL Target] が web サイトの読み込みに失敗した場合は、すべてのブラウザー データを消去し、新しい拡張機能を無効にします。

## よくある質問

### 拡張機能がアクティブな場合、[!DNL Adobe Target] または [!UICONTROL Adobe Journey Optimizer]（AJO）以外で使用した際に何か作業を行いますか？

この拡張機能は、対象の web サイトが [!DNL Adobe] 製品（[!DNL Target]、[!DNL AJO]）の iFrame 内に読み込まれた場合にのみアクティブになります。このフロー以外では、拡張機能はヘッダーを追加、削除、変更せずに、web サイト内にコードを挿入しようとしません。

### 拡張機能が [!DNL Adobe Target] VEC でアクティブな場合、何を行いますか？

Web サイトが [!DNL Adobe] 製品（[!DNL Target]、[!DNL AJO]）の iFrame 内に読み込まれると、拡張機能は web サイトにコード（拡張機能にバンドルされている）を挿入し、[!DNL Adobe] CDN からヘルパーファイルをダウンロードしてビジュアルオーサリングを有効にします。
