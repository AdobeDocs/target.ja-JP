---
description: 以下のリリースノートでは、Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
keywords: リリースノート、プレリリース版
seo-description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
seo-title: Adobe Targetリリースノート（現在）
solution: 'Target '
title: Target リリースノート（現行）
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: ce1758df44740213a2d9011ee43f84cb52f6a29d

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。

## 発表

以下の重要なお知らせに注意してください。

* 2019 年 2 月 21 日に、EMEA、日本、APAC の各地域で Adobe Target インフラストラクチャがアップグレードされ、TLS1.1 以降をサポートしていない古いデバイスまたは Web ブラウザーを使用するエンドユーザーからデータを収集することがなくなりました。同様のアップグレードは、**2019 年 4 月 2 日**&#x200B;に北米地域でも予定されています。TLS 1.2 への移行により、セキュリティが向上します。移行をスムーズに実施するため、IT チームと詳細を確認し、変更の計画を立てることが重要です。詳細については、「[TLS（トランスポート層セキュリティ）暗号化の変更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)」を参照してください。
* [!DNL Target] と [!DNL Adobe Marketing Cloud] は、2019 年 3 月に Microsoft Internet Explorer 11 のサポートを終了します。この変更は [!DNL Target] オーサリングのみに影響し、エクスペリエンス配信には影響しません。Microsoft Edge か別のブラウザーに切り替えてください。詳しくは、「[サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)」を参照してください。

## Target Standard／Premium 19.6.1（2019 年 6 月 26 日）

このリリースには、次の新機能および機能強化が含まれています。

（括弧内の問題番号はアドビ社内で使用されます。）

| 機能／拡張機能 | 説明 |
| --- | --- |
| Visual Experience Composer（VEC） | **新しいVECメニューオプション**:VECでページ要素をクリックすると、その要素タイプで使用できるオプションがメニューに表示されます。<ul><li>[!UICONTROL スタイル/背景] オプションを使用して、選択した要素の背景画像と色を変更できるようになりました。（TGT-15001）</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**クリック追跡の改善**:VECおよびシングルページアプリケーション（SPA） VEC内でのクリック追跡の設定プロセスを改善しました。<ul><li>クリック追跡で使用する要素を選択する際、使用可能なすべてのエレメントの名前が右側の変更パネルに表示され、目的の要素をすばやく簡単に選択できます。</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. この番号にマウスポインターを置くと、選択したすべての要素の名前を表示できます。（TGT-33878）</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| シングルページアプリケーション Visual Experience Composer （SPA VEC） | **ガイド付きワークフロー**:新しいガイド付きワークフローは、単一ページアプリ用にアクティビティを実行して実行するために、ページ配信ルール設定をどのように設定すべきかを理解するのに役立ちます。(TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**コピーの変更**:SPA VECを使用して変更を定義し、その変更を単一ページアプリの他のビューで使用するためにコピーできるようになりました。(TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| Mobile Visual Experience Composer | **複数のアプリケーションバージョン**:モバイルアプリの複数バージョンのアクティビティを作成できるようになりました。これにより、バージョンが類似していて、アプリケーションのUIを大幅に変更する必要がなくなります。(TGT-34231)<br>See "Manage multiple app versions" in [Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#using-the-mobile-vec). |
| ![Premiumバッジ](/help/assets/premium.png) 自動パーソナライゼーション（AP）および自動ターゲット | **コントロールとしての特定のエクスペリエンス**:APまたは自動ターゲットアクティビティの作成時に、コントロールとして使用するエクスペリエンスを選択できます。この機能により、アクティビティで設定されたトラフィック配分の割合に基づいて、特定のエクスペリエンスにコントロールトラフィック全体をルーティングできます。その後、その1つのエクスペリエンスへのトラフィックを制御するために、パーソナライズされたトラフィックのパフォーマンスレポートを評価できます。現在の制御オプション（ランダムに提供されるエクスペリエンス）は引き続き使用できます。(TGT-32801, TGT-26572, &amp; TGT-26571)<br>See [Select the control for your Automated Personalization or Auto-Target Activity](/help/c-activities/t-automated-personalization/experience-as-control.md). Note that there is a [current known issue](/help/r-release-notes/known-issues-resolved-issues.md) with this feature.<br>**パーソナライゼーションインサイトレポート**:訪問者が特定の場所で特定のコンテンツ部分を表示したときに、属性にわかりやすい名前を付けると、より有意義な情報を提供します。(TGT-33421 &amp; TGT-34957)<br>See [Data collection for the Target personalization algorithms](/help/c-activities/t-automated-personalization/ap-data.md). |
| ![Premiumバッジ](/help/assets/premium.png) の推奨事項 | 「最近表示したアイテム」ロジックを作成する際、「以前購入された品目をレコメンデーション」を使用できます。（TGT-34030）<br>詳しくは、「条件を作成»の?«最近表示した項目?[](/help/c-recommendations/c-algorithms/create-new-algorithm.md#previously-purchased) |
| Google Chromeサイトのcookieポリシー | Googleは最近、2019年7月30日リリース用に設定されているChrome76から開始し、開発者はWebサイト間で動作できるcookieとユーザーを追跡できるcookieを明示的に指定する必要があります。<br>業界では、消費者向けにより安全なWebを作成するために、Targetは、訪問者に対して、ミーティング中にパーソナライズされたエクスペリエンスを配信し、訪問者のプライバシー期待を超えていることに積極的にコミットされています。<br>[Google Chrome SAeSite cookieポリシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md)を参照してください。 |

## at. jsバージョン2.1.0（2019年6月3日）

at. js2.1.0では、以下のエキサイティングな機能をお知らせします。

| 機能／拡張機能 | 説明 |
| --- | --- |
| アドビオプトインサポート | Adobe Opt-In は、アドビソリューションと同意管理プラットフォームの統合を簡略化する方法です。<br>アドビのオプトインについて詳しくは [、プライバシーおよび一般的なデータ保護規則（GGPR）](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)を参照してください。 |
| 業界標準CSP準拠 | at. jsは、eval（）を使用してJavaScriptを実行しなくなりました。 |
| クライアント側の分析ログ | 顧客側またはサーバー側でAnalyticsデータをAdobe Analyticsに送信する方法をユーザーが自由に制御できます。<br>詳しくは、実装する前に [、クライアント側のAnalyticsログを参照](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side)**&#x200B;してください。 |
| 通知の送信 | Allows developers to send notifications when an experience is rendered by their code instead of using `applyOffer()` or `applyOffers()`.<br>詳しくは [、adobe. target. sendNotifications（options）](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)を参照してください。 |
| ファイルサイズの削減 | at. jsのサイズは24%減少します。ファイルサイズが小さければページの読み込みパフォーマンスが向上し、ページにat. jsをダウンロードする時間が短縮されます。 |
| at. jsドキュメントの更新 | For a full list of all articles updated due to the at.js 2.1.0 release, see the June 3, 2019 entries in [Documentation changes](/help/r-release-notes/doc-change.md). |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは、「[ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](../r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは [、Experience Cloudリリースノート](https://marketing.adobe.com/resources/help/en_US/whatsnew/)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority 製品アップデート（<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html）にサインアップします。 |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |