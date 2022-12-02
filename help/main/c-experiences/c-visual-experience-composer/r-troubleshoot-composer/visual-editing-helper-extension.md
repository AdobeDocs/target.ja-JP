---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: '[!UICONTROL Visual Experience Composer]（VEC）で一部の web サイトを確実に開くことができない可能性がある理由を明らかにします。[!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、VEC 内に web サイトを確実に読み込むことができます。'
title: '[!UICONTROL Visual Editing Helper] 拡張機能の使用方法'
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: f997b6a0ea9e0cebf7b414c029971d8520f8b95f
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 100%

---

# [!UICONTROL Visual Editing Helper] 拡張機能

Google Chrome の [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、[!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer]（VEC）内に web サイトを確実に読み込んで、web エクスペリエンスを迅速に作成および QA できます。

>[!IMPORTANT]
>
>この新しい拡張機能は、以前の [Target VEC Helper ブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に代わるものです。

## VEC で一部の web サイトを確実に開くことができない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。

Chrome 用の [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能は、顧客が [!DNL Target] [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) やサードパーティ拡張機能（Requestly など）に頼るきっかけとなったサイト読み込みの問題を解決します。

## [!UICONTROL Visual Editing Helper] 拡張機能を使用するメリット

* すべての iframe バスティングヘッダー（`X-Frame-Options` や `Content-Security-Policy` など）は、web サイトから暗黙的に削除されます。複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target] at.js ライブラリがまだ含まれていない場合は、この拡張機能を使用してライブラリを挿入することにより、web サイトのエクスペリエンスを作成できます。その後に、アクティビティを作成し、プレビューリンクを使用してアクティビティの QA を実行できます。

[拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) を使用すると、拡張機能では at.js は挿入されませんが、SameSite Cookie 機能は引き続き存在します。Web ページに at.js を挿入するには、EEC をオフにします。

* [モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)は、[!UICONTROL 拡張 Experience Composer]（EEC）がなくてもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## [!UICONTROL Visual Editing Helper] ブラウザー拡張機能の取得とインストール

1. Chrome web ストアの [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}に移動します。
1. **[!UICONTROL Chrome に追加]**／**[!UICONTROL 拡張機能を追加]**&#x200B;をクリックします。
1. [!DNL Target] で VEC を開きます。
1. この拡張機能を使用するには、VEC または QA モードで、Chrome ブラウザーのツールバーにある「[!UICONTROL Visual Editing Helper]」ブラウザー拡張機能アイコン（![Visual Editing 拡張機能アイコン](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png)）をクリックします。

   [!UICONTROL Target] VEC で web サイトを開くと、[!UICONTROL Visual Editing Helper] が自動的に有効になり、オーサリング機能が強化されます。この拡張機能には、条件付き設定はありません。この拡張機能では、SameSite Cookie の設定を含むすべての設定を自動的に処理します。

   `SameSite=None` 属性に関するブラウザーの修正について詳しくは、「Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？」の節を参照してください。[Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。

## メモ

* [!DNL Target] の場合、この拡張機能が、[!DNL Target] UI の[!UICONTROL 管理]／[!UICONTROL 実装]から利用可能な最新版の at.js を読み込み、at.js がオーサリングライブラリをダウンロードします。
* [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)でこの拡張機能を使用して at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ [!DNL Adobe Experience Cloud] 組織に対して認証されている必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * 読み込みに失敗した VEC を使用して web サイトを読み込もうとすると、[!UICONTROL Visual Editing Helper] ブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js または alloy.js が web サイトにまだ実装されていない場合、この拡張機能のインストールを勧めるメッセージが VEC に表示されます。
* 新しい拡張機能を使用してから[古い拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に戻り、[!DNL Target] が web サイトの読み込みに失敗した場合は、すべてのブラウザー データを消去し、新しい拡張機能を無効にします。
