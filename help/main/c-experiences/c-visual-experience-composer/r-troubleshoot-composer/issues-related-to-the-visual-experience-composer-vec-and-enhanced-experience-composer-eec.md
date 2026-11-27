---
keywords: ターゲティング；visual experience composer；ホワイトリスト；ホワイトリスト；許可リスト;enhanced visual experience composer;vec;visual experience composerのトラブルシューティング；eec;enhanced experience composer;tls;tls 1.2
description: '[!DNL Target] [!UICONTROL Visual Experience Composer] （VEC）および[!UICONTROL Enhanced Experience Composer] （EEC）で発生することがある問題のトラブルシューティング方法について説明します。'
title: '[!UICONTROL Visual Experience Composer]および[!UICONTROL 拡張Experience Composer]に関連する問題をトラブルシューティングするには、どうすればよいですか？'
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
TQID: 'https://experienceleague.adobe.com/4v7Qe-Yzjke-GceUSRDO2SMZGkxvrkdsSXQt8TR-bic'
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
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1218'
ht-degree: 13%
---
# [!DNL Adobe Target] [!UICONTROL Visual Experience Composer]および[!UICONTROL 拡張Experience Composer]に関する問題のトラブルシューティング {#vec-eec-issues}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL Visual Experience Composer]** （VEC）と&#x200B;**[!UICONTROL Enhanced Experience Composer]** （EEC）の両方に影響する問題を解決する方法について説明します。

>[!ENDSHADEBOX]

[!DNL Target] **[!UICONTROL Visual Experience Composer]** （VEC）および&#x200B;**[!UICONTROL Enhanced Experience Composer]** （EEC）で、特定の条件の下で表示の問題やその他の問題が発生することがあります。 次の項目では、両方のコンポーザーに影響を与える問題とその解決方法について説明します。

## ブラウザーとセキュリティ

### Google Chrome SameSite cookie ポリシー {#samesite}

[!DNL Google Chrome]のSameSite Cookie適用ポリシーは、次のリリースのVECおよびEECに影響します。

>[!NOTE]
>
>次の変更は、3つのリリースすべてに適用されます。 VECは、[VEC Helper拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)がインストールされて有効になっていない限り、サイトのパスワードで保護されたページでは使用できません。 サイトのログイン Cookieはサードパーティ Cookieと見なされるため、**[!UICONTROL 参照]** モードでVEC エディター内のログイン リクエストで送信されません。 唯一の例外は、ログイン Cookieに既に`SameSite=None`属性と`Secure`属性が設定されている場合です。

* **Chrome 94 （2021年9月21日）:** Chrome 94以降のすべてのユーザーに対して、コマンドラインフラグ `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`が削除されました。
* **Chrome 91 （2021年5月25日）:** Chrome 91以降のすべてのユーザーについて、フラグ `#same-site-by-default-cookies`と`#cookies-without-same-site-must-be-secure`が`chrome://flags`から削除されました。 このビヘイビアーはデフォルトで有効になりました。
* **Chrome 80 （2020年8月）:** Chrome 80以降を使用しているすべてのユーザー：

  * アクティビティがサイト上にない場合、アクティビティの編集中に[!DNL Target] ライブラリをダウンロードできません。 ダウンロードコールは、顧客ドメインから保護された[!DNL Adobe] ドメインに対して実行され、未認証として拒否されます。
  * EECは機能しません。`adobemc.com` ドメインのCookieにSameSite属性を設定できません。 この属性がないと、ブラウザーはこれらのCookieを拒否し、EECが失敗します。

+++ ブロックするCookieを決定

SameSite cookie適用ポリシーによってブロックされているCookieを判断するには、[!DNL Chrome]の[!DNL Developer Tools]を使用します。

1. [!DNL Chrome]でVECを表示しているときに、Chrome > **[!UICONTROL 詳細ツール]** > **[!UICONTROL 開発ツール]**&#x200B;の右上隅にある&#x200B;**[!UICONTROL 省略記号]** アイコンをクリックします。
1. 「**[!UICONTROL ネットワーク]**」タブをクリックし、ブロックされたCookieを探します。

   >[!NOTE]
   >
   >「**[!UICONTROL ブロック済みCookie]**」チェックボックスを使用すると、ブロック済みCookieを見つけやすくなります。

+++

+++ Content Security Policy （CSP） ヘッダーは、web サイトの[!DNL Target] ライブラリをブロックします

Web サイトのCSP ヘッダーが[!DNL Target] ライブラリをブロックする場合、web サイトは読み込まれますが、編集は行われません。 [!DNL Target] ライブラリがブロックされていないことを確認してください。

