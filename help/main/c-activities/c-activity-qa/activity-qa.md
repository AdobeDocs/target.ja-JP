---
keywords: qa;qa モード；アクティビティ qa;qa url;qa url；プレビューurl；プレビューurl
description: Adobe [!DNL Target] QA URLを使用して、変更のないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化された状態のQA レポートを使用して、簡単なエンドツーエンドのアクティビティ QAを実行する方法について説明します。
title: QA アクティビティを実行するにはどうすればよいですか？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
TQID: https://experienceleague.adobe.com/glE1Kx2xhqagq9v-SgSkdwr6lYwpioe4DlSkLRFQ0jI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1815
ht-degree: 27%

---

# アクティビティ QA

[!DNL Adobe Target]のQA URLを使用すると、変更のないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化されたままのQA レポートを使用して、簡単なエンドツーエンドのアクティビティ QAを実行できます。

[!UICONTROL  アクティビティ QA]を使用すると、[!DNL Target] アクティビティを完全にテストしてから、本番稼動を開始できます。 [!UICONTROL  アクティビティ QA]機能には、次のものが含まれます。

* エクスペリエンスやアクティビティの更新に関係なく、変更がない、または再作成を必要としないチームメンバーと共有するためのリンクです。 この機能により、ユーザージャーニー全体でアクティビティを完全にテストできます。
* 考慮するオーディエンス条件を任意で選択できるので、マーケターは、オーディエンス条件を満たさなくてもターゲティング条件をテストしたり無視したりして、エクスペリエンスのデザインの QA を行えます。
* QA レポートが取り込まれることで、マーケターは、指標が想定どおりに増分され、QA レポートのデータが本番環境のレポートとは別に保持されていることを確認できます（A4T 以外のレポートの場合）。
* 配信条件（ページ/[!DNL Target] リクエスト/オーディエンス）を満たす、単独または他のライブアクティビティでエクスペリエンスをプレビューする機能。
* ユーザージャーニー全体を QA の対象にできます。 QA リンクを使用してサイトに 1 回アクセスすれば、アクティビティ QA 内でサイト全体を閲覧することができます。 セッションを終了するか、[QA ターゲットブックマークレット ](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)を使用して[!UICONTROL  アクティビティ QA]から強制的に除外するまで、アクティビティ QAに参加したままになります。 この機能は、複数のweb ページにまたがるアクティビティがある場合に便利です。

  >[!NOTE]
  >
  >この機能は、バージョン 2.*x*&#x200B;以降のat.js実装に当てはまります。 at.js 1.*x*&#x200B;実装の場合、この機能は、訪問者のブラウザーがサードパーティ Cookieをブロックしない場合にのみ有効です。

## QA URL へのアクセスおよび共有 {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. アクティビティの[!UICONTROL 概要] ページで、**[!UICONTROL アクティビティ QA]**&#x200B;をクリックします。

1. 以下の設定を指定します。

   * **[!UICONTROL オーディエンスルールを一致させてエクスペリエンスを表示する]:** オーディエンスの一致が機能することを確認する場合があります。 また、アクティビティのルック&amp;フィールを確認する場合もあります。 この設定を「オン」にすると、ターゲット条件を満たすテスターのみがエクスペリエンスの表示対象になります。 エクスペリエンスのターゲット設定（XT）アクティビティでは、単一のアクティビティ URL が提供されます。 表示されるエクスペリエンスは、ユーザーがどのターゲットルールに一致するかによって決まります。

     この設定を「オフ」にした場合は、ユーザーがリンクをクリックすると、ルールに一致するかどうかに関係なく、エクスペリエンスが表示されます。 QA を実行する際は、このオーディエンスのターゲット設定を考慮するかしないかを切り替えることができます。

   * **他のすべてのアクティビティのデフォルトコンテンツを表示：**&#x200B;このオプションを「オン」の位置に切り替えると、他のすべてのアクティビティにデフォルトコンテンツが表示されます。 例えば、プレビューは、同じページ/[!DNL Target] リクエスト上の他のすべてのライブアクティビティを考慮せずに単独で表示されます。

     「オフ」にした場合は、以下の点を考慮します。

      * テスト中のアクティビティと他のライブアクティビティの間に衝突がある場合、[通常の優先ルール ](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)が適用されます。 衝突のため、QAを行おうとしているアクティビティが表示されない可能性があります。
      * 指標は表示されたアクティビティについて増分しますが、それは QA レポートの環境内のみです。

