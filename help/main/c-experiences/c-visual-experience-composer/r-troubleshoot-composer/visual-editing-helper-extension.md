---
keywords: vec;visual experience composer; vec;iframe;extension;browser;faq
description: 一部のweb サイトが[!UICONTROL Visual Experience Composer] （VEC）で確実に開かない理由を確認します。 [!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、VEC内でWeb サイトを確実に読み込むことができます。
title: '[!UICONTROL Visual Editing Helper]拡張機能の使用方法を教えてください。'
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
TQID: https://experienceleague.adobe.com/wUWUT-FvVIAo52PDaBMfmT7vxv8VOR71hSGhxFvylus
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 837
ht-degree: 57%

---

# [!UICONTROL &#x200B; ビジュアル編集ヘルパー]拡張機能

[!DNL Google Chrome]の[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能を使用すると、[!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）内でWeb サイトを確実に読み込み、Web エクスペリエンスをすばやく作成してQAできます。

>[!IMPORTANT]
>
>* この新しい拡張機能は、以前の [Target VEC Helper ブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に代わるものです。 この記事の上部にある重要なメモを参照してください。 Manifest v3 のセキュリティ強化のため、[!DNL Target] では、[!DNL Adobe] で web サイトを視覚的に引き続き作成するために、この新しい拡張機能をダウンロードする必要があります。

## [!UICONTROL Visual Editing Helper]拡張機能の変更（2026年1月17日）

### **VEC ヘルパーに新しいスタートアップ cookie クリーンアップ実験機能を追加して、問題を修正しました。**

* VEC ヘルパーに新しいスタートアップ cookie クリーンアップ実験機能を追加することで、問題を修正しました。
* この機能強化により、オーサリングが継続的ではなく開始される際に、タブごとに1回、未分割Cookieをクリーニングすることで、パフォーマンスと信頼性が向上します。
* この機能は、冗長なクリーンアップを防ぐためにタブ履歴を追跡し、タブのクローズ時に履歴をクリアするので、タブが再度開かれたときにクリーンアップが正しく動作します。
* 一貫した動作を保証するために、包括的な単体テストが追加されました。

![VECの新しいオプション &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper.png)

## VEC で一部の web サイトを確実に開くことができない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。

[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能は、顧客が[!DNL Target] [拡張Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)またはサードパーティの拡張機能（Requestlyなど）に依存するようになったサイト読み込みの問題を解決します。

## [!UICONTROL Visual Editing Helper]拡張機能を使用するメリット

* すべての iframe バスティングヘッダー（`X-Frame-Options` や `Content-Security-Policy` など）は、web サイトから暗黙的に削除されます。 複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target] at.js ライブラリがまだ含まれていない場合は、この拡張機能を使用してライブラリを挿入することにより、web サイトのエクスペリエンスを作成できます。 その後に、アクティビティを作成し、プレビューリンクを使用してアクティビティの QA を実行できます。

  [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) を使用すると、拡張機能では at.js は挿入されませんが、SameSite Cookie 機能は引き続き存在します。 Web ページに at.js を挿入するには、EEC をオフにします。

* [&#x200B; モバイルビューポート &#x200B;](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)は、[!UICONTROL Enhanced Experience Composer] （EEC）がなくてもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## [!UICONTROL Visual Editing Helper] ブラウザー拡張機能を取得してインストールします

1. Chrome Web Store[&#128279;](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}の[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] ブラウザー拡張機能に移動します。
1. **[!UICONTROL Chromeに追加]** > **[!UICONTROL 拡張機能を追加]**&#x200B;をクリックします。
1. [!DNL Target] で VEC を開きます。
1. 拡張機能を使用するには、VEC モードまたはQA モードで、Chrome ブラウザーのツールバーにある[!UICONTROL Visual Editing Helper] ブラウザー拡張機能アイコン（![Visual Editing Extension アイコン &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png)）をクリックします。

   [!UICONTROL Visual Editing Helper]は、Web サイトが[!UICONTROL Target] VECで開かれたときに、オーサリングを強化するために自動的に有効になります。 この拡張機能には、条件付き設定はありません。 この拡張機能では、SameSite Cookie の設定を含むすべての設定を自動的に処理します。

   `SameSite=None` 属性に関するブラウザーの修正について詳しくは、「Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？」の節を参照してください。 [Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。

## メモ

* [!DNL Target]の場合、拡張機能は[!UICONTROL 管理] > [!UICONTROL 実装]の[!DNL Target] UIから利用可能な最新バージョンのat.jsを読み込み、at.jsはオーサリングライブラリをダウンロードします。
* [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)でこの拡張機能を使用して at.js を挿入する場合は、別の Chrome タブを開く必要があります。 この Chrome タブは、アクティビティを作成したのと同じ [!DNL Adobe Experience Cloud] 組織に対して認証されている必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * 読み込みに失敗したVECを使用してweb サイトを読み込もうとすると、[!UICONTROL Visual Editing Helper] ブラウザー拡張機能をインストールすることを示唆するメッセージが表示されます。
   * at.js または alloy.js が web サイトにまだ実装されていない場合、この拡張機能のインストールを勧めるメッセージが VEC に表示されます。
* 新しい拡張機能を使用してから[古い拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)に戻り、[!DNL Target] が web サイトの読み込みに失敗した場合は、すべてのブラウザー データを消去し、新しい拡張機能を無効にします。

## よくある質問

### 拡張機能は、アクティブな場合、[!DNL Adobe Target]または[!UICONTROL Adobe Journey Optimizer] （AJO）以外で使用する場合に何か実行しますか？

この拡張機能は、対象の web サイトが [!DNL Adobe] 製品（[!DNL Target]、[!DNL AJO]）の iFrame 内に読み込まれた場合にのみアクティブになります。 このフロー以外では、拡張機能はヘッダーを追加、削除、変更せずに、web サイト内にコードを挿入しようとしません。

### 拡張機能が [!DNL Adobe Target] VEC でアクティブな場合、何を行いますか？

Web サイトが [!DNL Adobe] 製品（[!DNL Target]、[!DNL AJO]）の iFrame 内に読み込まれると、拡張機能は web サイトにコード（拡張機能にバンドルされている）を挿入し、[!DNL Adobe] CDN からヘルパーファイルをダウンロードしてビジュアルオーサリングを有効にします。
