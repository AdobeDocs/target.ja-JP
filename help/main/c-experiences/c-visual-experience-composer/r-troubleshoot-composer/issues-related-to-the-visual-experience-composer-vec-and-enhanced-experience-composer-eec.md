---
keywords: ターゲティング；visual experience composer；ホワイトリスト；ホワイトリスト；許可リスト;enhanced visual experience composer;vec;visual experience composerのトラブルシューティング；eec;enhanced experience composer;tls;tls 1.2
description: 特定の条件で [!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）および[!UICONTROL Enhanced Experience Composer] （EEC）で発生することがある問題のトラブルシューティング方法について説明します。
title: '[!UICONTROL Visual Experience Composer]と[!UICONTROL Enhanced Experience Composer]に関連する問題のトラブルシューティング方法を教えてください。'
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
TQID: https://experienceleague.adobe.com/4v7Qe-Yzjke-GceUSRDO2SMZGkxvrkdsSXQt8TR-bic
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
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1202
ht-degree: 32%

---

# [!DNL Adobe Target] [!UICONTROL Visual Experience Composer]および[!UICONTROL Enhanced Experience Composer]に関する問題のトラブルシューティング

ディスプレイの問題やその他の問題は、[!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）および[!UICONTROL Enhanced Experience Composer] （EEC）で、特定の条件の下で発生することがあります。

## Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？ {#samesite}

+++詳細
次の[!DNL Chrome] リリースを使用する場合は、VECおよびEECに影響を与える変更に注意してください。

>[!NOTE]
>
>次の変更は、以下に概説する3つの更新すべてに影響します。
>
> * *not*&#x200B;様は、[VEC Helper拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)がインストールされていて、サイトのパスワードで保護されたページに対して有効になっていなくても、VECを使用できます。 サイトのログイン Cookieは3rd パーティ Cookieと見なされ、[!UICONTROL Browse] モードのVEC エディター内でログイン リクエストを送信しません。 唯一の例外は、サイトログイン Cookieに`SameSite=None`と`Secure`の属性が既に設定されている場合です。

**Chrome 94 （2021年9月21日）**: Chrome 94 リリース（2021年9月21日）に予定されている差し迫った変更により、次の変更は、Chrome 94以降のブラウザー版を使用しているすべてのユーザーに影響します。

* コマンドラインフラグ `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`が削除されます。

**Chrome 91 （2021年5月25日）**: Chrome 91 リリース（2021年5月25日）に対する変更が実装された場合、次の変更は、Chrome 91以降のブラウザー版を使用しているすべてのユーザーに影響します。

* フラグ `#same-site-by-default-cookies`と`#cookies-without-same-site-must-be-secure`が`chrome://flags`から削除されました。 このビヘイビアーはデフォルトで有効になりました。

**Chrome 80 （2020年8月）**:2020年8月に導入された変更により、Chrome 80以降のブラウザー版を使用しているすべてのユーザー：

* アクティビティの編集中に&#x200B;*not*&#x200B;さんが[!DNL Target] ライブラリをダウンロードできます（これらのライブラリがサイトにまだ存在しない場合）。 これは、ダウンロードコールが顧客ドメインから保護された[!DNL Adobe] ドメインに向けて行われ、未認証として拒否されるためです。

* EECは、`adobemc.com domain`でCookieにSameSite属性を設定できないため、すべてのユーザーに対して&#x200B;*not*&#x200B;機能を提供します。 この属性がないと、ブラウザーはこれらのCookieを拒否し、EECが失敗します。

+++

### ブロックするCookieを決定

+++詳細
SameSite cookieの適用ポリシーが原因でブロックされているCookieを判断するには、[!DNL Chrome]の[!DNL Developer Tools]を使用します。

1. [!DNL Developer Tools]にアクセスするには、[!DNL Chrome]でVECを表示しているときに、Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**&#x200B;の右上隅にある&#x200B;**[!UICONTROL ellipsis]** アイコンをクリックします。
1. 「**[!UICONTROL Network]**」タブをクリックし、「ブロックされたCookie」を探します。

   >[!NOTE]
   >
   >**[!UICONTROL Has blocked cookies]** チェックボックスを使用すると、ブロックされたCookieを簡単に見つけることができます。

+++

## [!DNL Target]はマルチレベル iframeをサポートしていますか？

+++詳細
[!DNL Target]はマルチレベル iframeをサポートしていません。 web サイトが子iframeを持つiframeを読み込む場合、at.jsは親iframeとのみ相互作用します。 [!DNL Target] ライブラリは子iframeと相互作用しません。

回避策として、子 iframe の URL を持つエクスペリエンスにページを追加できます。

+++

## ページを編集しようとすると、ページではなく、スピナーが表示されます。 （VEC と EEC） {#section_313001039F79446DB28C70D932AF5F58}

+++詳細
この状況は、URLに#文字が含まれている場合に発生する可能性があります。 問題を修正するには、VECまたはEECで[!UICONTROL Browse] モードに切り替え、次に[!UICONTROL Compose] モードに戻します。 スピナーの表示が消えて、ページが読み込まれます。

+++

## コンテンツセキュリティポリシー（CSP）ヘッダーは、web サイトの[!DNL Target] ライブラリをブロックします。 （VEC と EEC） {#section_89A30C7A213D43BFA0822E66B482B803}


+++詳細
Web サイトのCSP ヘッダーで[!DNL Target] ライブラリがブロックされている場合は、Web サイトが読み込まれますが、編集は行われません。[!DNL Target] ライブラリがブロックされていないことを確認してください。

>[!NOTE]
>
>次の情報に加えて、[!DNL Google Chrome]には[Adobe Target VEC Helper ブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用できます。

![cps_headers image](assets/cps_headers.png)

回避策として、次に示すように、[!DNL Requestly] ルールを設定してCSP ヘッダーを削除できます。

![cps_headers_2 image](assets/cps_headers_2.png)

VEC内でリソースが読み込まれない原因となるヘッダーに対して、同様の[!DNL Requestly] ルールを設定できます。

[!DNL Requestly]の場合、ヘッダーを削除する必要がある場合は、次のいずれかの操作を行う必要があります。

* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。

+++

## 保存されているアクティビティの再編集時に、VEC または EEC が壊れているように見えたり、初期化されなかったりします。 （VEC と EEC） {#section_5AC3BA8F8FBB451EA814F298D0645E54}

+++詳細
エクスペリエンスを定義した後にWeb サイトがVEC以外で変更された場合、アクティビティを再編集するために開いたときに、以前に実行されたアクションのセレクターが見つかりません。 ページは壊れているように表示され、警告は表示されません。

+++

## JavaScript を含む回転バナーなどのコンテンツが VEC または EEC に表示されません。 （VEC と EEC） {#section_8B5BE6EB050B42D6A14A054724C41330}

+++詳細
デフォルトでは、VECはJavaScript要素をブロックします。 JavaScriptを無効にすると、これらの要素を操作できます。 セットアップするサイトによっては、それでも一部のアイテムの表示が正しくなかったり表示できなかったりする場合があります。

+++

## ページ内の 1 つの要素を変更すると、複数の要素が変更されます。 （VEC と EEC） {#section_309188ACF34942989BE473F63C5710AF}

+++詳細
同じ DOM 要素 ID がページ内の複数の要素に使用されている場合、それらの要素のいずれかを変更するとその ID の要素がすべて変更されます。 この現象を予防するには、各ページで ID は 1 回のみ使用するようにしてください。 この方法は、HTMLの標準的なベストプラクティスです。 詳しくは、[&#x200B; ページ変更シナリオ &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)を参照してください。

+++

## iFrame バスティングのサイトのエクスペリエンスを編集できない。 （VEC と EEC） {#section_9FE266B964314F2EB75604B4D7047200}

+++詳細
この問題は、[!UICONTROL Enhanced Experience Composer] （EEC）を有効にすることで対処できます。 **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]**&#x200B;をクリックし、[!UICONTROL Enhanced Experience Composer]を有効にするチェックボックスを選択します。 EECでは、[!DNL Adobe]管理のプロキシを使用して、編集用にページを読み込みます。 このプロキシでは、iFrameを使用しないサイトでの編集が可能であり、まだ[!DNL Adobe Target] コードを追加していないサイトやページでの編集が可能です。 コードが追加されるまで、サイトにアクティビティは配信されません。 一部のサイトはEEC経由で読み込まれない場合があります。この場合、このオプションをオフにすると、iFrame経由でEECを読み込むことができます。

>[!NOTE]
>
>ローカルでホストされているページまたはネットワーク外でアクセスできないページは、[!DNL Adobe] プロキシ サーバーからアクセスできず、EECで開くことはできません。 こうしたページには、ステージング URL、ユーザー受け入れテスト（UAT）URL またはローカルでホストされているページなどがあります。

+++

## mbox/[!DNL Target]の実装がまだ完了していないページでテストを設定する。 （VEC と EEC） {#section_DE63BCCB5B124E10A71FA579B582A80A}

+++詳細
上記の「iFrame バスティングのサイトのエクスペリエンスを編集できない」を参照してください。

+++

## [!UICONTROL Edit Text]/[!UICONTROL Edit HTML]または[!UICONTROL Change Text]/[!DNL Change HTML]の太字と斜体のテキストスタイルがページに表示されません。 これらのスタイル変更を適用すると、テキストが消えることがあります。 （VEC と EEC） {#section_7A71D6DF41084C58B34C18701E8774E5}

+++詳細
VECで&#x200B;**[!UICONTROL Edit Text]/[!UICONTROL Edit HTML]**&#x200B;を[!UICONTROL A/B Test]または[!UICONTROL Experience Targeting]のアクティビティに使用したり、[!UICONTROL Automated Personalization]または[!UICONTROL Multivariate Test]のアクティビティに&#x200B;**[!UICONTROL Change Text]/[!UICONTROL Change HTML]**&#x200B;を使用してテキストを太字または斜体にする場合、これらのスタイルがページに適用されないか、VECのページからテキストが消える可能性があります。 これは、リッチテキストエディターがこれらのスタイルを適用する方法がweb サイトのマークアップを妨げる可能性があるためです。

この問題が発生した場合、次の手順に従ってください。

1. リッチテキストエディターの「**[!UICONTROL HTML]**」ボタンをクリックして、ソース編集モードに入ります。
1. スタイルテキスト要素を検索します。

   * 太字テキストの場合は、`<strong>`要素を`<b>`に変更します。

   * 斜体の場合は、`<em>`要素を`<i>`に変更します。

+++

## Automated Personalizationアクティビティで、VEC または EEC の画像のスワップが壊れているように見えます。 （VEC と EEC） {#section_88AABFDFE6A3420299B0D508B12A3994}

+++詳細
場所に画像オファーを追加するときは、VEC または EEC の元の画像スペースのフルサイズが利用されます。 配信時には、画像が拡大されずそのまま表示されるので、配信には影響しません。

+++