1. 「**[!UICONTROL 完了]**」をクリックして変更を保存します。
1. テスト用に、アクティビティリンク URLを組織のメンバーと共有します。

   アクティビティのリンクは期限切れになることはなく、誰かがアクティビティやエクスペリエンスを変更した場合にリンクを再送信する必要もありません。 ただし、アクティビティを編集するのではなく、[!UICONTROL  オーディエンスライブラリ ]から別のオーディエンスを適用すると、新しいリンクが生成され、もう一度共有する必要があります。

   各アクティビティリンク URL （エクスペリエンス A、エクスペリエンス Bなど）を使用すると、対応するエクスペリエンスからユーザージャーニーを開始できます。 エクスペリエンス用に生成されたURLをクリックし、通常のサイト参照に進むと、複数のページでエクスペリエンスが表示されます（複数のページが存在する場合）。 エクスペリエンスごとに URL が 1 つだけ生成されます。テンプレートのテストや複数ページのテストなど、複数のページにまたがるエクスペリエンスの場合でもそれは同様です。

   [!UICONTROL  アクティビティ QA] モードはスティッキーなので、サイトを移動して他のページを表示できます。 この状況は、バージョン 2.*x*&#x200B;以降のat.js実装に当てはまります。 at.js 1.*x*&#x200B;実装の場合、この状況は、訪問者のブラウザーがサードパーティ Cookieをブロックしない場合にのみ当てはまります。

1. アクティビティリンク URLから生成されたレポートを表示するには、アクティビティの&#x200B;**[!UICONTROL レポート]** ページをクリックし、**[!UICONTROL 設定]** アイコン （![icon_gear image](assets/icon_gear.png)）をクリックし、**[!UICONTROL 環境]** ドロップダウンリストから&#x200B;**[!UICONTROL QA モードトラフィック]**&#x200B;を選択します。

## QA モードからの解放

[!UICONTROL  アクティビティ QA]は粘着性があります。 [!UICONTROL Activity QA]でweb サイトを閲覧した後、典型的な訪問者のようにサイトを表示するには、[!DNL Target] セッションの有効期限が切れるか、[!UICONTROL Activity QA]から[!DNL Target] リリースする必要があります。

### at.js 2.*x*

サイトにat.js 2.*x*&#x200B;がデプロイされている場合は、[Target QA bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)を使用して、[!UICONTROL Activity QA]から強制的に削除します。 次の箇条書きの説明に従って、サイト上で空の値を持つページを読み込むと、at.js 2.*x*&#x200B;がデプロイされたときに&#x200B;*not*&#x200B;がブラウザーからQA Cookieを削除します。

### at.js 1.*x*

サイトにat.js 1.*x*&#x200B;がデプロイされている場合、[Target QA bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)を使用することに加えて、空の値を持つ`at_preview_token` パラメーターを使用してサイト上のページを読み込むことで、手動で強制的に削除することもできます。 例：

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

