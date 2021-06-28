---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Visual Experience Composer(VEC)で一部のWebサイトを確実に開けない理由を発見します。 VECヘルパーブラウザー拡張機能を使用すると、VEC内で確実にWebサイトを読み込むことができます。
title: Visual Experience Composer(VEC)ヘルパー拡張機能の使用方法を教えてください。
feature: Visual Experience Composer（VEC）
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 50%

---

# Visual Experience Composer ヘルパー拡張機能

Google Chrome用[!DNL Adobe Target] [!UICONTROL Visual Experience Composer](VEC)ヘルパーブラウザー拡張機能を使用すると、VEC内で確実にWebサイトを読み込み、Webエクスペリエンスを迅速に作成およびQAできます。

>[!NOTE]
>
>VECヘルパーブラウザーは、Chrome拡張機能です。 この拡張機能は、Mozilla Firefoxを使用する場合は必要ありません。

## VECで一部のWebサイトを確実に開けない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* Web サイトに at.js ライブラリがまだ実装されていません。
* お客様の QA またはステージサイトは、外部では利用できません（サイトは内部）。
* Google Chrome 80以降を、強化されたSameSite cookieの適用ポリシーと共に使用している。 詳しくは、 [最近発表されたGoogle Chrome SameSite cookieの実施ポリシーがVECおよびEECに与える影響](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)を参照してください。

Chrome用のVECヘルパーブラウザー拡張機能は、お客様が[!DNL Target] [拡張Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md#eec)や、Requestlyなどのサードパーティ拡張機能に依存するようになった、サイトの読み込みの問題を解決します。

## VECヘルパー拡張機能を使用するメリット

* すべての iframe バスティングヘッダー（X-Frame-Options や Content-Security-Policy など）は、Web サイトから暗黙的に削除されます。複雑なRequestlyルールを作成する必要はなくなりました。
* Web ページに [!DNL Target]at.js JavaScript ライブラリがまだ含まれていない場合は、拡張機能を使用してライブラリを挿入することにより、Web サイトのエクスペリエンスを作成できます。その後に、プレビューリンクを使用してアクティビティを作成し、QA を実行できます。

   拡張Experience Composer(EEC)を使用する場合、拡張機能はat.jsを挿入しませんが、SameSite Cookie機能は引き続き存在します。 Webページにat.jsを挿入するには、EECをオフにします。

* [モバ](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) イルビューポートは、拡張Experience Composer  (EEC)がない場合でもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## VEC ヘルパーブラウザー拡張の取得とインストール

1. Chrome Web Storeの[Adobe Target VECヘルパーブラウザー拡張機能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak)に移動します。
1. **[!UICONTROL Chrome に追加 / 拡張機能を追加]**&#x200B;をクリックします。
1. [!DNL Target]でVECを開きます。
1. 拡張機能を使用するには、VEC または [QA モード](/help/c-activities/c-activity-qa/activity-qa.md)で、Chrome ブラウザーのツールバーにある「VEC ヘルパーブラウザー拡張」アイコン（ ![「VEC ヘルパー」アイコン](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ）をクリックします。
1. （条件付き）Webページにまだ[!DNL Target] at.js JavaScriptライブラリが含まれていない場合は、「**[!UICONTROL Targetライブラリを挿入]**」切り替えを「オン」位置にスライドさせます。

   「[!UICONTROL Target ライブラリを挿入]」設定が有効になっている VEC ヘルパーを次の図に示します。

   ![VEC ヘルパー 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   オーサリングを有効にするためにページに[!DNL Target]ライブラリを挿入するかどうかを VEC ヘルパーが確認している様子を次の図に示します。

   ![VEC ヘルパー 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （条件付き） **[!UICONTROL Cookies]**&#x200B;の切り替えを「オン」位置にスライドさせて、SameSite=None属性ブラウザーの修正を自動的に追加し、cookieの名前とドメインを指定します。

   ![VECヘルパー拡張機能でのcookieの切り替え](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   次のリンクで追加情報を参照できます。

   * SameSite=None属性ブラウザーの修正に関する詳細については、「最近発表されたGoogle Chrome SameSite cookieの実施ポリシーがVECおよびEECに与える影響」を参照してください。 [Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

   * Cookie名は「mbox」で、Cookieドメインはmboxを扱うドメインの第2の最上位レベルです。 会社のドメインなので、cookie はファーストパーティ cookie になります。例: `mycompany.com`. 詳しくは、『*Experience Cloudインターフェイスユーザーガイド*』の[Adobe Target Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html?lang=ja)を参照してください。

## メモ

* デフォルトでは、拡張機能の「 [!UICONTROL Target ライブラリを挿入] 」フラグがオフになっています。[!DNL Target]向けにまだ実装されていないサイトで VEC を使用する場合は、このフラグを有効にすることができます。

   このフラグはグローバル設定です。 このフラグは、VEC で開かれているすべての Web サイトに対して有効または無効になります。例えば、このフラグを「on」に設定し、at.jsで既に実装されているWebサイトを開くと、at.jsが既に読み込まれていることを知らせるメッセージを受け取ります。 Adobeでは、ほとんどのお客様が既にページにat.jsが実装され、デフォルト設定の「off」を使用していると予想します。

* この拡張機能は、[!DNL Target UI]の[!UICONTROL 管理/実装]から利用できる最新バージョンのat.jsを読み込みます。
* 拡張機能を使用して [QA モード](/help/c-activities/c-activity-qa/activity-qa.md)で at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ[!DNL Adobe Experience Cloud]組織に対して認証される必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、VEC ヘルパーブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js が Web サイトにまだ実装されていない場合、拡張機能のインストールを勧めるメッセージが VEC に表示されます。
   * 拡張機能を有効にして読み込みを実行している場合は、拡張機能により at.js ライブラリが挿入（必要に応じて）されるか、または VEC 内で Web サイトが確実に開かれることを示すメッセージが表示されます。
