---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Adobe Target Visual Experience Composer（VEC）ヘルパーブラウザー拡張を使用して、VEC 内で確実に Web サイトを読み込み、エクスペリエンスを迅速に作成および QA する方法について説明します。
title: Adobe Target Visual Experience Composer（VEC）ヘルパー拡張
feature: vec
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 54%

---


# Visual Experience Composer ヘルパー拡張機能

Google Chrome用[!DNL Adobe Target] [!UICONTROL Visual Experience Composer](VEC)ヘルパーブラウザー拡張機能を使用すると、VEC内でWebサイトを確実に読み込み、WebエクスペリエンスのオーサリングとQAを迅速に行うことができます。

>[!NOTE]
>
>VEC Helperブラウザーは、Chromeの拡張機能です。 Mozilla Firefoxを使用する場合、この拡張機能は不要です。

## 一部のWebサイトがVECで確実に開かない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* Web サイトに at.js ライブラリがまだ実装されていません。
* お客様の QA またはステージサイトは、外部では利用できません（サイトは内部）。
* 強化されたSameSite cookieの適用ポリシーでGoogle Chrome 80以降を使用している。 詳しくは、[最近発表されたGoogle Chrome SameSite cookieの実施ポリシーがVECおよびEECに与える影響](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)を参照してください。

ChromeのVEC Helperブラウザー拡張機能を使用すると、サイト読み込みの問題を解決できます。サイト読み込みの際には、ユーザーが[!DNL Target] [拡張Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md#eec)や、Requestlyなどのサードパーティの拡張機能に依存するようになりました。

## VEC Helper拡張機能を使用する利点

* すべての iframe バスティングヘッダー（X-Frame-Options や Content-Security-Policy など）は、Web サイトから暗黙的に削除されます。そのための複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target]at.js JavaScript ライブラリがまだ含まれていない場合は、拡張機能を使用してライブラリを挿入することにより、Web サイトのエクスペリエンスを作成できます。その後に、プレビューリンクを使用してアクティビティを作成し、QA を実行できます。

   拡張Experience Composer(EEC)を使用する場合、拡張によってat.jsが挿入されませんが、SameSite Cookie機能は引き続き存在します。 Webページにat.jsを挿入するには、EECをオフにします。

* [モバイル](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) ビューポートは、 [!UICONTROL 拡張Experience Composer] (EEC)がなくてもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## VEC ヘルパーブラウザー拡張の取得とインストール

1. Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak)の[Adobe TargetVEC Helperブラウザー拡張機能に移動します。
1. **[!UICONTROL Chrome に追加 / 拡張機能を追加]**&#x200B;をクリックします。
1. [!DNL Target]でVECを開きます。
1. 拡張機能を使用するには、VEC または [QA モード](/help/c-activities/c-activity-qa/activity-qa.md)で、Chrome ブラウザーのツールバーにある「VEC ヘルパーブラウザー拡張」アイコン（ ![「VEC ヘルパー」アイコン](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ）をクリックします。
1. （条件付き）Webページにまだ[!DNL Target] at.js JavaScriptライブラリが含まれていない場合は、**[!UICONTROL ターゲットライブラリを挿入]**&#x200B;トグルを「オン」位置にスライドします。

   「[!UICONTROL Target ライブラリを挿入]」設定が有効になっている VEC ヘルパーを次の図に示します。

   ![VEC ヘルパー 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   オーサリングを有効にするためにページに[!DNL Target]ライブラリを挿入するかどうかを VEC ヘルパーが確認している様子を次の図に示します。

   ![VEC ヘルパー 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （条件付き）**[!UICONTROL Cookie]**&#x200B;を「on」の位置に切り替えてスライドさせ、SameSite=None属性ブラウザーの修正を自動的に追加し、Cookieの名前とドメインを指定します。

   ![VECヘルパー拡張でのcookieの切り替え](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   追加情報については、次のリンクを参照してください。

   * SameSite=None属性ブラウザーの修正について詳しくは、「最近発表されたGoogle Chrome SameSite cookieの実施ポリシーがVECおよびEECに与える影響について」を参照してください。 [Visual Experience Composerと拡張Experience Composerに関する問題のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)に記載されています。

   * Cookie名は「mbox」で、Cookieドメインはmboxを扱うドメインの2番目で最上位です。 会社のドメインなので、cookie はファーストパーティ cookie になります。例: `mycompany.com`. 詳しくは、『*Experience Cloudインターフェイスユーザーガイド*』の[Adobe Targetcookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html)を参照してください。

## メモ

* 実装するには [!DNL Target]at.js ライブラリを使用する必要があります。拡張機能では、mbox.js の実装を使用できません。
* デフォルトでは、拡張機能の「 [!UICONTROL Target ライブラリを挿入] 」フラグがオフになっています。[!DNL Target]向けにまだ実装されていないサイトで VEC を使用する場合は、このフラグを有効にすることができます。

   このフラグはグローバル設定であることに注意してください。このフラグは、VEC で開かれているすべての Web サイトに対して有効または無効になります。例えば、このフラグを「on」に設定し、既にat.jsを使用して実装されているWebサイトを開くと、at.jsが既に読み込まれていることを知らせるメッセージが表示されます。 ほとんどのお客様は、既にページにat.jsが実装されており、デフォルト設定の「オフ」を使用することを予期しています。

* この拡張機能は、[!DNL Target UI]の[!UICONTROL 管理/実装]にある&lt;a0/>から入手できる最新バージョンのat.jsを読み込みます。
* 拡張機能を使用して [QA モード](/help/c-activities/c-activity-qa/activity-qa.md)で at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ[!DNL Adobe Experience Cloud]組織に対して認証される必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、VEC ヘルパーブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js が Web サイトにまだ実装されていない場合、拡張機能のインストールを勧めるメッセージが VEC に表示されます。
   * 拡張機能を有効にして読み込みを実行している場合は、拡張機能により at.js ライブラリが挿入（必要に応じて）されるか、または VEC 内で Web サイトが確実に開かれることを示すメッセージが表示されます。

