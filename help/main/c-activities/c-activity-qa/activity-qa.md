---
keywords: qa;qa モード；アクティビティ qa;qa url;qa url；プレビューurl；プレビューurl
description: Adobe [!DNL Target]のQA URLを使用して、変更のないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化されたままのQA レポートを使用して、簡単なエンドツーエンドのアクティビティ QAを実行する方法について説明します。
title: QA アクティビティを実行するにはどうすればよいですか？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
TQID: 'https://experienceleague.adobe.com/glE1Kx2xhqagq9v-SgSkdwr6lYwpioe4DlSkLRFQ0jI'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ec6df29fa12dab229b89c061a9db3374e38c2152
workflow-type: tm+mt
source-wordcount: '1868'
ht-degree: 12%
---
# アクティビティ QAの概要 {#activity-qa}

>[!BEGINSHADEBOX]

**このページで：** アクティビティ QA リンクを使用してアクティビティをエンドツーエンドでテストし、QA レポートを確認して、QA モードから解放する方法を説明します。

>[!ENDSHADEBOX]

**[!UICONTROL アクティビティ QA]**&#x200B;を使用すると、アクティビティを公開する前に、[!DNL Adobe Target] アクティビティを完全にテストできます。プレビューリンクは変更されません。オプションのオーディエンスターゲティング、ライブアクティビティデータとは別のQA レポートを使用できます。 **[!UICONTROL アクティビティ QA]**&#x200B;機能には、次のものが含まれます。

* **固定リンク：** エクスペリエンスやアクティビティの更新に関係なく、変更がない、または再生成が必要ないチームメンバーとリンクを共有します。
* **オプションのオーディエンスターゲティング：** ターゲティング条件をテストするか、無視して、オーディエンスの条件を満たさずにエクスペリエンスの外観を確認します。
* **個別のQA レポート：**&#x200B;指標が期待どおりに増加することを確認してください。 QA レポートデータは、実稼動レポートとは別に保持されます（A4T以外のレポートの場合）。
* **他のアクティビティを使用したプレビュー：**&#x200B;配信条件を満たす単独または他のライブアクティビティ（ページ/[!DNL Target] リクエスト/オーディエンス）を使用して、エクスペリエンスをプレビューします。
* **完全なユーザージャーニー：** QA リンクを使用して一度サイトにアクセスしてから、**[!UICONTROL アクティビティ QA]**&#x200B;でサイト全体を参照します。 セッションを終了するか、[QA ターゲットブックマークレット ](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md)を使用して強制的に退出するまで、**[!UICONTROL アクティビティ QA]**&#x200B;に留まります。 この機能は、複数のweb ページにまたがるアクティビティがある場合に便利です。

  >[!NOTE]
  >
  >この機能は、バージョン 2.*x*&#x200B;以降のat.js実装に当てはまります。 at.js 1.*x*&#x200B;実装の場合、この機能は、訪問者のブラウザーがサードパーティ Cookieをブロックしない場合にのみ有効です。

## QA URLへのアクセスと共有 {#section_1C59BAA247B247BDB125D1BE8EAD4547}

アクティビティ QA リンクを使用すると、アクティビティが公開される前に、サイト上のアクティビティの各エクスペリエンスを表示できます。 QA トラフィックはライブトラフィックとは別にレポートされるため、テストはライブレポートに影響しません。

