---
keywords: qa;qa モード；アクティビティ qa;qa url;qa url；プレビュー url；プレビュー url
description: Adobe [!DNL Target] QA URL を使用して、変更されないプレビューリンク、オプションのオーディエンスのターゲット設定、ライブアクティビティデータからセグメント化されたままの QA レポートで、簡単なエンドツーエンドのアクティビティ QA を実行する方法を説明します。
title: アクティビティを QA するにはどうすればよいですか？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 4b7c6d82e6988c64ace401d8f749b181b8dc1866
workflow-type: tm+mt
source-wordcount: '1665'
ht-degree: 27%

---

# アクティビティ QA

[!DNL Adobe Target] の QA URL を使用すると、変更のないプレビューリンク、オプションのオーディエンスのターゲット設定、ライブアクティビティデータからセグメント化されたままの QA レポートで、エンドツーエンドの簡単なアクティビティ QA を実行できます。

[!UICONTROL Activity QA] では、[!DNL Target] アクティビティを完全にテストしてからライブで起動できます。 [!UICONTROL Activity QA] の機能が含まれます。

* エクスペリエンスやアクティビティに加えられた更新に関係なく、変更のない、または再生成を必要としないチームメンバーと共有するリンク。 この機能を使用すると、ユーザージャーニー全体を通してアクティビティを完全にテストできます。
* 考慮するオーディエンス条件を任意で選択できるので、マーケターは、オーディエンス条件を満たさなくてもターゲット条件をテストしたり無視したりして、エクスペリエンスのデザインの QA を行えます。
* QA レポートが取り込まれることで、マーケターは、指標が想定どおりに増分され、QA レポートのデータが実稼動環境のレポートとは別に保持されていることを確認できます（A4T 以外のレポートの場合）。
* 単独で、または配信条件（ページ/[!DNL Target] リクエスト/オーディエンス）を満たす他のライブアクティビティを使用して、エクスペリエンスをプレビューする機能。
* ユーザージャーニー全体を QA の対象にできます。QA リンクを使用してサイトに 1 回アクセスすれば、アクティビティ QA 内でサイト全体を閲覧することができます。セッションを終了するか、[QA Target ブックマークレット ](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) を使用して強制的に [!UICONTROL Activity QA] を停止するまで、アクティビティ QA を実行し続けます。 この機能は、複数の web ページにまたがるアクティビティがある場合に役立ちます。

  >[!NOTE]
  >
  >この機能は、バージョン 2 の at.js 実装に当てはまります。*x* 以降 at.js の場合 1.*x* 実装では、この機能は、訪問者のブラウザーがサードパーティ cookie をブロックしない場合にのみ当てはまります。

## QA URL へのアクセスおよび共有 {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. アクティビティの [!UICONTROL Overview] ページで、「**[!UICONTROL Activity QA]**」をクリックします。

   ![アクティビティ QA リンク](assets/qa_link.png)

1. 以下の設定を指定します。

   ![QA リンク設定オプション](assets/qa_link_config.png)

   * **[!UICONTROL Match audience rules to see experiences]:** オーディエンスマッチングの動作を確認したい場合があります。 アクティビティのルックアンドフィールを確認したい場合もあります。 この設定を「オン」にすると、ターゲット条件を満たすテスターのみがエクスペリエンスの表示対象になります。エクスペリエンスのターゲット設定（XT）アクティビティでは、単一のアクティビティ URL が提供されます。表示されるエクスペリエンスは、ユーザーがどのターゲットルールに一致するかによって決まります。

     この設定を「オフ」にした場合は、ユーザーがリンクをクリックすると、ルールに一致するかどうかに関係なく、エクスペリエンスが表示されます。QA を実行する際は、このオーディエンスのターゲット設定を考慮するかしないかを切り替えることができます。

   * **他のすべてのアクティビティにデフォルトコンテンツを表示：** このオプションを「オン」の位置に切り替えると、他のすべてのアクティビティにデフォルトコンテンツが表示されます。 例えば、プレビューは、同じページ/[!DNL Target] リクエスト上の他のすべてのライブアクティビティを考慮せずに、単独で表示されます。

     「オフ」にした場合は、以下の点を考慮します。

      * テストするアクティビティと他のライブアクティビティの間に競合がある場合は、[ 通常の優先度ルール ](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) が適用されます。 競合が原因で、QA を実行しようとしているアクティビティを確認できない可能性があります。
      * 指標は表示されたアクティビティについて増分しますが、それは QA レポートの環境内のみです。

