---
description: Visual Experience Composer（VEC）と拡張 Experience Composer（EEC）では、特定の条件下で表示の問題が発生することがあります。
keywords: ターゲット設定;visual experience composer;ホワイトリスト;ホワイトリスト;拡張 visual experience composer;vec;visual experience composer のトラブルシューティング;トラブルシューティング;eec;拡張 experience composer;tls;tls 1.2
seo-description: Visual Experience Composer（VEC）と拡張 Experience Composer（EEC）では、特定の条件下で表示の問題が発生することがあります。
seo-title: Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング
solution: 'Target '
title: Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング
uuid: 93f646d9-fcbc-43f0-9f84-0ce8e486ff7f
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング{#troubleshooting-issues-related-to-the-visual-experience-composer-and-enhanced-experience-composer}

Visual Experience Composer（VEC）と拡張 Experience Composer（EEC）では、特定の条件下で表示の問題が発生することがあります。

## ページを編集しようとすると、ページではなく、スピナーが表示されます。（VEC と EEC）{#section_313001039F79446DB28C70D932AF5F58}

この問題は、URL に # 文字が含まれている場合に発生することがあります。この問題を修正するには、Visual Experience Composer を「参照」モードに切り替えて、その後「構成」モードに戻します。スピナーの表示が消えて、ページが読み込まれます。

## コンテンツセキュリティポリシー（CSP）ヘッダーによって、Web サイト上で Target ライブラリがブロックされます。（VEC と EEC）{#section_89A30C7A213D43BFA0822E66B482B803}

Web サイトの CSP ヘッダーによって Target ライブラリがブロックされることにより、Web サイトは読み込まれるものの編集できない場合は、Target ライブラリがブロックされないようにします。

>[!NOTE]
>
>以下の情報に加えて、Google Chrome 用 [Adobe Target VEC ヘルパーブラウザー拡張機能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用できます。

![](assets/cps_headers.png)

次のように、Requestly ルールを設定して CSP ヘッダーを削除することで対処できます。

![](assets/cps_headers_2.png)

VEC 内でのリソースの読み込みを妨げているヘッダーに、同様の Requestly ルールを設定できます。

Requestly の場合、ヘッダーを削除する必要があるときは必ず次のいずれかを実行する必要があります。

* VEC で開く URL の URL ルールを追加して、それらの URL についてのみヘッダーが削除されるようにします。
* VEC で編集するときにはルールを有効にし、VEC を使用していないときはルールを無効にします。

## 保存されているアクティビティの再編集時に、VEC または EEC が壊れているように見えたり、初期化されなかったりします。（VEC と EEC）{#section_5AC3BA8F8FBB451EA814F298D0645E54}

Web サイトが、エクスペリエンスの定義後に Visual Experience Composer 外で変更された場合、それよりも前にアクションがおこなわれたセレクターは、アクティビティを再編集で開くときに検出できません。ページは壊れているように表示され、警告は表示されません。

## JavaScript を含む回転バナーなどのコンテンツが VEC または EEC に表示されません。（VEC と EEC）{#section_8B5BE6EB050B42D6A14A054724C41330}

デフォルトでは、Visual Experience Composer は JavaScript 要素をブロックします。Visual Experience Composer の設定で JavaScript を無効にすると、これらの要素を使用できます。セットアップするサイトによっては、それでも一部のアイテムの表示が正しくなかったり表示できなかったりする場合があります。

## ホストした target.js ファイルが読み込みに失敗し、後続のページがリロードされます。（VEC と EEC）{#section_87F6418C2CD142A7B4D1E7037935F81F}

この問題は、バージョン 57 より前の mbox.js（つまり、バージョン 56 以前）の場合に発生します。

すべての VEC ユーザーが[最新バージョンの mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) にアップグレードするか、少なくともバージョン 57 にアップグレードすることをお勧めします。また、[at.js への移行](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)も検討してください。

## ページ内の 1 つの要素を変更すると、複数の要素が変更されます。（VEC と EEC）{#section_309188ACF34942989BE473F63C5710AF}

同じ DOM 要素 ID がページ内の複数の要素に使用されている場合、それらの要素のいずれかを変更するとその ID の要素がすべて変更されます。この現象を予防するには、各ページで ID は 1 回のみ使用するようにしてください。これは標準の HTML ベストプラクティスです。詳しくは、[ページ修正のシナリオ](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)を参照してください。

## iFrame バスティングのサイトのエクスペリエンスを編集できない。（VEC と EEC）{#section_9FE266B964314F2EB75604B4D7047200}

この問題は、拡張 Experience Composer を有効にすることで対処できます。**[!UICONTROL セットアップ]** / **[!UICONTROL 環境設定]**をクリックし、拡張 Experience Composer を有効にするチェックボックスをオンにします。拡張 Experience Composer は、編集するページの読み込みに、アドビが管理するプロキシを使用します。これにより、iFrame バスティングのサイトの編集と、まだ Adobe Target コードを追加していないサイトとページの編集が可能になります。コードが追加されるまで、サイトにアクティビティは配信されません。サイトによっては、拡張 Experience Composer を介して読み込むことができない場合があります。その場合は、このオプションをオフにして、iFrame を介して Visual Experience Composer を読み込むことができます。 []

>[!NOTE]
>
>ローカルでホストされているページや、ネットワーク外からアクセスできないページは、アドビのプロキシサーバーにアクセスできず、EEC で開くことができません。こうしたページには、ステージング URL、ユーザー受け入れテスト（UAT）URL またはローカルでホストされているページなどがあります。

## mbox/target をまだ実装していないページでテストを設定したい。（VEC と EEC）{#section_DE63BCCB5B124E10A71FA579B582A80A}

上記の「iFrame バスティングのサイトのエクスペリエンスを編集できない」を参照してください。

## 「テキスト／HTML を編集」または「テキスト／HTML を変更」でテキストスタイルの太字および斜体がページで表示されません。これらのスタイル変更を適用すると、テキストが消えることがあります。（VEC と EEC）{#section_7A71D6DF41084C58B34C18701E8774E5}

Visual Experience Composer で A/B またはエクスペリエンスターゲット設定アクティビティに「**[!UICONTROL テキスト／HTML を編集]**」を使用したり、自動パーソナライゼーションまたは多変量分析テストアクティビティに「**テキスト／HTML を変更]」を使用して、テキストに太字や斜体を設定すると、Visual Experience Composer でこれらのスタイルがページに適用できないか、ページからテキストが消えることがあります。[!UICONTROL **これは、リッチテキストエディターでこれらのスタイルを適用する方法が Web サイトのマークアップに影響を与える可能性があるためです。

この問題が発生した場合、次の手順に従ってください。

1. リッチテキストエディターの **[!UICONTROL HTML]ボタンをクリックして、ソース編集モードに入ります。**
1. スタイルテキスト要素を検索します。

   * 太字テキストの場合は、`<strong>`要素を`<b>`に変更します。

   * 斜体の場合は、`<em>`要素を`<i>`に変更します。

## 自動パーソナライゼーションアクティビティで、VEC または EEC の画像のスワップが壊れているように見えます。（VEC と EEC）{#section_88AABFDFE6A3420299B0D508B12A3994}

場所に画像オファーを追加するときは、VEC または EEC の元の画像スペースのフルサイズが利用されます。配信時には、画像が拡大されずそのまま表示されるので、配信には影響しません。
