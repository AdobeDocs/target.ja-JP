---
keywords: リリースノート、プレリリースノート、今後の機能強化、今後の修正、今後の機能、今後のリリース
description: Adobe Target の以前のリリースに含まれる機能、拡張機能、修正のリストを表示します。
title: 以前のリリースにはどのような機能が含まれていますか。
feature: Release Notes
source-git-commit: 53cd01d2406b8a2f8560fe380ebb5044872e6711
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 77%
---
# 以前のリリースのリリースノート

[!DNL Target Standard/Premium]、[!DNL Target] プラットフォームおよび [!DNL Target] JavaScript ライブラリ（at.js）のリリースノートなど、以前の [!DNL Adobe Target] リリースのリリースノートです。

リリースノートは、リリースの月と年ごとに降順で表示されます。

>[!NOTE]
>
>今月の Target リリース（プラットフォームおよび Target Standard/Premium）について詳しくは、[Target のリリースノート（最新）](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) を参照してください。

## リリースノート - 2024年

### [!DNL Adobe Experience Platform Web SDK] `__view__` 範囲の最適化（2024年10月22日（PT））

2024年7月22日（PT）から 2024年8月15日（PT）の間に、[!DNL Target] チームは `__view__` 範囲を最適化し、アクティビティのインプレッション、訪問、訪問者レポートの精度を向上させました。 この最適化は、自動レンダリングされた提案のレポートデータを自動的に取得することを目的とし、ほとんどのアカウントに対して透過的になる必要があります。

すべての新規の [!DNL Adobe Experience Platform Web SDK] のお客様には、この最適化が有効になります。 ただし、at.js から移行し、以下の実装手順に従っていないお客様の場合、最適化は無効になります。 これらのお客様には、2025年2月3日（PT）までに実装をレビューすることをお勧めします。 この日以降、すべてのお客様に対して最適化が有効になります。 それまでに実装をレビューして調整しないと、以下に示すように、レポートに影響を与える可能性があります。 実装が影響を受けるかどうかを確認する必要がある場合や、実装の調整により多くの時間が必要な場合は、[!DNL Adobe Customer Care] にお問い合わせください。

>[!IMPORTANT]
>
>2025年2月3日（PT）までに実装レビューを完了して問題を解決できない場合は、1 回限りの 6 か月間の延長をリクエストできます。 リクエストは、2025年1月31日（PT）までに送信する必要があります。 アドビがリクエストをレビューし、決定します。

