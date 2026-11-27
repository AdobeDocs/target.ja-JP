---
keywords: vec;visual experience composer; vec;iframe;extension;browser;faq
description: 一部のweb サイトが[!UICONTROL Visual Experience Composer] （VEC）で確実に開かない理由を確認します。 [!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、VEC内でWeb サイトを確実に読み込むことができます。
title: '[!UICONTROL Visual Editing Helper]拡張機能の使用方法を教えてください。'
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
TQID: 'https://experienceleague.adobe.com/wUWUT-FvVIAo52PDaBMfmT7vxv8VOR71hSGhxFvylus'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
    internal-label: Web experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 5%
---
# [!UICONTROL &#x200B; ビジュアル編集ヘルパー]拡張機能 {#visual-editing-helper}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL Visual Editing Helper]** ブラウザー拡張機能が&#x200B;**[!UICONTROL Visual Experience Composer]** （VEC）にWeb サイトを確実に読み込む方法と、インストールして使用する方法について説明します。

>[!ENDSHADEBOX]

[!DNL Google Chrome]の[!DNL Adobe Experience Cloud] **[!UICONTROL Visual Editing Helper]** ブラウザー拡張機能は、[!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** （VEC）にWeb サイトを確実に読み込むため、Web エクスペリエンスの作成とチェックをより迅速におこなうことができます。

>[!IMPORTANT]
>
>この拡張機能は、記事の上部にある重要なメモで説明されているように、以前の[Target VEC Helper ブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に置き換わります。 Manifest V3はセキュリティの強化を導入しているため、[!DNL Target]でweb サイトを視覚的にオーサリングし続けるには、[!DNL Adobe]がこの新しい拡張機能をダウンロードする必要があります。

## VECで一部のWeb サイトが確実に開かない理由

次の理由により、WEB サイトがVECで確実に開かない場合があります。

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* お客様のQAまたはステージングサイトは内部サイトであり、ネットワーク外では利用できません。

拡張機能は、これらのサイト読み込み問題を解決します。この問題を解決するために、お客様は[Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)またはサードパーティの拡張機能（Requestlyなど）に依存しています。

## 拡張機能の利点

* **Iframe-busting ヘッダーが削除されました：**&#x200B;拡張機能は`X-Frame-Options`や`Content-Security-Policy`などのヘッダーをWeb サイトから暗黙的に削除するため、複雑なRequestly ルールは必要ありません。
* **at.js インジェクション：** web ページに[!DNL Target] at.js ライブラリがまだ含まれていない場合、拡張機能はそれをインジェクションできます。 web サイト向けにエクスペリエンスを作成し、プレビューリンクを使用してアクティビティを作成および確認できます。 [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) （EEC）では、拡張機能はat.jsを挿入しませんが、SameSite Cookie機能は残ります。 Web ページにat.jsを挿入するには、EECをオフにします。
* **モバイルビューポート：** [&#x200B; モバイルビューポート &#x200B;](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)は、**[!UICONTROL Enhanced Experience Composer]** （EEC）がなくてもサポートされます。
* **新しい[!DNL Target]のお客様：**&#x200B;この拡張機能を使用すると、IT開発者がweb サイトに[!DNL Target]を実装していない場合でも、[!DNL Target]を試すことができます。
* **パートナー：**&#x200B;複数の顧客のweb サイトと[!DNL Target] アカウントにサービスを提供するパートナーには、サードパーティツールの複数のルールの代わりに、VECの読み込みをサポートする1つのメカニズムが用意されています。

## 拡張機能を入手してインストールする

[!DNL Chrome]に拡張機能をインストールすると、iframeをブロックするweb サイトや、at.jsがまだ実装されていないweb サイトなど、VECでWeb サイトを確実に読み込むことができます。

1. Chrome Web Store[&#128279;](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}の[!DNL Adobe Experience Cloud] **[!UICONTROL Visual Editing Helper &#x200B;]**&#x200B;ブラウザー拡張機能に移動します。
1. **[!UICONTROL Chromeに追加]** > **[!UICONTROL 拡張機能を追加]**&#x200B;をクリックします。
1. [!DNL Target] で VEC を開きます。
1. VEC モードまたはQA モードで、[!DNL Chrome]のツールバーにある&#x200B;**[!UICONTROL Visual Editing Helper]** ブラウザー拡張機能アイコン（![Visual Editing Helper アイコン &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png)）をクリックします。

   拡張機能は、オーサリングを強化するために[!DNL Target] VECでweb サイトを開いたときに自動的に有効になります。 条件設定はなく、SameSite Cookie設定を含むすべての設定を自動的に処理します。 `SameSite=None`属性ブラウザーの修正について詳しくは、[Google Chrome SameSite Cookie ポリシー](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)を参照してください。

## 使用状況メモ

* 拡張機能は、**[!UICONTROL 管理]** > **[!UICONTROL 実装]**&#x200B;の[!DNL Target] UIで利用できる最新バージョンのat.jsを読み込み、at.jsはオーサリングライブラリをダウンロードします。
* 拡張機能を使用して[QA Mode](/help/main/c-activities/c-activity-qa/activity-qa.md)でat.jsを挿入するには、別のChrome タブを開く必要があります。 このタブは、アクティビティが作成されたのと同じ[!DNL Adobe Experience Cloud]組織に対して認証する必要があります。
* VECには、次の場合に拡張機能のインストールを推奨するメッセージが表示されます。

  * VECでweb サイトの読み込みに失敗する。
  * at.jsまたはalloy.jsは、web サイトにまだ実装されていません。

* 新しい拡張機能が試され、[古い拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)が再度使用されたが、[!DNL Target]がweb サイトの読み込みに失敗した場合は、すべてのブラウザーデータを消去し、新しい拡張機能を無効にします。

## 拡張機能の最新の変更（2026年1月17日）

この拡張機能は、VEC ヘルパーにスタートアップ cookie クリーンアップ実験機能を追加します。 この機能は、オーサリングが開始されるときに、タブごとに1回だけ未分割Cookieをクリーンアップし、パフォーマンスと信頼性を向上させます。 冗長なクリーンアップを防ぐために各タブの履歴を追跡し、タブが閉じられたときにその履歴を消去するので、タブが再度開かれたときにクリーンアップが正しく動作します。 ユニットテストは、一貫した動作を保証します。

![&#x200B; クッキー処理モード、高度なロギングオプション、実験的な機能を含むVEC Helper拡張機能のオプション、Web ページの読み込みの遅延、クッキークリーニング、スタートアップクッキークリーンアップ &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper.png)

## よくある質問

+++ 拡張機能は、[!DNL Adobe Target]または[!UICONTROL Adobe Journey Optimizer] （AJO）以外で使用されている場合、何もおこなわれますか？

拡張機能は、web サイトが[!DNL Adobe]製品（[!DNL Target]、[!DNL AJO]）のiFrame内に読み込まれた場合にのみ有効になります。 このフロー以外では、拡張機能はヘッダーの追加、削除、変更を試みず、web サイト内のコードの注入も試みません。

+++

+++ 拡張機能が [!DNL Adobe Target] VEC でアクティブな場合、何を行いますか？

[!DNL Adobe]製品（[!DNL Target]、[!DNL AJO]）のiFrame内でweb サイトが読み込まれると、拡張機能は拡張機能にバンドルされたコードをweb サイトに挿入し、[!DNL Adobe] CDNからヘルパーファイルをダウンロードしてビジュアルオーサリングを有効にします。

+++
