---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: '[!UICONTROL Visual Experience Composer]（VEC）で一部の web サイトを確実に開くことができない理由を明らかにします。 VEC Helper ブラウザー拡張機能を使用すると、VEC内でWeb サイトを確実に読み込むことができます。'
title: '[!UICONTROL Visual Experience Composer] （VEC） ヘルパー拡張機能の使用方法を教えてください。'
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
TQID: https://experienceleague.adobe.com/lqZGGWG1NVtKDzNGPq5k2bDPzxDfNWqPtJ-bYfLCr3Q
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
source-wordcount: 1079
ht-degree: 55%

---

# [!UICONTROL Visual Experience Composer] ヘルパー拡張機能

[!DNL Google Chrome]の[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC） ヘルパーブラウザー拡張機能を使用すると、VEC内でWeb サイトを確実に読み込んで、Web エクスペリエンスを迅速にオーサリングおよびQAできます。

VEC ヘルパーブラウザーは[!DNL Chrome]拡張機能です。 [!DNL Mozilla Firefox]を使用する場合、この拡張機能は必要ありません。

>[!IMPORTANT]
>
>* この記事に記載されている従来の[!DNL Target] VEC Helper拡張機能は、Manifest V2を使用して作成されました。 [!DNL Google] では、2024年6月以降、Manifest V2 を使用して作成された拡張機能を許可しなくなると発表しました。 詳しくは、*Chrome for Developers* サイトの[!DNL Google]の[Manifest V2 サポートタイムラインのお知らせ](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank}を参照してください。
>
>* 2024年6月以降、[!DNL Google]は、このトピックで説明されている拡張機能を含む、Manifest V2を使用して作成された拡張機能の無効化を開始します。 [!DNL Adobe] では、お客様ができるだけ早く新しい [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)に移行することをお勧めします。

## VEC で一部の web サイトを確実に開くことができない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* Web サイトに at.js ライブラリがまだ実装されていません。
* 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。
* VECを使用して、[Service Workers](https://developer.mozilla.org/ja-JP/docs/Web/API/Service_Worker_API){target=_blank} （SW）を使用しているweb サイトを開こうとする場合、現在の制限がいくつかあります。

SW は、web ページによってインストールされているドメインのリクエストをインターセプトするために使用できる web テクノロジーです。 SW はページの訪問中は存続し、以降の訪問時にはアクティブになります。 SW は、どのリクエストを通過させ、どのリクエストをインターセプトし、代わりにキャッシュからサービスを提供するかを決定します。

SW はキャッシュを制御できます。Web ページ自体、JS、CSS、IMG、AJAXリクエストなどの静的リソース、コンテンツおよび応答ヘッダーをキャッシュできます。これには、SAMEORIGIN、CSP（Content-Security-Policy）、Set-Cookie など、X-Frame-Options のような [Target VEC ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)が削除しようとするものを含みます。

残念ながら、web リクエストをインターセプトするChrome拡張APIは、SWによってインターセプトされ処理されたリクエストを受け取りません。 したがって、Web ページのリクエストがSWによってキャッシュから提供された場合、X-Frame-Options ヘッダーまたはCSP ヘッダーもキャッシュされたため、Web ページがVEC内で読み込まれないため、拡張機能はヘッダーとCookieを修正できません。

回避策として、Chrome Developer Tools/Application タブでService Workerを無効にし、Service Worker セクションの「Bypass for network」チェックボックスを有効にすることができます。

* 強化されたSameSite Cookie適用ポリシーを使用して、Google Chrome 80以降を使用している。 詳細については、[最近発表されたGoogle Chrome SameSite Cookie適用ポリシーが、VECおよびEEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)にどのような影響を与えますか？

Chrome用VEC Helper ブラウザー拡張機能は、お客様が[!DNL Target] [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)またはサードパーティの拡張機能（Requestlyなど）に依存するようになったサイト読み込みの問題を解決します。

## VEC Helper拡張機能を使用するメリット

* すべての iframe バスティングヘッダー（X-Frame-Options や Content-Security-Policy など）は、Web サイトから暗黙的に削除されます。 複雑なRequestly ルールを作成する必要はもうありません。
* Web ページに [!DNL Target]at.js JavaScript ライブラリがまだ含まれていない場合は、拡張機能を使用してライブラリを挿入することにより、Web サイトのエクスペリエンスを作成できます。 その後に、プレビューリンクを使用してアクティビティを作成し、QA を実行できます。

  Enhanced Experience Composer （EEC）を使用すると、拡張機能はat.jsを挿入しませんが、SameSite Cookie機能は引き続き存在します。 Web ページに at.js を挿入するには、EEC をオフにします。

* [モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)は、[!UICONTROL Enhanced Experience Composer]（EEC）がなくてもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## VEC ヘルパーブラウザー拡張の取得とインストール

1. Chrome Web ストア [&#128279;](https://chromewebstore.google.com/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca)のAdobe Target VEC Helper ブラウザー拡張機能に移動します。
1. **[!UICONTROL Add to Chrome > Add Extension]** をクリックします。
1. [!DNL Target] で VEC を開きます。
1. 拡張機能を使用するには、VEC または [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)で、Chrome ブラウザーのツールバーにある「VEC ヘルパーブラウザー拡張」アイコン（ ![「VEC ヘルパー」アイコン](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ）をクリックします。
1. （条件付き） web ページに[!DNL Target] at.js JavaScript ライブラリがまだ含まれていない場合は、**[!UICONTROL Inject Target Libraries]** トグルを「オン」の位置にスライドさせます。

   次の図は、[!UICONTROL Inject Target Libraries]設定が有効になっているVEC ヘルパーを示しています。

   ![VEC ヘルパー 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   オーサリングを有効にするためにページに[!DNL Target]ライブラリを挿入するかどうかを VEC ヘルパーが確認している様子を次の図に示します。

   ![VEC ヘルパー 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （条件付き） **[!UICONTROL Cookies]** トグルを「オン」位置にスライドさせ、`SameSite=None`属性ブラウザーの修正を自動的に追加します。

   VEC ヘルパー拡張機能の![Cookie トグル &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   `SameSite=None` 属性に関するブラウザーの修正について詳しくは、「Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？」の節を参照してください。 [Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

## メモ

* 拡張機能の[!UICONTROL Inject Target libraries] フラグは、デフォルトでオフになっています。 [!DNL Target]向けにまだ実装されていないサイトで VEC を使用する場合は、このフラグを有効にすることができます。

  このフラグはグローバル設定です。 このフラグは、VEC で開かれているすべての Web サイトに対して有効または無効になります。 例えば、このフラグを「on」に設定し、at.jsで既に実装されているweb サイトを開くと、at.jsが既に読み込まれていることを知らせるメッセージが表示されます。 Adobeでは、多くのお客様が既にat.jsをページに実装しており、デフォルト設定の「off」を使用していることを想定しています。

* 拡張機能は、[!UICONTROL Administration > Implementation]の[!DNL Target UI]から利用可能な最新バージョンのat.jsを読み込みます。
* 拡張機能を使用して [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)で at.js を挿入する場合は、別の Chrome タブを開く必要があります。 この Chrome タブは、アクティビティを作成したのと同じ[!DNL Adobe Experience Cloud]組織に対して認証される必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、VEC ヘルパーブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js が Web サイトにまだ実装されていない場合、拡張機能のインストールを勧めるメッセージが VEC に表示されます。
   * 拡張機能を有効にして読み込みを実行している場合は、拡張機能により at.js ライブラリが挿入（必要に応じて）されるか、または VEC 内で Web サイトが確実に開かれることを示すメッセージが表示されます。