手動の提案レンダリングの場合にこの最適化のメリットを活用するには、[[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank} をレビューして、エクスペリエンスを手動でレンダリングした後や、`applyPropositions` メソッド（またはヘルパーとしての対応する [!DNL Launch] アクション）を使用してエクスペリエンスをレンダリングした際に、通知が送信されるようにします。

エクスペリエンスを手動でレンダリングする際の最も一般的なシナリオは次のとおりです。

* JSON オファーの使用
* [[!UICONTROL &#x200B; フォームベースのExperience Composer]](/help/main/c-experiences/form-experience-composer.md)で作成されたアクティビティでのカスタム決定範囲の使用
* グローバルな`__view__` スコープを使用する[!UICONTROL &#x200B; フォームベースのExperience Composer]を使用して作成されたアクティビティの取得時に`renderDecisions: true`を使用しない

通知が&#x200B;*データ収集*&#x200B;ガイドの[パーソナライズされたコンテンツのレンダリング](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank}に記載されているとおりに実装されていない場合、[!DNL Target] および [Analytics for Target レポート](/help/main/c-integrating-target-with-mac/a4t/a4t.md)（A4T）でレポートデータが欠落している可能性があります。 特定のシナリオでは、レポートデータが取得されないので、トラフィック分割が正しく行われない可能性があります。 または、他のシナリオで、同じイベントが繰り返しレポートされる可能性もあります。

実装に応じて、[!DNL Analytics] および A4T レポートへの影響を確認します。

[!DNL Platform Web SDK] では、エクスペリエンスとパーソナライゼーションのレンダリングに対して、次の 2 つの実装タイプをサポートします。

* **パーソナライゼーションと測定のための単一の呼び出し。**

  当初は推奨されていましたが、[!DNL Platform Web SDK] の単一の呼び出しアプローチは、分割呼び出しアプローチに置き換えられるので廃止される予定です。 アドビでは、すべての新規実装で新しい分割呼び出しアプローチを使用することと、既存のお客様にも分割呼び出し方式に移行することをお勧めします。

  単一の呼び出しアプローチを引き続き使用すると、[!DNL Analytics] レポートに次のような予期しない変更が表示される可能性があります。

  * バウンス数の減少。
  * A4Tと[!UICONTROL &#x200B; ページビュー]のヒットが結合されていないため、[!DNL Analytics]個のeVarとイベントを使用してA4T レポートの特定の分類と相関関係を実行することが困難です。

* **分割呼び出し（ページ上部イベントとページ下部イベントとも呼ばれます）。**

  この実装タイプは、[!DNL Adobe] が推奨する新しい[分割呼び出し実装アプローチ](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank}です。 このアプローチでは、新しい最適化は [!DNL Analytics] や A4T レポートに影響を与えません。

ご質問がある場合は、[アドビカスタマーケア](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。 （KB-2179）

### at.js バージョン 2.11.6（2024年9月29日（PT））

* [!UICONTROL Visual Experience Composer] （VEC）または[!UICONTROL &#x200B; フォームベース Experience Composer]内のリダイレクトオファーで[!DNL Target]が正しく動作しない問題を修正しました。

at.js リリースについて詳しくは、*Adobe Target 開発者ガイド*&#x200B;の [at.js のバージョンの詳細](https://experienceleague.adobe.com/ja/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}を参照してください。

### [!DNL Adobe Customer Journey Analytics] での [!DNL Target] レポート（2024年5月8日（PT））

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank} と [!DNL Target] を統合すれば、最適化プログラムに適した強力な分析機能と時間節約ツールを利用できます。

[!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用する主なメリットは次のとおりです。

* マーケターは、[!DNL Customer Journey Analytics] の成功指標を [!DNL Target] のアクティビティレポートにいつでも動的に適用できます。 アクティビティを実行する前にすべての項目を指定する必要はありません。
* マーケターは、[実験パネル](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}などの [!DNL Customer Journey Analytics] 機能を活用して、web サイトのパーソナライゼーションをさらに分析できます。

詳しくは、[Adobe Customer Journey Analytics での Target レポート](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)を参照してください。

### [!UICONTROL Visual Experience Composer] ヘルパー拡張機能（2024年4月23日）

従来の [!DNL Target] Visual Experience Composer ヘルパー拡張機能は、Manifest V2 を使用して作成されました。 [!DNL Google] では、2024年6月以降、Manifest V2 を使用して作成された拡張機能を許可しなくなると発表しました。 詳しくは、[[!UICONTROL Visual Experience Composer] ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を参照してください。

[!DNL Adobe] では、お客様ができるだけ早く新しい [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)に移行することをお勧めします。

### [!UICONTROL &#x200B; ブラウザー]のオーディエンス属性の`Browser:iPad`と`Browser:iPhone`の更新（2024年4月30日）

| アップデート | 詳細 |
|--- |--- |
| [!UICONTROL &#x200B; ブラウザー:iPad]と[!UICONTROL &#x200B; ブラウザー:iPhone]が、オーディエンスの作成時に使用される[&#x200B; ブラウザー属性](/help/main/c-target/c-audiences/c-target-rules/browser.md)で更新されました。 | [!DNL Adobe Target] を使用すると、ページを訪問した際に特定の[ブラウザーやブラウザーオプション](/help/main/c-target/c-audiences/c-target-rules/browser.md)を使用する訪問者など、[いくつかのカテゴリ属性のいずれかをターゲットに設定](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)できます。<P>[!DNL Target] Standard／Premium 24.3.1（2024年3月4～6日（PT））以降、`Browser:iPad` や `Browser:iPhone` などのターゲット UI を使用して作成されたビルトインのオーディエンスは、`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`、`profile.mobile.isTablet` を使用して [!DNL iPad] と [!DNL iPhone] に対して適切なターゲティングを実行するように更新されます。<P>このアップデートでは、お客様側でのアクションは必要ありません。<p><B>重要</b>：お客様がプロファイルスクリプト（および JavaScript セグメント）で [!DNL iPad] と [!DNL iPhone] を適切にターゲティングを実行するには、**2024年4月30日（PT）**&#x200B;までにお客様が手動で変更を行う必要があります。 手動で変更する必要がある代替設定の例については、[!UICONTROL &#x200B; ブラウザー]のオーディエンス属性[&#128279;](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates)の更新 [!DNL iPad] および [!DNL iPhone] を参照してください。 |

### [!UICONTROL Visual Editing Helper]拡張機能（2024年3月14日）

このリリースには、[!DNL Google Chrome] の [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 拡張機能に関する以下の機能強化および修正が含まれています。

* お客様の web サイトでオーサリングを実行する際の iFrame 読み込みメカニズムを強化しました。
* [!UICONTROL Visual Experience Composer] （VEC）でオーサリングを実行中に拡張機能がCookieを複製する問題を修正しました。

### [!DNL Target] Standard/Premium 24.3.1（2024年3月4～6日（PT））

このリリースには、以下の機能強化および修正が含まれています。

* アクティビティ内の一意のセレクターの数を計算するロジックを修正しました。 （TGT-47878）
* [!UICONTROL Analytics for Target] （A4T）レポートで設定された[!UICONTROL 多変量] （MVT）アクティビティが正しく表示されない問題を修正しました。 （TGT-47490）
* トラフィックのないエクスペリエンスがコントロールエクスペリエンスとして使用された場合の、レポートに表示される警告メッセージを改善しました。 （TGT-47537）
* 多数のバックエンドとローカライゼーションに関する修正を追加しました。

### [!DNL Target] Standard/Premium 24.1.1（2024年1月22日、23日、25日（PT））

このリリースには、以下の機能強化および修正が含まれています。

* 収益目標の指標を持つTarget （A4T）アクティビティのAnalyticsでは、列名として「収益」が表示されず、収益指標がレポートに（$）形式で表示されませんでした。 これは、表面上の問題で、既に修正されています。 （TGT-46995）
* レポートの日付間隔が正しく機能しない問題を修正しました。 （TGT-47396）
* 顧客が[!UICONTROL 詳細アクション &#x200B;] アイコンを使用してアクティビティをアクティブ化または非アクティブ化した後、誤ったステータスが[!UICONTROL すべてのアクティビティ &#x200B;] ページに表示される問題を修正しました。 （TGT-47367）
* 1人の顧客に対して[!UICONTROL 重要属性] レポートが表示されない問題を修正しました。 （TGT-47272）
* 1 人のお客様が「認証が必要」を有効にしようとした際に「無効なペイロード」メッセージが表示される問題を修正しました。 （TGT-47195）
* [!DNL Target] UI の多数のローカライズされた文字列を更新しました。
