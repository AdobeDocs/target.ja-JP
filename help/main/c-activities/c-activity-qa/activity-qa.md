---
keywords: qa;qa モード；アクティビティ qa;qa url;qa url；プレビュー url；プレビュー url
description: Adobeの使用方法を学ぶ [!DNL Target] QA URL：変更されないプレビューリンク、オプションのオーディエンスのターゲット設定、ライブアクティビティデータからセグメント化されたままの QA レポートにより、エンドツーエンドのアクティビティ QA を簡単に実行できます。
title: アクティビティを QA するにはどうすればよいですか？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 4b7c6d82e6988c64ace401d8f749b181b8dc1866
workflow-type: tm+mt
source-wordcount: '1665'
ht-degree: 27%

---

# アクティビティ QA

での QA URL の使用 [!DNL Adobe Target] 変更のないプレビューリンク、オプションのオーディエンスのターゲット設定、ライブアクティビティデータからセグメント化されたままの QA レポートを使用して、エンドツーエンドのアクティビティ QA を簡単に実行できます。

[!UICONTROL Activity QA] では、を完全にテストできます [!DNL Target] ライブで起動する前のアクティビティ。 この [!UICONTROL Activity QA] 機能には次のものが含まれます。

* エクスペリエンスやアクティビティに加えられた更新に関係なく、変更のない、または再生成を必要としないチームメンバーと共有するリンク。 この機能を使用すると、ユーザージャーニー全体を通してアクティビティを完全にテストできます。
* 考慮するオーディエンス条件を任意で選択できるので、マーケターは、オーディエンス条件を満たさなくてもターゲット条件をテストしたり無視したりして、エクスペリエンスのデザインの QA を行えます。
* QA レポートが取り込まれることで、マーケターは、指標が想定どおりに増分され、QA レポートのデータが実稼動環境のレポートとは別に保持されていることを確認できます（A4T 以外のレポートの場合）。
* 単独で、または配信条件を満たす他のライブアクティビティを使用して、エクスペリエンスをプレビューする機能（page/[!DNL Target] リクエスト/オーディエンス）。
* ユーザージャーニー全体を QA の対象にできます。QA リンクを使用してサイトに 1 回アクセスすれば、アクティビティ QA 内でサイト全体を閲覧することができます。セッションを終了するか、 [QA Target ブックマークレット](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 無理に出る [!UICONTROL Activity QA]. この機能は、複数の web ページにまたがるアクティビティがある場合に役立ちます。

  >[!NOTE]
  >
  >この機能は、バージョン 2 の at.js 実装に当てはまります。*x* またはそれ以降。 at.js の場合 1.*x* 実装では、この機能は、訪問者のブラウザーがサードパーティ cookie をブロックしない場合にのみ当てはまります。

## QA URL へのアクセスおよび共有 {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. アクティビティのから [!UICONTROL Overview] ページ、クリック **[!UICONTROL Activity QA]**.

   ![アクティビティ QA リンク](assets/qa_link.png)

1. 以下の設定を指定します。

   ![QA リンク設定オプション](assets/qa_link_config.png)

   * **[!UICONTROL Match audience rules to see experiences]:** オーディエンスのマッチングが機能することを確認したい場合があります。 アクティビティのルックアンドフィールを確認したい場合もあります。 この設定を「オン」にすると、ターゲット条件を満たすテスターのみがエクスペリエンスの表示対象になります。エクスペリエンスのターゲット設定（XT）アクティビティでは、単一のアクティビティ URL が提供されます。表示されるエクスペリエンスは、ユーザーがどのターゲットルールに一致するかによって決まります。

     この設定を「オフ」にした場合は、ユーザーがリンクをクリックすると、ルールに一致するかどうかに関係なく、エクスペリエンスが表示されます。QA を実行する際は、このオーディエンスのターゲット設定を考慮するかしないかを切り替えることができます。

   * **他のすべてのアクティビティのデフォルトコンテンツを表示します：** このオプションを「オン」の位置に切り替えると、他のすべてのアクティビティに対してデフォルトコンテンツが表示されます。 例えば、プレビューは、同じページ上の他のすべてのライブアクティビティを考慮せずに、個別に表示されます。[!DNL Target] リクエスト。

     「オフ」にした場合は、以下の点を考慮します。

      * テストするアクティビティと他のライブアクティビティの間に競合がある場合、 [優先度（標準） ルール](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) 適用。 競合が原因で、QA を実行しようとしているアクティビティを確認できない可能性があります。
      * 指標は表示されたアクティビティについて増分しますが、それは QA レポートの環境内のみです。

1. クリック **[!UICONTROL Done]** 変更を保存します。
1. アクティビティリンクの URL を、テスト用に組織のメンバーと共有します。

   アクティビティのリンクには有効期限がなく、他のユーザーがアクティビティやエクスペリエンスを変更した場合にリンクを再送信する必要はありません。 ただし、から別のオーディエンスを適用する場合は、 [!UICONTROL Audience Library]アクティビティを単に編集するのではなく、新しいリンクが生成されるので、再度共有する必要があります。

   各アクティビティリンク URL （エクスペリエンス A、エクスペリエンス B など）を使用すると、対応するエクスペリエンスからユーザージャーニーを開始できます。 エクスペリエンス用に生成された URL をクリックし、通常のサイトブラウジングに進んで、複数のページ（複数のページが存在する場合）のエクスペリエンスを確認します。 エクスペリエンスが複数のページ（テンプレートテストまたは複数ページテスト）に及んでいる場合でも、エクスペリエンスごとに生成される URL は 1 つだけです。

   以下の理由から、サイト内を移動して他のページを表示できます [!UICONTROL Activity QA] モードは sticky です。 これは、バージョン 2 を使用した at.js 実装に当てはまります。*x* またはそれ以降。 at.js の場合 1.*x* 実装の場合、この状況は、訪問者のブラウザーがサードパーティ cookie をブロックしない場合にのみ当てはまります。

1. アクティビティリンクの URL から生成されたレポートを表示するには、アクティビティの **[!UICONTROL Reports]** ページで、 **[!UICONTROL Settings]** アイコン （  ![icon_gear 画像](assets/icon_gear.png) ）を選択してから、 **[!UICONTROL QA Mode Traffic]** から **[!UICONTROL Environment]** ドロップダウンリスト。

## QA モードからのリリース

[!UICONTROL Activity QA] sticky （粘着性） で web サイトを参照した後 [!UICONTROL Activity QA]、あなたの [!DNL Target] セッションの有効期限が切れる必要があります。期限切れにならない場合は、 [!DNL Target] あなたを解放する [!UICONTROL Activity QA] 一般的な訪問者のようにサイトを表示する前に。

### at.js 2.*x*

サイトに at.js 2 がある場合。*x* デプロイ済み。を使用します [Target QA ブックマークレット](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 無理に出る [!UICONTROL Activity QA]. 次の箇条書きで説明するように、値が空のページをサイトに読み込むと、次のようになります *ではない* at.js 2 の場合は、ブラウザーから QA cookie を削除します。*x* がデプロイされている場合）。

### at.js 1.*x*

サイトに at.js 1 がある場合。*x* デプロイ（を使用する以外） [Target QA ブックマークレット](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)を使用してページをサイトに読み込むことで、手動で強制的に自分を強制終了することもできます。 `at_preview_token` 空の値を持つパラメーター。 例：

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

サイトにが含まれている場合 [[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} をデプロイし、 `at_qa_mode` 空の値を持つパラメーター。 例：

`https://www.mysite.com/?at_qa_mode=`

## 注意点 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* アクティビティ QA がすべてので使用できるようになりました [!DNL Target] アクティビティタイプの「エクスペリエンスのプレビュー URL でAutomated Personalization アクティビティのプレビュー」機能は不要になりました。
* [!UICONTROL Activity QA] アカウントに保存されたアクティビティが多すぎると、保存されたアクティビティのプレビューリンクが読み込まれないことがあります。 プレビューリンクの再試行は機能します。 この状況が引き続き発生しないように、アクティブに使用されなくなった保存済みアクティビティをアーカイブします。
* [!UICONTROL Activity QA] URL は、アクティビティで利用できます。 [レポートソースとしての Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）。 を使用して QA を実行中に発生したヒット [!UICONTROL Activity QA] は、アクティビティのデータがライブになった後もフローする、同じレポートスイートにフローします。
* [!UICONTROL Activity QA] 終了日を過ぎたアーカイブ済みアクティビティまたはアクティビティのコンテンツを表示しない。 終了したアクティビティを非アクティブ化する場合、次の期間にアクティビティを再度保存する必要があります。 [!UICONTROL Activity QA] 仕事に。
* に読み込まれたアクティビティ [!DNL Target Standard/Premium] （送信元： [!DNL Target Classic]（例えば）は QA URL をサポートしません。
* 対象： [!UICONTROL Auto-Allocate] および [!UICONTROL Recommendations] アクティビティ（モデルは、でキャプチャされた訪問の影響を受けません） [!UICONTROL Activity QA].
* アクティビティの作成時に「URL が」指定された場合 [フォームベースのコンポーザーでの絞り込み](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) または [visual Experience Composer のページ配信オプション）](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)の場合、QA URL は次の理由で機能しません [!UICONTROL Activity QA] url パラメーターを追加します。 この問題に対処するには、QA URL をクリックしてサイトに移動し、追加されたパラメーターを URL から削除してから新しい URL を読み込みます。
* at.js 1.*x*, [!UICONTROL Activity QA] safari またはサードパーティ cookie をブロックする別のブラウザーを使用している場合、モードが動的に変更される。 その場合、移動先の URL ごとにプレビューパラメーターを追加する必要があります。 実装している場合も同じです [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}.
* アクティビティで複数のエクスペリエンスオーディエンス（例えば、同じアクティビティに含まれる米国および英国のサイト）を使用する場合、4 つの組み合わせ（エクスペリエンス A/US サイト、エクスペリエンス A/英国のサイト、エクスペリエンス B/米国のサイト、エクスペリエンス B/英国のサイト）に対して QA リンクが生成されません。 エクスペリエンス A とエクスペリエンス B に対する 2 つだけが生成されます。オーディエンス条件を満たすユーザーにのみ、該当のページが表示されます。英国の QA 担当者は、米国サイトを表示できません。
* `at_preview` すべてのパラメーターと値は、既にURLエンコードされています。ほとんどの場合、すべてが期待どおりに動作します。 ただし、クエリ文字列パラメーターを再度エンコードするバランサーまたは web サーバーを読み込む必要がある顧客もあります。

  このダブルエンコーディングにより、 [!DNL Target] は、をデコードしようとします `at_preview_token`, [!DNL Target] 正しいトークン値を抽出できず、プレビューが機能しません。

  [!DNL Adobe] では、IT チームに問い合わせて、すべてのプレビューパラメーターが許可リストに加えるされ、これらの値が一切変換されないことを確認することをお勧めします。

  次の表に、ドメインに許可リストに加えるできるパラメーターを示します。

  | パラメーター | タイプ | 値 | 説明 |
  |--- |--- |--- |--- |
  | `at_preview_token` | 暗号化された文字列 | 必須、デフォルト値なし | QA モードで実行できるキャンペーン ID のリストを含む、暗号化されたエンティティ。 |
  | `at_preview_index` | 文字列 | 空 | パラメーターの形式はです `<campaignIndex>` または `<campaignIndex>_< experienceIndex>`<br>どちらのインデックスも 1 から始まります。 |
  | `at_preview_listed_activities_only` | ブール値（true／false） | デフォルト値：false | &quot;true&quot;の場合、 `at_preview_index` パラメーターで指定されているすべてのキャンペーンが処理されます。<br>「false」の場合、プレビュートークンで指定されていない場合でも、ページのすべてのキャンペーンが処理されます。 |
  | `at_preview_evaluate_as_true_audience_ids` | 文字列 | 空 | 以下の範囲で、常に（ターゲティングおよびレポートレベルで） true と評価される必要がある segmentId のアンダースコア区切り（「_」）リスト [!DNL Target] リクエスト。 |
  | `_AT_Debug` | 文字列 | ウィンドウまたはコンソール | コンソールログまたは新規ウィンドウです。 |
  | `adobe_mc_ref` |  |  | デフォルトのページの参照 URL を新しいページに渡します。バージョン2.1以降で `AppMeasurement.js` 使用する場合、このパラメーター値 [!DNL Adobe Analytics] を新しいページの参照URLとして使用します。 |
  | `adobe_mc_sdid` |  |  | は成功します [!DNL Supplemental Data Id] （SDID）と [!DNL Experience Cloud Org Id] デフォルトページから新しいページへ。 これらの ID を渡すと、 [!UICONTROL Analytics for Target] （A4T）で、を「ステッチ」します。 [!DNL Target] を含むデフォルトページでのリクエスト [!DNL Analytics] 新しいページでリクエストします。 |

* この [!UICONTROL Target QA Mode] UI は、複数ページアクティビティで、エクスペリエンスの最初の URL のみを表示します。 ジャーニーテストを作成し、URL1 から URL2 に移動することを想定しています。 ただし、独立して URL2 にアクセスする場合は、URL1 に対して提供されたすべての URL パラメータをコピーし、 &quot;？&quot;を付けた後でそれらを URL2 に適用します。URL1に表示されるように。
* アカウントに保存されたアクティビティが多すぎると、保存されたアクティビティのアクティビティ QA プレビューリンクが読み込まれないことがあります。プレビューリンクを再試行します。この問題が繰り返し発生するのを防ぐために、アクティブに使用されなくなった保存済みアクティビティをアーカイブします。

## Target JavaScript ライブラリ [!UICONTROL QA Mode] 互換性 {#compatibility}

[!DNL Target] では、次の JavaScript ライブラリをサポートしています。

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja)

次の表に、様々なアクティビティタイプとかどうかを示します [!UICONTROL Activity QA] モードは各ライブラリでサポートされています。

| アクティビティタイプ | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B Test] | ○ | ○ | ○ |
| [!UICONTROL Auto-Allocate] | ○ | ○ | ○ |
| [!UICONTROL Auto-Target] | ○ | ○ | ○ |
| [!UICONTROL Automated Personalization] （AP） | ○ | ○ | ○ |
| [!UICONTROL Experience Targeting] （XT） | ○ | ○ | ○ |
| [!UICONTROL Multivariate Test] （MVT） | ○ | ○ | ○ |
| [!UICONTROL Recommendations] | ○ | ○ | ○ |