サイトに[[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}がデプロイされている場合は、空の値を持つ`at_qa_mode` パラメーターを使用してサイト上のページを読み込むことで、手動で強制的に削除できます。 例：

`https://www.mysite.com/?at_qa_mode=`

## 注意点 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* アクティビティ QAがすべての[!DNL Target]のアクティビティタイプで使用できるようになったため、「エクスペリエンスのプレビューURLを使用したAutomated Personalization アクティビティのプレビュー」機能は不要になりました。
* アカウントに保存されているアクティビティが多すぎる場合、保存されたアクティビティの[!UICONTROL  アクティビティ QA]のプレビューリンクが読み込まれない可能性があります。 プレビューリンクを再試行すると、正常に動作します。 この状況が引き続き発生しないようにするには、保存済みのアクティビティのうち、アクティブに使用されなくなったアクティビティをアーカイブします。
* [!UICONTROL  アクティビティ QA]のURLは、[Analyticsをレポートソース ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）とするアクティビティで利用できます。 アクティビティ QA]を使用してQAを実行する際に生成されたヒットは、アクティビティの公開後でも、アクティビティのデータがフローするレポートスイートと同じレポートスイートに送信されます。[!UICONTROL 
* [!UICONTROL  アクティビティ QA]は、アーカイブされたアクティビティまたは終了日を過ぎたアクティビティのコンテンツを表示しません。 終了したアクティビティを非アクティブ化した場合、[!UICONTROL  アクティビティ QA]が機能するように、アクティビティを再度保存する必要があります。
* [!DNL Target Standard/Premium]に読み込まれたアクティビティ （例：[!DNL Target Classic]から）は、QA URLをサポートしていません。
* [!UICONTROL 自動割り当て]および[!UICONTROL Recommendations] アクティビティでは、モデルは[!UICONTROL Activity QA]でキャプチャされた訪問の影響を受けません。
* アクティビティ [の作成中に「URLが」を指定した場合は、フォームベースのコンポーザー](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)または[ ページ配信オプション （Visual Experience Composer） ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)で、アクティビティ の絞り込みが発生します。これは、[!UICONTROL  アクティビティ QA]がURL パラメーターを追加しているためです。 この問題に対処するには、QA URL をクリックしてサイトに移動し、追加されたパラメーターを URL から削除してから新しい URL を読み込みます。
* at.js 1.*x*&#x200B;をお持ちの場合、Safariまたはサードパーティ Cookieをブロックする別のブラウザーを使用している場合、[!UICONTROL Activity QA] モードはスティッキーではありません。 この場合、移動する各URLにプレビューパラメーターを追加する必要があります。 [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}を実装した場合も同様です。
* アクティビティで複数のエクスペリエンスオーディエンス（同じアクティビティに含まれる米国と英国のサイトなど）を使用する場合、4つの組み合わせ（エクスペリエンス A/米国サイト、エクスペリエンス A/英国サイト、エクスペリエンス B/米国サイト、エクスペリエンス B/英国サイト）に対してQA リンクは生成されません。 エクスペリエンス A とエクスペリエンス B に対する 2 つだけが生成されます。オーディエンス条件を満たすユーザーにのみ、該当のページが表示されます。 英国のQA ユーザーは米国のサイトを表示できません。
* `at_preview` すべてのパラメーターと値は、既にURLエンコードされています。 多くの場合、すべてが期待通りに機能します。 ただし、一部の顧客は、クエリ文字列パラメーターを再びエンコードしようとするバランサーまたはWeb サーバーを読み込む必要があります。

  この二重エンコーディングのため、[!DNL Target]が`at_preview_token`をデコードしようとすると、[!DNL Target]は正しいトークン値を抽出できず、プレビューが機能しません。

  [!DNL Adobe]では、すべてのプレビューパラメーターが許可リストに加えるされ、これらの値が何らかの形で変換されないようにするために、IT チームと話し合うことをお勧めします。

  次の表に、ドメインで許可リストに加えるできるパラメーターを示します。

  | パラメーター | タイプ | 値 | 説明 |
  |--- |--- |--- |--- |
  | `at_preview_token` | 暗号化された文字列 | 必須、デフォルト値なし | QA モードで実行できるキャンペーン IDのリストを含む、暗号化されたエンティティ。 |
  | `at_preview_index` | 文字列 | 空 | パラメーターの形式は`<campaignIndex>`または`<campaignIndex>_< experienceIndex>`<br>両方のインデックスが1で始まります。 |
  | `at_preview_listed_activities_only` | ブール値（true／false） | デフォルト値：false | &quot;true&quot;の場合、 `at_preview_index` パラメーターで指定されているすべてのキャンペーンが処理されます。<br>「false」の場合、プレビュートークンで指定されていない場合でも、ページのすべてのキャンペーンが処理されます。 |
  | `at_preview_evaluate_as_true_audience_ids` | 文字列 | 空 | 常に（ターゲティングレベルとレポートレベルで）評価されるセグメント IDのアンダースコア区切り（「_」）リストは、[!DNL Target] リクエストの範囲で「true」として評価されます。 |
  | `_AT_Debug` | 文字列 | ウィンドウまたはコンソール | コンソールログまたは新規ウィンドウです。 |
  | `adobe_mc_ref` |  |  | デフォルトのページの参照 URL を新しいページに渡します。 バージョン2.1以降で `AppMeasurement.js` 使用する場合、このパラメーター値 [!DNL Adobe Analytics] を新しいページの参照URLとして使用します。 |
  | `adobe_mc_sdid` |  |  | [!DNL Supplemental Data Id] （SDID）と[!DNL Experience Cloud Org Id]をデフォルトページから新しいページに渡します。 これらのIDを渡すと、[!UICONTROL Analytics for Target] （A4T）は、デフォルトページの[!DNL Target] リクエストと、新しいページの[!DNL Analytics] リクエストを「結合」することができます。 |

* [!UICONTROL  ターゲット QA モード ] UIには、複数ページのアクティビティのエクスペリエンスの最初のURLのみが表示されます。 ジャーニーテストを作成し、URL1からURL2に移動することを前提としています。 ただし、独立して URL2 にアクセスする場合は、URL1 に対して提供されたすべての URL パラメータをコピーし、 &quot;？&quot;を付けた後でそれらを URL2 に適用します。 URL1に表示されるように。
* アカウントに保存されたアクティビティが多すぎると、保存されたアクティビティのアクティビティ QA プレビューリンクが読み込まれないことがあります。 プレビューリンクを再試行します。 この問題が引き続き発生するのを防ぐために、アクティブに使用されなくなった保存済みのアクティビティをアーカイブします。

## Target JavaScript ライブラリ [!UICONTROL QA モード ]の互換性 {#compatibility}

[!DNL Target]は次のJavaScript ライブラリをサポートしています：

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja)

次の表に、様々なアクティビティタイプを示し、各ライブラリで[!UICONTROL Activity QA] モードがサポートされているかどうかを示します。

| アクティビティタイプ | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B テスト] | ○ | ○ | ○ |
| [!UICONTROL 自動配分] | ○ | ○ | ○ |
| [!UICONTROL 自動ターゲット] | ○ | ○ | ○ |
| [!UICONTROL Automated Personalization]（AP） | ○ | ○ | ○ |
| [!UICONTROL エクスペリエンスのターゲット設定]（XT） | ○ | ○ | ○ |
| [!UICONTROL 多変量分析テスト] （MVT） | ○ | ○ | ○ |
| [!UICONTROL レコメンデーション] | ○ | ○ | ○ |