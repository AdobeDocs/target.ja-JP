---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Adobe Target Visual Experience Composer（VEC）ヘルパーブラウザー拡張を使用して、VEC 内で確実に Web サイトを読み込み、エクスペリエンスを迅速に作成および QA する方法について説明します。
title: Adobe Target Visual Experience Composer（VEC）ヘルパー拡張
feature: vec
topic: Standard
translation-type: tm+mt
source-git-commit: 73af03c895ce98e5b6762950e8cd638d7bef0990
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 54%

---


# Visual Experience Composer ヘルパー拡張機能

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Helper browser extension for Google Chrome lets you load websites reliably within the VEC to rapidly author and QA web experiences.

>[!NOTE]
>
>VEC Helperブラウザーは、Chromeの拡張機能です。 Mozilla Firefoxを使用する場合、この拡張機能は不要です。

## 一部のWebサイトがVECで確実に開かない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* Web サイトに at.js ライブラリがまだ実装されていません。
* お客様の QA またはステージサイトは、外部では利用できません（サイトは内部）。
* 強化されたSameSite cookieの適用ポリシーでGoogle Chrome 80以降を使用している。 詳しくは、 [「最近発表されたGoogle Chrome SameSite cookieの実施ポリシーがVECおよびEECに与える影響を教えてください](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

The VEC Helper browser extension for Chrome solves site-loading issues for which customers now rely on the [!DNL Target] [Enhanced Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md#eec) or third-party extensions, such as Requestly.

## VEC Helper拡張機能を使用する利点

* すべての iframe バスティングヘッダー（X-Frame-Options や Content-Security-Policy など）は、Web サイトから暗黙的に削除されます。そのための複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target]at.js JavaScript ライブラリがまだ含まれていない場合は、拡張機能を使用してライブラリを挿入することにより、Web サイトのエクスペリエンスを作成できます。その後に、プレビューリンクを使用してアクティビティを作成し、QA を実行できます。

   拡張Experience Composer(EEC)を使用する場合、拡張によってat.jsが挿入されませんが、SameSite Cookie機能は引き続き存在します。 Webページにat.jsを挿入するには、EECをオフにします。

* [モバイルビューポート](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) は、 [!UICONTROL 拡張Experience Composer] (EEC)がなくてもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## VEC ヘルパーブラウザー拡張の取得とインストール

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. **[!UICONTROL Chrome に追加 / 拡張機能を追加]**&#x200B;をクリックします。
1. でVECを開き [!DNL Target]ます。
1. 拡張機能を使用するには、VEC または [QA モード](/help/c-activities/c-activity-qa/activity-qa.md)で、Chrome ブラウザーのツールバーにある「VEC ヘルパーブラウザー拡張」アイコン（ ![「VEC ヘルパー」アイコン](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ）をクリックします。
1. （条件付き）Webページにまだ **[!UICONTROL at.js JavaScriptライブラリが含まれていない場合、「ターゲットライブラリを]** 挿入 [!DNL Target] 」トグルを「オン」位置にスライドさせます。

   「[!UICONTROL Target ライブラリを挿入]」設定が有効になっている VEC ヘルパーを次の図に示します。

   ![VEC ヘルパー 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   オーサリングを有効にするためにページに[!DNL Target]ライブラリを挿入するかどうかを VEC ヘルパーが確認している様子を次の図に示します。

   ![VEC ヘルパー 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （条件付き）「 **[!UICONTROL Cookie]** 」を「on」の位置に切り替えて、SameSite=None属性ブラウザーの修正を自動的に追加し、Cookieの名前とドメインを指定します。

   ![VECヘルパー拡張でのcookieの切り替え](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   追加情報については、次のリンクを参照してください。

   * SameSite=None属性ブラウザーの修正について詳しくは、「最近発表されたGoogle Chrome SameSite cookieの実施ポリシーがVECおよびEECに与える影響について」を参照してください。 in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * Cookie名は「mbox」で、Cookieドメインはmboxを扱うドメインの2番目で最上位です。 会社のドメインなので、cookie はファーストパーティ cookie になります。例: `mycompany.com`. 詳細については、『 [Experience Cloudインターフェイスユーザガイド』の「](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-target.html) Adobe Targetcookie *」を参照してください*。

## メモ

* 実装するには [!DNL Target]at.js ライブラリを使用する必要があります。拡張機能では、mbox.js の実装を使用できません。
* デフォルトでは、拡張機能の「 [!UICONTROL Target ライブラリを挿入] 」フラグがオフになっています。[!DNL Target]向けにまだ実装されていないサイトで VEC を使用する場合は、このフラグを有効にすることができます。

   このフラグはグローバル設定であることに注意してください。このフラグは、VEC で開かれているすべての Web サイトに対して有効または無効になります。例えば、このフラグを「on」に設定し、既にat.jsを使用して実装されているWebサイトを開くと、at.jsが既に読み込まれていることを知らせるメッセージが表示されます。 ほとんどのお客様は、既にページにat.jsが実装されており、デフォルト設定の「オフ」を使用することを予期しています。

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* 拡張機能を使用して [QA モード](/help/c-activities/c-activity-qa/activity-qa.md)で at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ[!DNL Adobe Experience Cloud]組織に対して認証される必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、VEC ヘルパーブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js が Web サイトにまだ実装されていない場合、拡張機能のインストールを勧めるメッセージが VEC に表示されます。
   * 拡張機能を有効にして読み込みを実行している場合は、拡張機能により at.js ライブラリが挿入（必要に応じて）されるか、または VEC 内で Web サイトが確実に開かれることを示すメッセージが表示されます。

