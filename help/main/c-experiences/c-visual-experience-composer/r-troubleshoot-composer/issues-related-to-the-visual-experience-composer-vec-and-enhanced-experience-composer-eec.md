---
keywords: ターゲット設定；visual experience composer；許可リスト；ホワイトリスト；許可リスト;許可リスト；拡張 visual experience composer;vec;visual experience composer のトラブルシューティング；トラブルシューティング；eec；拡張 experience composer;tls;tls 1.2
description: 特定の条件下で  [!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）および [!UICONTROL Enhanced Experience Composer] （EEC）で発生する可能性のある問題のトラブルシューティング方法を説明します。
title: '[!UICONTROL Visual Experience Composer] と [!UICONTROL Enhanced Experience Composer] に関連する問題のトラブルシューティング方法'
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 26%

---

# [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] および [!UICONTROL Enhanced Experience Composer] に関連する問題のトラブルシューティング

特定の条件下で、[!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）と [!UICONTROL Enhanced Experience Composer] （EEC）でディスプレイの問題やその他の問題が発生することがあります。

## Google Chrome の SameSite cookie 実施ポリシーは、VEC および EEC にどのような影響を与えますか？ {#samesite}

+++詳細
次の [!DNL Chrome] リリースを使用する場合は、VEC および EEC に影響を与える変更に注意してください。

>[!NOTE]
>
>次の変更は、以下に示す 3 つの更新すべてに影響します。
>
> * [VEC Helper 拡張機能 *がインストールされ* サイトのパスワードで保護されたページに対して有効になっていない場合 ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)VEC を使用できません。 サイトのログイン cookie はサードパーティ cookie と見なされ、[!UICONTROL Browse] モードの VEC エディター内のログインリクエストでは送信されません。 唯一の例外は、サイトのログイン Cookie に `SameSite=None` 属性と `Secure` 属性が既に設定されている場合です。

**Chrome 94 （2021 年 9 月 21 日（PT））**: Chrome 94 リリース（2021 年 9 月 21 日（PT））で予定されている差し迫った変更は、次の変更がChrome 94 以降のブラウザーバージョンのすべてのユーザーに影響します。

* コマンド ライン フラグ `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` は削除されます。

**Chrome 91 （2021 年 5 月 25 日（PT））**: Chrome 91 リリース（2021 年 5 月 25 日（PT））に実装された変更は、次の変更がChrome 91 以降のブラウザーバージョンのすべてのユーザーに影響します。

* フラグ `#same-site-by-default-cookies` と `#cookies-without-same-site-must-be-secure` が `chrome://flags` から削除されました。 この動作は、デフォルトで有効になっています。

**Chrome 80 （2020 年 8 月）**: 2020 年 8 月に実装された変更により、Chrome 80 以降のブラウザーバージョンを使用するすべてのユーザーは次のようになります。

* アクティビティの編集中は *ダウンロードでき [!DNL Target] せん* アクティビティがサイトにまだ存在しない場合）。 これは、ダウンロード呼び出しが顧客ドメインからセキュリティで保護された [!DNL Adobe] ドメインに対して行われ、未認証として拒否されるためです。

* EEC は、`adobemc.com domain` で Cookie の SameSite 属性を設定できないので、すべてのユーザーに対して *機能しません*。 この属性がない場合、ブラウザーはこれらの Cookie を拒否し、EEC が失敗します。

+++

### ブロックされている Cookie の特定

+++詳細
同じ SameSite cookie 強制ポリシーによってブロックされている cookie を特定するには、[!DNL Chrome] の [!DNL Developer Tools] を使用します。

1. [!DNL Chrome] で VEC を表示しながら [!DNL Developer Tools] にアクセスするには、Chrome/**[!UICONTROL More Tools]**/**[!UICONTROL Developer Tools]** の右上隅にある **[!UICONTROL ellipsis]** アイコンをクリックします。
1. **[!UICONTROL Network]** タブをクリックして、ブロックされた Cookie を探します。

   >[!NOTE]
   >
   >「**[!UICONTROL Has blocked cookies]**」チェックボックスを使用すると、ブロックされた Cookie を見つけやすくなります。

+++

## [!DNL Target] はマルチレベル iframe をサポートしていますか。

+++詳細
[!DNL Target] はマルチレベル iframe をサポートしていません。 Web サイトが子 iframe を持つ iframe を読み込む場合、at.js は親 iframe のみとやり取りします。 [!DNL Target] ライブラリは子 iframe とやり取りしません。

回避策として、子 iframe の URL を持つエクスペリエンスにページを追加できます。

+++

## ページを編集しようとすると、ページではなく、スピナーが表示されます。（VEC と EEC） {#section_313001039F79446DB28C70D932AF5F58}

+++詳細
この状況は、URL に#文字が含まれている場合に発生する可能性があります。 この問題を修正するには、VEC または EEC で [!UICONTROL Browse] モードに切り替えてから、[!UICONTROL Compose] モードに戻します。 スピナーの表示が消えて、ページが読み込まれます。

+++

## コンテンツセキュリティポリシー（CSP）ヘッダーは、Web サイト上の [!DNL Target] ライブラリをブロックします。 （VEC と EEC） {#section_89A30C7A213D43BFA0822E66B482B803}


+++詳細
Web サイトの CSP ヘッダーが [!DNL Target] ライブラリをブロックし、が web サイトを読み込むが編集を妨げる場合、[!DNL Target] ライブラリがブロックされていないことを確認してください。

>[!NOTE]
>
>以下の情報に加えて、[Adobe Target VEC Helper ブラウザー拡張機能 ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) を使用でき [!DNL Google Chrome] す。

![cps_headers image](assets/cps_headers.png)

回避策として、次に示すように、[!DNL Requestly] ルールを設定して CSP ヘッダーを削除できます。

![cps_headers_2 画像 ](assets/cps_headers_2.png)

VEC 内でリソースが読み込まれない任意のヘッダーに対して、同様の [!DNL Requestly] ルールを設定できます。

例え [!DNL Requestly]、ヘッダーを削除する必要がある場合は、次のいずれかを実行する必要があります。

* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。

+++

## 保存されているアクティビティの再編集時に、VEC または EEC が壊れているように見えたり、初期化されなかったりします。（VEC と EEC） {#section_5AC3BA8F8FBB451EA814F298D0645E54}

+++詳細
エクスペリエンスを定義した後に web サイトが VEC 外で変更された場合、アクティビティを再編集用に開いたときに、以前にアクションが実行されたセレクターが見つかりません。 ページは壊れているように表示され、警告は表示されません。

+++

## JavaScript を含む回転バナーなどのコンテンツが VEC または EEC に表示されません。（VEC と EEC） {#section_8B5BE6EB050B42D6A14A054724C41330}

+++詳細
デフォルトでは、VEC はJavaScript要素をブロックします。 JavaScriptを無効にすると、これらの要素を操作できます。 セットアップするサイトによっては、それでも一部のアイテムの表示が正しくなかったり表示できなかったりする場合があります。

+++

## ページ内の 1 つの要素を変更すると、複数の要素が変更されます。（VEC と EEC） {#section_309188ACF34942989BE473F63C5710AF}

+++詳細
ページ上の複数の要素で同じ DOM 要素 ID が使用されている場合、それらの要素のいずれかを変更すると、その ID を持つすべての要素が変更されます。 この現象を予防するには、各ページで ID は 1 回のみ使用するようにしてください。これは、標準のHTML ベストプラクティスです。 詳しくは、[ ページ修正のシナリオ ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB) を参照してください。

+++

## iFrame バスティングのサイトのエクスペリエンスを編集できない。（VEC と EEC） {#section_9FE266B964314F2EB75604B4D7047200}

+++詳細
この問題は、[!UICONTROL Enhanced Experience Composer] （EEC）をイネーブルにすることで解決できます。 **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]** をクリックし、[!UICONTROL Enhanced Experience Composer] を有効にするチェックボックスをオンにします。 EEC は、[!DNL Adobe] 管理プロキシを使用して、編集用にページを読み込みます。 このプロキシを使用すると、iFrame でバスティングサイトを編集したり、コードをまだ追加していないサイトやページ [!DNL Adobe Target] 編集したりできます。 コードが追加されるまで、サイトにアクティビティは配信されません。一部のサイトでは、EEC を介した読み込みが行われない場合があります。その場合は、このオプションのチェックを解除して、iFrame を介して EEC を読み込むことができます。

>[!NOTE]
>
>ローカルでホストされているページまたはネットワーク外からアクセスできないページは、[!DNL Adobe] プロキシサーバーからアクセスできず、EEC で開くこともできません。 こうしたページには、ステージング URL、ユーザー受け入れテスト（UAT）URL またはローカルでホストされているページなどがあります。

+++

## mbox/[!DNL Target] の実装がまだ完了していないページにテストを設定したいのですが、 （VEC と EEC） {#section_DE63BCCB5B124E10A71FA579B582A80A}

+++詳細
上記の「iFrame バーストするサイトのエクスペリエンスを編集できない」を参照してください。

+++

## [!UICONTROL Edit Text]/[!UICONTROL Edit HTML] または [!UICONTROL Change Text]/[!DNL Change HTML] を含む太字や斜体のテキストスタイルがページに表示されません。 これらのスタイル変更を適用すると、テキストが消えることがあります。（VEC と EEC） {#section_7A71D6DF41084C58B34C18701E8774E5}

+++詳細
[!UICONTROL A/B Test] または [!UICONTROL Experience Targeting] アクティビティの VEC で **[!UICONTROL Edit Text]/[!UICONTROL Edit HTML]** を使用したり、[!UICONTROL Automated Personalization] または [!UICONTROL Multivariate Test] アクティビティで **[!UICONTROL Change Text]/[!UICONTROL Change HTML]** を使用してテキストを太字または斜体にすると、これらのスタイルがページに適用されなかったり、VEC のページからテキストが消えたりする場合があります。 これは、リッチテキストエディターがこれらのスタイルを適用する方法により、web サイトのマークアップが妨げられる可能性があるために発生します。

この問題が発生した場合、次の手順に従ってください。

1. リッチテキストエディターの「**[!UICONTROL HTML]**」ボタンをクリックして、ソース編集モードに入ります。
1. スタイルテキスト要素を検索します。

   * 太字テキストの場合は、`<strong>`要素を`<b>`に変更します。

   * 斜体の場合は、`<em>`要素を`<i>`に変更します。

+++

## Automated Personalizationアクティビティで、VEC または EEC の画像のスワップが壊れているように見えます。（VEC と EEC） {#section_88AABFDFE6A3420299B0D508B12A3994}

+++詳細
場所への画像オファーの追加は、VEC または EEC 内の元の画像領域の完全なディメンションを使用します。 配信時には、画像が拡大されずそのまま表示されるので、配信には影響しません。

+++