1. アクティビティの&#x200B;**[!UICONTROL 概要]** ページで、**[!UICONTROL アクティビティ QA]**&#x200B;をクリックします。

   概要ページ ](../assets/activity-qa.png)の「アクティビティの場所」セクションの「![ アクティビティ QA」ボタン

1. **[!UICONTROL オーディエンスルールを一致させてエクスペリエンスを表示する]**&#x200B;を設定し、テスターがオーディエンスに適格かどうかを選択します。 オーディエンスマッチングが機能することを確認するにはオンにし、アクティビティのルックアンドフィールを確認するにはオフにします。

   * **オン：** テスターは、エクスペリエンスを表示するには、ターゲティング要件を満たす必要があります。 エクスペリエンスのターゲット設定（XT）アクティビティの場合、単一のアクティビティ URLが提供され、表示されるエクスペリエンスは、対象となるターゲティングルールによって異なります。
   * **オフ：** リンクには、資格があるかどうかに関係なく、エクスペリエンスが表示されます。 QA中にいつでも2つの設定を切り替えることができます。

   ![2つの設定と各エクスペリエンスのQA URLを含むアクティビティ QA ウィンドウ ](../assets/activity-qa-1.png)

1. **[!UICONTROL 他のすべてのアクティビティのデフォルトコンテンツを表示]**&#x200B;に設定して、他のライブアクティビティをページに表示するかどうかを選択します。

   * **オン：** デフォルトコンテンツは、その他のすべてのアクティビティに表示されます。 プレビューは、同じページ/[!DNL Target] リクエストの他のライブアクティビティを考慮せずに、独立して表示されます。
   * **オフ：** テスト中のアクティビティと他のライブアクティビティの間に衝突がある場合、[通常の優先ルール ](/help/main/c-activities/priority.md#priority)が適用されるため、QAするアクティビティが表示されない可能性があります。 指標は表示されたアクティビティについて増分しますが、それは QA レポートの環境内のみです。

1. 「**[!UICONTROL 完了]**」をクリックして変更を保存します。

1. テスト用に、アクティビティリンク URLを組織のメンバーと共有します。

   各リンク URL （エクスペリエンス A、エクスペリエンス Bなど）は、対応するエクスペリエンスからユーザージャーニーを開始します。 エクスペリエンスごとに URL が 1 つだけ生成されます。テンプレートのテストや複数ページのテストなど、複数のページにまたがるエクスペリエンスの場合でもそれは同様です。

   リンクは期限切れになることはなく、アクティビティやエクスペリエンスの変更によって再送信する必要はありません。 ただし、アクティビティを編集する代わりに&#x200B;**[!UICONTROL オーディエンスライブラリ]**&#x200B;から別のオーディエンスを適用すると、新しいリンクが生成され、もう一度共有する必要があります。

1. エクスペリエンスのURLをクリックしてから、通常どおりサイトを参照すると、複数のページ（複数のページが存在する場合）でエクスペリエンスが表示されます。

   **[!UICONTROL アクティビティ QA]** モードはページ間で保持されるので、サイトを移動して他のページを表示できます。 これは、バージョン 2.*x*&#x200B;以降のat.js実装に当てはまります。 at.js 1.*x*&#x200B;実装の場合、これは、訪問者のブラウザーがサードパーティ Cookieをブロックしない場合にのみ当てはまります。

1. アクティビティリンク URLから生成されたレポートを表示するには、アクティビティの&#x200B;**[!UICONTROL レポート]** ページにアクセスし、**[!UICONTROL 設定]** アイコン （![icon_gear image](assets/icon_gear.png)）をクリックし、**[!UICONTROL 環境]** ドロップダウンリストから&#x200B;**[!UICONTROL QA モードトラフィック]**&#x200B;を選択します。

   レポート設定の環境リストの![QA モードトラフィックオプション ](../assets/activity-qa-2.png)

## アクティビティ QA モードを終了

**[!UICONTROL アクティビティ QA]** モードは、終了するまで保持されます。 **[!UICONTROL アクティビティ QA]**&#x200B;でweb サイトを閲覧した後、[!DNL Target] セッションが期限切れになるか、強制的に離脱するまでQA モードのままになります。 典型的な訪問者のようにサイトを表示するには、まず離脱する必要があります。

### at.js 2.*x*

サイトにat.js 2.*x*&#x200B;がデプロイされている場合は、[Target QA bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md)を使用して、**[!UICONTROL Activity QA]**&#x200B;から強制的に削除します。 次の節で説明するように、空の値を持つサイトでページを読み込むと、*not*&#x200B;は、at.js 2.*x*&#x200B;がデプロイされたときに、ブラウザーからQA Cookieを削除しません。

### at.js 1.*x*

サイトにat.js 1.*x*&#x200B;がデプロイされている場合、[Target QA ブックマークレット ](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md)を使用することに加えて、`at_preview_token` パラメーターが空の値に設定されたサイト上のページを手動で読み込むことができます。 次に例を示します。

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

サイトに[[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}がデプロイされている場合、`at_qa_mode` パラメーターが空の値に設定されたサイト上のページを手動で読み込むことで、自分自身を強制的に削除できます。 次に例を示します。

`https://www.mysite.com/?at_qa_mode=`

## 注意点 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

### 可用性と制限 {#availability}

+++ Automated Personalization エクスペリエンスのプレビューURL

**[!UICONTROL アクティビティ QA]**&#x200B;は、[!DNL Target]のすべてのアクティビティタイプで利用できるようになりました。そのため、「エクスペリエンスのプレビューURLを使用したAutomated Personalization アクティビティのプレビュー」機能は不要になりました。

+++

+++ レポートソースとしての分析（A4T）

**[!UICONTROL アクティビティ QA]**&#x200B;のURLは、[Analyticsをレポートソース ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）とするアクティビティで利用できます。 アクティビティ QA ]**を使用してQAを実行する際に生成されたヒットは、アクティビティが公開された後でも、アクティビティデータがフローする同じレポートスイートに送信されます。**[!UICONTROL 

+++

+++ アーカイブ済みまたは終了したアクティビティ

**[!UICONTROL アクティビティ QA]**&#x200B;は、アーカイブされたアクティビティまたは終了日を過ぎたアクティビティのコンテンツを表示しません。 終了したアクティビティを非アクティブ化した場合、**[!UICONTROL アクティビティ QA]**&#x200B;が機能するように、アクティビティを再度保存する必要があります。

+++

+++ インポートしたアクティビティ

[!DNL Target Standard/Premium]に読み込まれたアクティビティ （例：[!DNL Target Classic]から）は、QA URLをサポートしていません。

+++

+++ 自動割り当てとレコメンデーションモデル

**[!UICONTROL 自動割り当て]**&#x200B;および&#x200B;**[!UICONTROL Recommendations]** アクティビティでは、モデルは&#x200B;**[!UICONTROL Activity QA]**&#x200B;でキャプチャされた訪問の影響を受けません。

+++

### リンクとブラウジング {#links-and-browsing}

+++ 「URLは」条件を持つアクティビティ

フォームベースのコンポーザー](/help/main/c-experiences/form-experience-composer.md)でアクティビティを作成する際に「URLが」を指定した場合、またはVisual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)で[ ページ配信オプションを指定した場合、**[!UICONTROL Activity QA]**&#x200B;はURL パラメーターを追加するため、QA URLは機能しません。 [この問題に対処するには、QA URL をクリックしてサイトに移動し、追加されたパラメーターを URL から削除してから新しい URL を読み込みます。

+++

+++ サードパーティ Cookieをブロックするブラウザー（at.js 1.*x*）

at.js 1.*x*&#x200B;をお持ちの場合、Safariまたはサードパーティ Cookieをブロックする別のブラウザーを使用している場合、**[!UICONTROL Activity QA]** モードはページ間で保持されません。 この場合、移動する各URLにプレビューパラメーターを追加する必要があります。 [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}を実装した場合も同様です。

+++

+++ 複数のエクスペリエンスオーディエンスを持つアクティビティ

アクティビティで複数のエクスペリエンスオーディエンス（同じアクティビティに含まれる米国と英国のサイトなど）を使用する場合、4つの組み合わせ（エクスペリエンス A/米国サイト、エクスペリエンス A/英国サイト、エクスペリエンス B/米国サイト、エクスペリエンス B/英国サイト）に対してQA リンクは生成されません。 2つのQA リンク（エクスペリエンス Aとエクスペリエンス B）のみが作成され、ユーザーがページを表示するには、適切なオーディエンスの条件を満たす必要があります。 英国のQA ユーザーは米国のサイトを表示できません。

+++

+++ マルチページアクティビティ

**[!UICONTROL ターゲット QA モード]** UIには、複数ページのアクティビティのエクスペリエンスの最初のURLのみが表示されます。 ジャーニーテストを作成し、URL1からURL2に移動することを前提としています。 ただし、URL2に個別に移動する場合は、URL1に指定されたすべてのURL パラメーターをコピーし、「?」を配置した後にURL2に適用します url1のように。

+++

### 読み込まれないプレビューリンク {#preview-not-loading}

+++ 保存されたアクティビティが多すぎます

アカウントに保存されているアクティビティが多すぎる場合、保存されたアクティビティの&#x200B;**[!UICONTROL アクティビティ QA]**&#x200B;のプレビューリンクが読み込まれない可能性があります。 プレビューリンクを再試行します。 この問題が繰り返されないようにするには、アクティブに使用されなくなった保存済みアクティビティをアーカイブします。

+++

+++ ダブルエンコードされたプレビューパラメーター

`at_preview` すべてのパラメーターと値は、既にURLエンコードされています。 多くの場合、すべてが期待通りに機能します。 ただし、一部の顧客は、クエリ文字列パラメーターを再びエンコードしようとするロードバランサーまたはweb サーバーを使用します。

この二重エンコーディングでは、[!DNL Target]は`at_preview_token`をデコードしようとしたときに正しいトークン値を抽出できないため、プレビューが機能しません。

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

+++

## Target JavaScript ライブラリ [!UICONTROL QA モード ]の互換性 {#compatibility}

[!DNL Target]は次のJavaScript ライブラリをサポートしています：

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja)

次の表に、様々なアクティビティタイプを示し、各ライブラリで&#x200B;**[!UICONTROL Activity QA]** モードがサポートされているかどうかを示します。

| アクティビティタイプ | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B テスト] | ○ | ○ | ○ |
| [!UICONTROL 自動配分] | ○ | ○ | ○ |
| [!UICONTROL 自動ターゲット] | ○ | ○ | ○ |
| [!UICONTROL Automated Personalization]（AP） | ○ | ○ | ○ |
| [!UICONTROL エクスペリエンスのターゲット設定]（XT） | ○ | ○ | ○ |
| [!UICONTROL 多変量分析テスト] （MVT） | ○ | ○ | ○ |
| [!UICONTROL レコメンデーション] | ○ | ○ | ○ |