>[!NOTE]
>
>次の情報に加えて、[!DNL Google Chrome]の[Adobe Target VEC Helper ブラウザー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用できます。

![ コンテンツセキュリティポリシーディレクティブに違反したというメッセージが表示された、target.jsに対するブロックされたリクエストを示すブラウザーコンソール ](assets/cps_headers.png)

回避策として、次の図に示すように、[!DNL Requestly] ルールを設定してCSP ヘッダーを削除します。

![要求ダイアログ、HTTP要求と応答のヘッダーを変更し、Content-Security-Policyという名前のルールを使用して、応答からContent-Security-Policy ヘッダーを削除する](assets/cps_headers_2.png)

VEC内でリソースが読み込まれない原因となるヘッダーに対して、同様の[!DNL Requestly] ルールを設定できます。 [!DNL Requestly]でヘッダーを削除する必要がある場合は、次のいずれかの操作を行います。

* VECで開くURLのURL ルールを追加して、これらのURLに対してのみヘッダーが削除されるようにします。
* VECでの編集中にルールを有効にし、VECが使用されていない場合はルールを無効にします。

+++

+++ マルチレベル iframeはサポートされていません

[!DNL Target]はマルチレベル iframeをサポートしていません。 web サイトが子iframeを持つiframeを読み込む場合、at.jsは親iframeとのみ相互作用します。 [!DNL Target] ライブラリは子iframeと相互作用しません。

回避策として、子iframeのURLを使用してエクスペリエンスにページを追加します。

+++

+++ エクスペリエンスは、iFrameを使用するサイトまたは[!DNL Target]実装のないページでは編集できません

この問題に対処するには、**[!UICONTROL Enhanced Experience Composer]** （EEC）を有効にしてください。 **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]**&#x200B;をクリックし、**[!UICONTROL 拡張Experience Composer]**&#x200B;を有効にするチェックボックスを選択します。

EECは[!DNL Adobe]管理プロキシを使用して、編集用にページを読み込みます。 このプロキシを使用すると、iFrameを使用しないサイトや、[!DNL Adobe Target] コードがまだ追加されていないサイトやページで編集できます。 コードが追加されるまで、サイトにアクティビティは配信されません。 一部のサイトがEECを通じて読み込まれない場合があり、このオプションをオフにすると、iFrameを通じてページが読み込まれます。

>[!NOTE]
>
>ローカルでホストされているページとネットワーク外でアクセスできないページは、[!DNL Adobe] プロキシ サーバーからアクセスできず、EECで開くことはできません。 こうしたページには、ステージング URL、ユーザー受け入れテスト（UAT）URL またはローカルでホストされているページなどがあります。

+++

## ページの読み込みと表示

+++ ページを編集すると、ページの代わりにスピナーが表示されます

この状況は、URLに#文字が含まれている場合に発生する可能性があります。 この問題を修正するには、VECまたはEECで&#x200B;**[!UICONTROL 参照]** モードに切り替え、次に&#x200B;**[!UICONTROL 作成]** モードに戻ります。 スピナーの表示が消えて、ページが読み込まれます。

+++

+++ VECまたはEECが壊れているように見えるか、保存されたアクティビティが再度編集されたときに初期化されません

エクスペリエンスを定義した後にWeb サイトがVEC以外で変更された場合、アクティビティを再編集するために開いたときに、以前に実行したアクションのセレクターが見つかりません。 ページは壊れているように表示され、警告は表示されません。

+++

+++ JavaScriptを含むバナーやその他のコンテンツをVECまたはEECに表示できない

デフォルトでは、VECはJavaScript要素をブロックします。 JavaScriptを無効にすると、これらの要素の操作が可能になります。 セットアップするサイトによっては、それでも一部のアイテムの表示が正しくなかったり表示できなかったりする場合があります。

+++

+++ Automated Personalization アクティビティの場合、VECまたはEECで画像の入れ替えが壊れて表示されます

場所に画像オファーを追加するときは、VEC または EEC の元の画像スペースのフルサイズが利用されます。 配信時には、画像が拡大されずそのまま表示されるので、配信には影響しません。

+++

## 結果の編集

+++ ページ上の1つの要素を変更すると、複数の要素が変更されます

同じ DOM 要素 ID がページ内の複数の要素に使用されている場合、それらの要素のいずれかを変更するとその ID の要素がすべて変更されます。 これを防ぐには、各ページでIDを1回だけ使用します。 これは標準の HTML ベストプラクティスです。 詳しくは、[ ページの変更シナリオ ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#vec-scenarios)を参照してください。

+++

+++ 太字や斜体のテキストスタイルが表示されない、またはテキストを編集/HTMLを編集またはテキストを変更/HTMLを変更を適用した後にテキストが表示されない

**[!UICONTROL テキストを編集]**/**[!UICONTROL HTMLを編集]**&#x200B;が&#x200B;**[!UICONTROL A/B テスト]**&#x200B;または&#x200B;**[!UICONTROL エクスペリエンスのターゲット]** アクティビティにVECで使用されている場合、または&#x200B;**[!UICONTROL テキストを変更]**/**[!UICONTROL HTMLを変更]**&#x200B;が&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;または&#x200B;**[!UICONTROL 多変量テスト]** アクティビティに使用されている場合、テキストがページに適用されないか、VECのページテキストから消消削除される可能性があります。 これは、リッチテキストエディターがこれらのスタイルを適用する方法がweb サイトのマークアップを妨げる可能性があるためです。

この問題が発生した場合：

1. リッチテキストエディターの **[!UICONTROL HTML]** ボタンをクリックして、ソース編集モードに入ります。
1. スタイル設定されたテキスト要素を検索します。

   * 太字テキストの場合は、`<strong>`要素を`<b>`に変更します。
   * 斜体の場合は、`<em>`要素を`<i>`に変更します。

+++