1. 「**[!UICONTROL Done]**」をクリックして変更を保存します。
1. アクティビティリンクの URL を、テスト用に組織のメンバーと共有します。

   アクティビティのリンクには有効期限がなく、他のユーザーがアクティビティやエクスペリエンスを変更した場合にリンクを再送信する必要はありません。 ただし、アクティビティを単に編集するのではなく、[!UICONTROL Audience Library] ーディエンスから異なるオーディエンスを適用する場合は、新しいリンクが生成されるので、再度共有する必要があります。

   各アクティビティリンク URL （エクスペリエンス A、エクスペリエンス B など）を使用すると、対応するエクスペリエンスからユーザージャーニーを開始できます。 エクスペリエンス用に生成された URL をクリックし、通常のサイトブラウジングに進んで、複数のページ（複数のページが存在する場合）のエクスペリエンスを確認します。 エクスペリエンスが複数のページ（テンプレートテストまたは複数ページテスト）に及んでいる場合でも、エクスペリエンスごとに生成される URL は 1 つだけです。

   [!UICONTROL Activity QA] モードはスティッキーなので、サイトを移動して他のページを表示できます。 これは、バージョン 2 を使用した at.js 実装に当てはまります。*x* 以降 at.js の場合 1.*x* 実装では、この状況は、訪問者のブラウザーがサードパーティ cookie をブロックしない場合にのみ当てはまります。

1. アクティビティリンクの URL から生成されたレポートを表示するには、アクティビティの **[!UICONTROL Reports]** ページをクリックし、**[!UICONTROL Settings]** アイコン（![icon_gear image](assets/icon_gear.png)）をクリックして、「**[!UICONTROL Environment]**」ドロップダウンリストから「**[!UICONTROL QA Mode Traffic]**」を選択します。

## QA モードからのリリース

[!UICONTROL Activity QA] がベタベタしている。 [!UICONTROL Activity QA] で web サイトを閲覧した後、[!DNL Target] セッションの有効期限が切れるか、通常の訪問者のようにサイト [!DNL Target] 表示する前に [!UICONTROL Activity QA] からリリースする必要があります。

### at.js 2.*x*

サイトに at.js 2 がある場合。*x* がデプロイされている場合は、[Target QA ブックマークレット ](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) を使用して、自分を [!UICONTROL Activity QA] から強制的に除外します。 次の箇条書きで説明するように、空の値を使用してサイトにページを読み込む *、at.js 2 の場合にブラウザーから QA cookie が削除されるわけではありません*。*x* がデプロイされている場合）。

### at.js 1.*x*

サイトに at.js 1 がある場合。*x* をデプロイすると、[Target QA ブックマークレット ](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) を使用する以外に、`at_preview_token` パラメーターに値が空のページをサイトに読み込むことで、手動で強制的に実行することもできます。 例：

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

