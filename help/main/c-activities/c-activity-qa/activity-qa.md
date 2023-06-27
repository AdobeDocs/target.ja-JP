---
keywords: qa;qa モード；アクティビティ qa;qa url;qa url；プレビュー url；プレビュー url
description: Adobe [!DNL Target] QA URL を使用すると、変更されることのないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化された QA レポートを含む、エンドツーエンドの簡単なアクティビティ QA を実行できます。
title: QA アクティビティの方法
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 30ce57ffacabb9625b4668c5482646d4acdb1e55
workflow-type: tm+mt
source-wordcount: '1668'
ht-degree: 38%

---

# アクティビティ QA

での QA URL の使用 [!DNL Adobe Target] 変更されないプレビューリンク、オプションのオーディエンスターゲティング、実際のアクティビティデータからセグメント化された QA レポートを使用して、簡単にエンドツーエンドのアクティビティ QA を実行できます。

[!UICONTROL アクティビティ QA] を [!DNL Target] アクティビティを開始する前に有効にしておく必要があります。 この [!UICONTROL アクティビティ QA] には次の機能が含まれます。

* エクスペリエンスやアクティビティが更新されても変更されることがなく、再生成の必要がないリンクをチームのメンバーと共有できる. この機能を使用すると、ユーザージャーニー全体にわたってアクティビティを完全にテストできます。
* 考慮するオーディエンス条件を任意で選択できるので、マーケティング担当者は、オーディエンス条件を満たさなくてもターゲット条件をテストしたり無視したりして、エクスペリエンスのデザインの QA をおこなえる.
* QA レポートが取り込まれることで、マーケティング担当者は、指標が想定どおりに増分され、QA レポートのデータが実稼動環境のレポートとは別に保持されていることを確認できます（A4T 以外のレポートの場合）。
* エクスペリエンスを単独で、または配信条件 ( ページ/[!DNL Target] リクエスト/オーディエンス ) で利用できます。
* ユーザージャーニー全体を QA の対象にできます。QA リンクを使用してサイトに 1 回アクセスすれば、アクティビティ QA 内でサイト全体を閲覧することができます。セッションを終了するか、 [QA Target ブックマークレット](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 無理に引き出す [!UICONTROL アクティビティ QA]. この機能は、複数の Web ページにまたがるアクティビティがある場合に役立ちます。

  >[!NOTE]
  >
  >この機能は、バージョン 2 の at.js 実装に当てはまります。*x* または後で。 at.js 1.*x* 実装の場合、この機能は、訪問者のブラウザーでサードパーティ cookie がブロックされない場合にのみ当てはまります。

## QA URL へのアクセスおよび共有 {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. アクティビティの [!UICONTROL 概要] ページ、クリック **[!UICONTROL アクティビティ QA]**.

   ![アクティビティ QA リンク](assets/qa_link.png)

1. 以下の設定を指定します。

   ![QA リンク設定オプション](assets/qa_link_config.png)

   * **[!UICONTROL オーディエンスルールを一致させてエクスペリエンスを確認する]:** オーディエンスの一致が機能することを確認したい場合があります。 アクティビティのルックアンドフィールを確認したい場合もあります。 この設定を「オン」にすると、ターゲット条件を満たすテスターのみがエクスペリエンスの表示対象になります。エクスペリエンスのターゲット設定（XT）アクティビティでは、単一のアクティビティ URL が提供されます。表示されるエクスペリエンスは、ユーザーがどのターゲットルールに一致するかによって決まります。

     この設定を「オフ」にした場合は、ユーザーがリンクをクリックすると、ルールに一致するかどうかに関係なく、エクスペリエンスが表示されます。QA を実行する際は、このオーディエンスのターゲット設定を考慮するかしないかを切り替えることができます。

   * **他のすべてのアクティビティのデフォルトコンテンツを表示：** このオプションを「オン」に切り替えると、他のすべてのアクティビティのデフォルトコンテンツが表示されます。 例えば、同じページ上の他のすべてのライブアクティビティを考慮せずに、プレビューが単独で表示されます。[!DNL Target] リクエスト。

     「オフ」にした場合は、以下の点を考慮します。

      * テスト対象のアクティビティとその他のライブアクティビティとの間で衝突が発生する場合は、[通常の優先順位ルール](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)が適用されます。衝突のため、QA 対象のアクティビティが表示されない可能性があります。
      * 指標は表示されたアクティビティについて増分しますが、それは QA レポートの環境内のみです。

1. 「**[!UICONTROL 完了]**」をクリックして変更を保存します。
1. アクティビティリンク URL を組織のメンバーと共有してテストします。

   アクティビティリンクは期限切れになることはなく、アクティビティやエクスペリエンスを変更した場合でも、リンクを再送信する必要はありません。 ただし、 [!UICONTROL オーディエンスライブラリ]を使用すると、アクティビティを単に編集するのではなく、新しいリンクが生成され、再び共有する必要があります。

   各アクティビティリンク URL（エクスペリエンス A、エクスペリエンス B など）を使用して、対応するエクスペリエンスからユーザージャーニーを開始できます。 エクスペリエンス用に生成された URL をクリックし、通常のサイト閲覧に進み、複数のページでエクスペリエンスを表示します（複数のページが存在する場合）。 エクスペリエンスごとに URL が 1 つだけ生成されます。テンプレートのテストや複数ページのテストなど、複数のページにまたがるエクスペリエンスの場合でもそれは同様です。

   サイト内を移動して他のページを確認すると、 [!UICONTROL アクティビティ QA] モードはスティッキーです。 この状況は、バージョン 2 の at.js 実装に当てはまります。*x* または後で。 at.js 1.*x* 実装の場合、この状況は、訪問者のブラウザーでサードパーティ Cookie がブロックされない場合にのみ当てはまります。

1. アクティビティリンクの URL から生成されたレポートを表示するには、アクティビティの **[!UICONTROL レポート]** ページで、 **[!UICONTROL 設定]** アイコン (  ![icon_gear 画像](assets/icon_gear.png) ) を選択し、「 **[!UICONTROL QA モードトラフィック]** から **[!UICONTROL 環境]** 」ドロップダウンリストから選択できます。

## 注意点 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* アクティビティ QA は、 [!DNL Target] アクティビティタイプの場合、「エクスペリエンスプレビュー URL を使用したAutomated Personalizationアクティビティのプレビュー」機能は不要になりました。
* [!UICONTROL アカウントに保存されたアクティビティが多すぎると、保存されたアクティビティのアクティビティ QA プレビューリンクが読み込まれないことがあります。]プレビューリンクの再試行が機能します。 この状況が引き続き発生しないようにするには、アクティブに使用されなくなった保存済みアクティビティをアーカイブします。
* [!UICONTROL アクティビティ QA] URL は、 [レポートソースとしての Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。 QA の実行中に生成されたヒット ( [!UICONTROL アクティビティ QA] は、アクティビティがライブになった後でもアクティビティのデータがフローするのと同じレポートスイートにフローします。
* [!UICONTROL アクティビティ QA は、アーカイブされたアクティビティまたは終了日を過ぎたアクティビティに対してコンテンツを表示しません。]終了したアクティビティを非アクティブ化する場合は、次の目的でアクティビティを再度保存する必要があります。 [!UICONTROL アクティビティ QA] を有効にします。
* にインポートされたアクティビティ [!DNL Target Standard/Premium] （から） [!DNL Target Classic]（例えば）は QA URL をサポートしていません。
* In [!UICONTROL 自動配分] および [!UICONTROL Recommendations] アクティビティの場合、 [!UICONTROL アクティビティ QA].
* [!UICONTROL アクティビティ QA] 定着です。 Web サイトを [!UICONTROL アクティビティ QA]、 [!DNL Target] セッションは期限切れにする必要があります。期限切れにするか、 [!DNL Target] 解放する [!UICONTROL アクティビティ QA] サイトを一般的な訪問者と同じように表示するには、まずを参照してください。 以下を使用： [Target QA ブックマークレット](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 無理に引き出す [!UICONTROL アクティビティ QA].

  また、空の値（など）を `at_preview_token` 使用してサイト上のページを読み込むことで、手動で自分を除外 `https://www.mysite.com/?at_preview_token=`することもできます。

* アクティビティの作成時に「URL が次の場合」を指定した場合 [フォームベースのコンポーザーの絞り込み](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) または [Visual Experience Composer のページ配信オプション )](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)に値を指定しない場合、QA URL は機能しません。 [!UICONTROL アクティビティ QA] URL パラメーターを追加します。 この問題に対処するには、QA URL をクリックしてサイトに移動し、追加されたパラメーターを URL から削除してから新しい URL を読み込みます。
* at.js 1.*x*, [!UICONTROL アクティビティ QA] Safari またはサードパーティ cookie をブロックする別のブラウザーを使用している場合、モードはスティッキーではありません。 その場合、移動先の各 URL にプレビューパラメーターを追加する必要があります。 を実装している場合も同じことが言えます。 [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}.
* アクティビティが複数のエクスペリエンスオーディエンス（同じアクティビティに含まれる米国と英国のサイトなど）を使用している場合、4 つの組み合わせ（Experience A/US サイト、Experience A/UK サイト、Experience B/US サイト、Experience B/UK サイト）に対して QA リンクが生成されません。 エクスペリエンス A とエクスペリエンス B に対する 2 つだけが生成されます。オーディエンス条件を満たすユーザーにのみ、該当のページが表示されます。英国の QA 担当者は、米国サイトを表示できません。
* `at_preview` すべてのパラメーターと値は、既にURLエンコードされています。ほとんどの場合、すべてが期待どおりに動作します。 ただし、クエリ文字列パラメーターを再度エンコードしようとする場合は、ロードバランサーまたは Web サーバーを使用する必要があります。

  この二重エンコーディングが原因で、 [!DNL Target] をデコードしようとします `at_preview_token`, [!DNL Target] は正しいトークンの値を抽出できないので、プレビューが機能しません。

  [!DNL Adobe] では、IT チームに相談して、これらの値が変換されないように、すべてのプレビューパラメーターが許可リストに加えるされていることを確認することをお勧めします。

  次の表に、ドメインで許可リストに加えるできるパラメーターを示します。

  | パラメーター | タイプ | 値 | 説明 |
  |--- |--- |--- |--- |
  | `at_preview_token` | 暗号化された文字列 | 必須、デフォルト値なし | QA モードで実行できるキャンペーン ID のリストを含む、暗号化されたエンティティです。 |
  | `at_preview_index` | 文字列 | 空 | パラメータの形式 `<campaignIndex>` または `<campaignIndex>_< experienceIndex>`<br>両方のインデックスは1から始まります。 |
  | `at_preview_listed_activities_only` | ブール値（true／false） | デフォルト値：false | &quot;true&quot;の場合、 `at_preview_index` パラメーターで指定されているすべてのキャンペーンが処理されます。<br>「false」の場合、プレビュートークンで指定されていない場合でも、ページのすべてのキャンペーンが処理されます。 |
  | `at_preview_evaluate_as_true_audience_ids` | 文字列 | 空 | アンダースコア区切り (「_」) の segmentId のリストで、（ターゲティングとレポートのレベルで）常に「true」として評価される必要があるもの [!DNL Target] リクエスト。 |
  | `_AT_Debug` | 文字列 | ウィンドウまたはコンソール | コンソールログまたは新規ウィンドウです。 |
  | `adobe_mc_ref` |  |  | デフォルトのページの参照 URL を新しいページに渡します。バージョン2.1以降で `AppMeasurement.js` 使用する場合、このパラメーター値 [!DNL Adobe Analytics] を新しいページの参照URLとして使用します。 |
  | `adobe_mc_sdid` |  |  | を [!DNL Supplemental Data Id] (SDID) および [!DNL Experience Cloud Org Id] デフォルトのページから新しいページに移動します。 これらの ID を渡すことで、許可される [!UICONTROL Analytics for Target] (A4T) [!DNL Target] リクエストを [!DNL Analytics] リクエストを新しいページで作成します。 |

* この [!UICONTROL Target QA モード] UI には、複数ページアクティビティのエクスペリエンスの最初の URL のみが表示されます。 あなたがジャーニーテストを作成し、URL1 から URL2 に移動していると仮定します。 ただし、独立して URL2 にアクセスする場合は、URL1 に対して提供されたすべての URL パラメータをコピーし、 &quot;？&quot;を付けた後でそれらを URL2 に適用します。URL1に表示されるように。
* アカウントに保存されたアクティビティが多すぎると、保存されたアクティビティのアクティビティ QA プレビューリンクが読み込まれないことがあります。プレビューリンクを再試行します。この問題が繰り返し発生するのを防ぐために、アクティブに使用されなくなった保存済みアクティビティをアーカイブします。

## Target JavaScript ライブラリ [!UICONTROL QA モード]の互換性 {#compatibility}

[!DNL Target] は、次の JavaScript ライブラリをサポートしています。

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html)

次の表に、様々なアクティビティタイプと、 [!UICONTROL アクティビティ QA] モードは、各ライブラリでサポートされています。

| アクティビティタイプ | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B テスト] | ○ | ○ | ○ |
| [!UICONTROL 自動配分] | ○ | ○ | ○ |
| [!UICONTROL 自動ターゲット] | ○ | ○ | ○ |
| [!UICONTROL Automated Personalization]（AP） | ○ | ○ | ○ |
| [!UICONTROL エクスペリエンスのターゲット設定]（XT） | ○ | ○ | ○ |
| [!UICONTROL 多変量分析テスト] （MVT） | ○ | ○ | ○ |
| [!UICONTROL Recommendations] | ○ | ○ | ○ |

