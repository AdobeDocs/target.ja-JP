---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: '[!UICONTROL Visual Experience Composer]（VEC）で一部の web サイトを確実に開くことができない理由を明らかにします。VEC Helper ブラウザー拡張機能を使用すると、VEC 内に web サイトを確実に読み込むことができます。'
title: '[!UICONTROL Visual Experience Composer] （VEC）ヘルパー拡張機能の使用方法？'
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 97b1d78de2d6ba33c1dd72494edcfc97fc3ba7e6
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 55%

---

# [!UICONTROL Visual Experience Composer] helper 拡張機能

[!DNL Google Chrome] の [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）ヘルパーブラウザー拡張機能を使用すると、VEC 内に web サイトを確実に読み込んで、web エクスペリエンスを迅速に作成および QA できます。

VEC Helper ブラウザーは [!DNL Chrome] 拡張機能です。 [!DNL Mozilla Firefox] を使用する場合、この拡張機能は必要ありません。

>[!IMPORTANT]
>
>この記事で説明している従来の [!DNL Target] VEC Helper 拡張機能は、Manifest V2 を使用して作成されました。 [!DNL Google] では、2024年6月以降、Manifest V2 を使用して作成された拡張機能を許可しなくなると発表しました。詳しくは、*Chrome for Developers* サイトの [!DNL Google] にある [Manifest V2 support timeline announcement](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} を参照してください。
>
>2024 年 6 月以降、[!DNL Google] は、このトピックで説明している拡張機能を含め、Manifest V2 を使用して作成された拡張機能の無効化を開始します。 [!DNL Adobe] では、お客様ができるだけ早く新しい [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)に移行することをお勧めします。

## VEC で一部の web サイトを確実に開くことができない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* Web サイトに at.js ライブラリがまだ実装されていません。
* 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。
* 現在、[Service Workers](https://developer.mozilla.org/ja-JP/docs/Web/API/Service_Worker_API){target=_blank} （SW）を使用している web サイトを VEC で開こうとすると、いくつかの制限があります。

SW は、web ページによってインストールされているドメインのリクエストをインターセプトするために使用できる web テクノロジーです。SW はページの訪問中は存続し、以降の訪問時にはアクティブになります。SW は、どのリクエストを通過させ、どのリクエストをインターセプトし、代わりにキャッシュからサービスを提供するかを決定します。

SW はキャッシュを制御できます。Web ページ自体、JS、CSS、IMG、AJAXリクエストなどの静的リソース、コンテンツおよび応答ヘッダーをキャッシュできます。これには、SAMEORIGIN、CSP（Content-Security-Policy）、Set-Cookie など、X-Frame-Options のような [Target VEC ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)が削除しようとするものを含みます。

残念ながら、web リクエストをインターセプトするChrome Extension API は、SW によってインターセプトおよび処理されたリクエストを受け取りません。 したがって、web ページリクエストが SW によってキャッシュから提供された場合、X-Frame-Options ヘッダーまたは CSP ヘッダーもキャッシュされたため、web ページが VEC 内に読み込まれないので、拡張機能ではヘッダーと Cookie を修正できません。

考えられる回避策として、Chrome Developer Tools/Application タブで「Service Workers」を無効にし、「Service Workers」セクションの下にある「Bypass for network」チェックボックスを有効にします。

* Google Chrome 80 以降を拡張された SameSite cookie 強制ポリシーと共に使用している。 詳しくは、[ 最近発表されたGoogle Chromeの SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite) を参照してください。

Chrome用 VEC Helper ブラウザー拡張機能は、お客様が [!DNL Target] [ 拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) やサードパーティ拡張機能（Requestly など）に頼るきっかけとなったサイト読み込みの問題を解決します。

## VEC Helper 拡張機能を使用するメリット

* すべての iframe バスティングヘッダー（X-Frame-Options や Content-Security-Policy など）は、Web サイトから暗黙的に削除されます。複雑な Requestly ルールを作成する必要はなくなります。
* Web ページに [!DNL Target]at.js JavaScript ライブラリがまだ含まれていない場合は、拡張機能を使用してライブラリを挿入することにより、Web サイトのエクスペリエンスを作成できます。その後に、プレビューリンクを使用してアクティビティを作成し、QA を実行できます。

  なお、拡張 Experience Composer （EEC）を使用する場合、拡張機能は at.js を挿入しませんが、SameSite Cookie 機能は引き続き存在します。 Web ページに at.js を挿入するには、EEC をオフにします。

* [モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)は、[!UICONTROL Enhanced Experience Composer]（EEC）がなくてもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## VEC ヘルパーブラウザー拡張の取得とインストール

1. Chrome Web ストアの [Adobe Target VEC Helper ブラウザー拡張機能に移動します ](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak)。
1. **[!UICONTROL Add to Chrome > Add Extension]** をクリックします。
1. [!DNL Target] で VEC を開きます。
1. 拡張機能を使用するには、VEC または [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)で、Chrome ブラウザーのツールバーにある「VEC ヘルパーブラウザー拡張」アイコン（ ![「VEC ヘルパー」アイコン](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ）をクリックします。
1. （条件付き） web ページに [!DNL Target] at.js JavaScript ライブラリがまだ含まれていない場合は、**[!UICONTROL Inject Target Libraries]** 切り替えスイッチを「オン」の位置にスライドさせます。

   次の図は、[!UICONTROL Inject Target Libraries] 設定が有効になっている VEC Helper を示しています。

   ![VEC ヘルパー 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   オーサリングを有効にするためにページに[!DNL Target]ライブラリを挿入するかどうかを VEC ヘルパーが確認している様子を次の図に示します。

   ![VEC ヘルパー 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （条件付き） **[!UICONTROL Cookies]** の切り替えスイッチを「オン」の位置にスライドすると、`SameSite=None` 属性ブラウザーの修正が自動的に追加されます。

   ![VEC ヘルパー拡張機能の cookie の切り替え ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   `SameSite=None` 属性に関するブラウザーの修正について詳しくは、「Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？」の節を参照してください。[Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

## メモ

* 拡張機能の [!UICONTROL Inject Target libraries] フラグは、デフォルトではオフになっています。 [!DNL Target]向けにまだ実装されていないサイトで VEC を使用する場合は、このフラグを有効にすることができます。

  このフラグはグローバル設定です。 このフラグは、VEC で開かれているすべての Web サイトに対して有効または無効になります。例えば、このフラグを「on」に設定して、at.js で既に実装されている web サイトを開くと、at.js が既に読み込まれているというメッセージが届きます。 Adobeでは、ほとんどのお客様が既に at.js をページに実装しており、「off」のデフォルト設定を使用していることを想定しています。

* この拡張機能は、[!UICONTROL Administration > Implementation] の [!DNL Target UI] から利用可能な最新バージョンの at.js を読み込みます。
* 拡張機能を使用して [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)で at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ[!DNL Adobe Experience Cloud]組織に対して認証される必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、VEC ヘルパーブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js が Web サイトにまだ実装されていない場合、拡張機能のインストールを勧めるメッセージが VEC に表示されます。
   * 拡張機能を有効にして読み込みを実行している場合は、拡張機能により at.js ライブラリが挿入（必要に応じて）されるか、または VEC 内で Web サイトが確実に開かれることを示すメッセージが表示されます。