サイトに [[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} がデプロイされている場合は、空の値を持つ `at_qa_mode` パラメーターを含むページをサイトに読み込むことで、手動で強制的に実行できます。 例：

`https://www.mysite.com/?at_qa_mode=`

## 注意点 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* アクティビティ QA を [!DNL Target] のすべてのアクティビティタイプで使用できるようになったので、「エクスペリエンスプレビュー URL でAutomated Personalization アクティビティをプレビュー」機能は不要になりました。
* アカウントに保存 [!UICONTROL Activity QA] れたアクティビティが多すぎると、保存したアクティビティのプレビューリンクが読み込まれないことがあります。 プレビューリンクの再試行は機能します。 この状況が引き続き発生しないように、アクティブに使用されなくなった保存済みアクティビティをアーカイブします。
* [!UICONTROL Activity QA] URL は、[Analytics をレポートソースとして ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）使用するアクティビティで利用できます。 同じレポートスイートに対して [!UICONTROL Activity QA] フローを使用して QA を実行する際に生成されたヒットです。このレポートスイートでは、アクティビティのデータは、アクティビティがライブになった後もフローします。
* [!UICONTROL Activity QA] には、アーカイブされたアクティビティや終了日を過ぎたアクティビティのコンテンツは表示されません。 終了したアクティビティを非アクティブ化した場合、[!UICONTROL Activity QA] が機能するには、アクティビティを再度保存する必要があります。
* （[!DNL Target Classic] などから） [!DNL Target Standard/Premium] に読み込まれたアクティビティは QA URL をサポートしません。
* [!UICONTROL Auto-Allocate] および [!UICONTROL Recommendations] アクティビティでは、モデルは [!UICONTROL Activity QA] でキャプチャされた訪問の影響を受けません。
* アクティビティの作成時に「URL は」を指定した場合 [ フォームベース Composer で絞り込み ](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)Visual Experience Composer でページ配信オプション [](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)、は URL パラメーターを追加するので、QA URL は機能し [!UICONTROL Activity QA] せん。 この問題に対処するには、QA URL をクリックしてサイトに移動し、追加されたパラメーターを URL から削除してから新しい URL を読み込みます。
* at.js 1.*x*、Safari またはサードパーティの Cookie をブロックする別のブラウザーを使用している場合、[!UICONTROL Activity QA] モードが動的に固定されない。 その場合、移動先の URL ごとにプレビューパラメーターを追加する必要があります。 [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank} を実装している場合も同じです。
* アクティビティで複数のエクスペリエンスオーディエンス（例えば、同じアクティビティに含まれる米国および英国のサイト）を使用する場合、4 つの組み合わせ（エクスペリエンス A/US サイト、エクスペリエンス A/英国のサイト、エクスペリエンス B/米国のサイト、エクスペリエンス B/英国のサイト）に対して QA リンクが生成されません。 エクスペリエンス A とエクスペリエンス B に対する 2 つだけが生成されます。オーディエンス条件を満たすユーザーにのみ、該当のページが表示されます。英国の QA 担当者は、米国サイトを表示できません。
* `at_preview` すべてのパラメーターと値は、既にURLエンコードされています。ほとんどの場合、すべてが期待どおりに動作します。 ただし、クエリ文字列パラメーターを再度エンコードするバランサーまたは web サーバーを読み込む必要がある顧客もあります。

  このダブルエンコーディングにより、[!DNL Target] が `at_preview_token` をデコードしようとすると、正しいトークン値を抽出で [!DNL Target] ず、プレビューが機能しません。

  [!DNL Adobe] では、IT チームに問い合わせて、これらの値が一切変換されないように、すべてのプレビューパラメーターが許可リストに加えるされていることを確認することをお勧めします。

  次の表に、ドメインに許可リストに加えるできるパラメーターを示します。

  | パラメーター | タイプ | 値 | 説明 |
  |--- |--- |--- |--- |
  | `at_preview_token` | 暗号化された文字列 | 必須、デフォルト値なし | QA モードで実行できるキャンペーン ID のリストを含む、暗号化されたエンティティ。 |
  | `at_preview_index` | 文字列 | 空 | パラメーターの形式は `<campaignIndex>` または `<campaignIndex>_< experienceIndex>`<br> 両方のインデックスは 1 で始まります。 |
  | `at_preview_listed_activities_only` | ブール値（true／false） | デフォルト値：false | &quot;true&quot;の場合、 `at_preview_index` パラメーターで指定されているすべてのキャンペーンが処理されます。<br>「false」の場合、プレビュートークンで指定されていない場合でも、ページのすべてのキャンペーンが処理されます。 |
  | `at_preview_evaluate_as_true_audience_ids` | 文字列 | 空 | [!DNL Target] リクエストのスコープで、常に（ターゲティングおよびレポートレベルで） true と評価される必要がある segmentId のアンダースコア区切り（「_」）リスト。 |
  | `_AT_Debug` | 文字列 | ウィンドウまたはコンソール | コンソールログまたは新規ウィンドウです。 |
  | `adobe_mc_ref` |  |  | デフォルトのページの参照 URL を新しいページに渡します。バージョン2.1以降で `AppMeasurement.js` 使用する場合、このパラメーター値 [!DNL Adobe Analytics] を新しいページの参照URLとして使用します。 |
  | `adobe_mc_sdid` |  |  | デフォルトページから新しいページに [!DNL Supplemental Data Id] （SDID）と [!DNL Experience Cloud Org Id] を渡します。 これらの ID を渡すと、[!UICONTROL Analytics for Target] （A4T）は、デフォルトページの [!DNL Target] リクエストと新しいページの [!DNL Analytics] リクエストを「ステッチ」できます。 |

* [!UICONTROL Target QA Mode] UI は、複数ページアクティビティでのエクスペリエンスの最初の URL のみを表示します。 ジャーニーテストを作成し、URL1 から URL2 に移動することを想定しています。 ただし、独立して URL2 にアクセスする場合は、URL1 に対して提供されたすべての URL パラメータをコピーし、 &quot;？&quot;を付けた後でそれらを URL2 に適用します。URL1に表示されるように。
* アカウントに保存されたアクティビティが多すぎると、保存されたアクティビティのアクティビティ QA プレビューリンクが読み込まれないことがあります。プレビューリンクを再試行します。この問題が繰り返し発生するのを防ぐために、アクティブに使用されなくなった保存済みアクティビティをアーカイブします。

## Target JavaScript ライブラリ [!UICONTROL QA Mode] 互換性 {#compatibility}

[!DNL Target] は、次のJavaScript ライブラリをサポートしています。

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja)

次の表に、様々なアクティビティタイプと、各ライブラリで [!UICONTROL Activity QA] のモードがサポートされているかどうかを示します。

| アクティビティタイプ | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B Test] | ○ | ○ | ○ |
| [!UICONTROL Auto-Allocate] | ○ | ○ | ○ |
| [!UICONTROL Auto-Target] | ○ | ○ | ○ |
| [!UICONTROL Automated Personalization] （AP） | ○ | ○ | ○ |
| [!UICONTROL Experience Targeting] （XT） | ○ | ○ | ○ |
| [!UICONTROL Multivariate Test] （MVT） | ○ | ○ | ○ |
| [!UICONTROL Recommendations] | ○ | ○ | ○ |