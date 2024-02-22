---
keywords: アクティビティリスト；アクティビティ；アクティビティ；アクティビティタイプ；アクティビティの編集；アクティビティ操作；アクティビティ属性；アクティビティリストフィルター；アクティビティ制限；パーソナライズ；パーソナライズ
description: でのアクティビティの詳細 [!DNL Target] を使用すると、特定のオーディエンスに対するコンテンツをパーソナライズし、ページデザインをテストできます。
title: コンテンツをパーソナライズし、ページデザインをテストする方法 [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 38a3eb1f194a63620b8b4866a48a17903801fa46
workflow-type: tm+mt
source-wordcount: '2407'
ht-degree: 39%

---

# アクティビティ

のアクティビティ [!DNL Adobe Target] を使用すると、特定のオーディエンスに対するコンテンツをパーソナライズし、ページデザインをテストできます。

例えば、夏用の婦人靴の情報をハイライトするランディングページと夏用の一般衣料をハイライトする別のランディングページの 2 つをテストするアクティビティを作成できます。アクティビティによって、これらの各ランディングページをいつ表示するかを制御する条件や、成功度の高いページを判断する指標を定義できます。アクティビティは、特定の条件が満たされたときに開始および終了するよう設定できます。例えば、具体的な日付の範囲による期間の設定や、アクティビティが承認されたときに開始し非アクティブになったときに終了する設定ができます。

アクティビティを作成する際は、入念な計画が必要です。アクティビティの開始時刻と期間を指定します。 その後、オファーの一覧を作成し、それぞれにターゲットとなるオーディエンスを割り当てます。

## アクティビティリスト {#section_DE8E2DB30D534962A931EF8BB48240F5}

[!UICONTROL アクティビティ]リストは、[!DNL Target] を開いたときのデフォルトのビューです。このページからアクティビティを作成し、既存のアクティビティを管理できます。

[!DNL Target] UI の上部にある「[!UICONTROL アクティビティ]」タブをクリックして[!UICONTROL アクティビティ]リストを表示することもできます。

![アクティビティリスト](/help/main/c-activities/assets/activities-list-new.png)

The [!UICONTROL アクティビティ] リストには、すべてのアクティビティの概要が表示され、様々なアクションを実行できます。

| 要素 | 説明 |
|--- |--- |
| 左ナビゲーションレール | 保存済みまたはライブのアクティビティと失敗または失敗の間を切り替えます [ドラフトアクティビティ](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL フィルターを表示] アイコン<P>![フィルターアイコンを表示](/help/main/c-activities/assets/show-filters-icon.png) | フィルターにアクセスするには、 **[!UICONTROL フィルターを表示]** アイコンをクリックします。<P>詳しくは、 [アクティビティリストへのフィルターの適用](#filters) 下 |
| 検索ボックス | アクティビティをすばやく見つけたり、 [!UICONTROL アクティビティ] リスト。 次の項目で検索できます。 [!UICONTROL 名前], [!UICONTROL URL]または [!UICONTROL ID]. |
| [!UICONTROL アクティビティを作成] | アクティビティを作成します。 様々なアクティビティタイプの作成について詳しくは、次を参照してください。 <ul><li>[A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[自動配分アクティビティの作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[自動ターゲットアクティビティの作成](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Automated Personalizationアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[多変量分析テストの作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Recommendations アクティビティの作成](/help/main/c-recommendations/recommendations.md)</li></ul>各タイプについて詳しくは、 [アクティビティのタイプ](#types) 下 |
| [!UICONTROL モバイルプレビューリンクを作成]<P>![その他のアクションメニュー](/help/main/c-activities/assets/icon-create-mobile-link.png) | 用途 [モバイルプレビューリンク](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=ja) モバイルアプリアクティビティに対して簡単なエンドツーエンドの QA を実行できます。<P>次をクリック： **その他のオプション** アイコン（縦の省略記号）、「 **モバイルプレビューリンクを作成**&#x200B;をクリックし、モバイルでテストするアクティビティを選択します。 |
| テーブルをカスタマイズ<P>![テーブルをカスタマイズアイコン](/help/main/c-activities/assets/icon-customize-table.png) | 表示する列を変更します。 [!UICONTROL アクティビティ] リストを表示するには、 **[!UICONTROL テーブルをカスタマイズ]** アイコンをクリックし、必要な列を選択または選択解除します。<P>変更はアカウントに適用され、ログアウト後もアクティブなままになります。 [!DNL Target]. |
| 一括操作チェックボックス | すべてのアクティビティまたは選択したアクティビティに対して一括操作を実行します。<P>使用可能なアクションのリスト（権限とアクティビティのステータスに応じて異なります）については、 [クイックアクションの実行](#quick-actions) 下 |
| [!UICONTROL タイプ] | アクティビティのタイプ。 The [!UICONTROL タイプ] 列を使用して、各アクティビティをタイプ別にすばやく識別できます。 <ul><li>AB-M：手動 [!UICONTROL A/B テスト]</li><li>AB-AA: [!UICONTROL 自動配分]</li><li>AB-AT: [!UICONTROL 自動ターゲット]</li><li>AP: [!UICONTROL Automated Personalization]</li><li>XT: [!UICONTROL エクスペリエンスのターゲット設定]</li><li>MVT: [!UICONTROL 多変量分析テスト]</li><li>レコード： [!UICONTROL Recommendations]</li></ul>各タイプについて詳しくは、 [アクティビティのタイプ](#types) 下 |
| [!UICONTROL Name] | アクティビティの名前。 アクティビティ名をクリックすると、そのアクティビティの [!UICONTROL 概要] ページに貼り付けます。 <P>次をクリック： **[!UICONTROL クイック情報]** 各アクティビティ名の横にあるアイコンを使用して、ポップアップカードでそのアクティビティの詳細情報を表示できます。<p>次をクリック： **[!UICONTROL その他のアクション]** 各アクティビティ名の横にあるアイコン（横の省略記号）を使用して、アクティビティに対するクイックアクションを実行するメニューを開きます。 （権限とアクティビティのステータスに応じて）次のアクションを使用できます。 [!UICONTROL 編集], [!UICONTROL 有効化], [!UICONTROL 非アクティブ化], [!UICONTROL コピー], [!UICONTROL 削除]、および [!UICONTROL アーカイブ]. 各アクションについて詳しくは、 [クイックアクションの実行](#quick-actions) 下<P>テーブルヘッダーをクリックして、名前の昇順または降順でリストをアルファベット順に並べ替えます。 |
| [!UICONTROL ステータス] | アクティビティのステータスは、次のいずれかになります。<ul><li>**ライブ**：アクティビティは現在実行中です。</li><li>**ドラフト**：アクティビティの設定は開始しましたが、アクティビティは [ドラフトモード](/help/main/c-activities/edit-activity.md) まだ実行する準備が整っていません。</li><li>**スケジュール済み**：アクティビティは、指定された開始日時になるとアクティブ化されます。</li><li>**非アクティブ**：アクティビティは一時停止しているか、非アクティブになっています。</li><li>**同期中**：アクティビティは保存されており、に同期中です。 [!DNL Target] 配信ネットワーク。</li><li>**終了**：アクティビティの指定終了日時になり、アクティビティが提供されなくなりました。</li><li>**アーカイブ済み**： アクティビティはアーカイブされています。アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。</li></ul>**注意**：特定のアクション ( [!DNL Target] API メソッドを使用する UI では、更新が [!DNL Target] UI |
| [!UICONTROL 最終更新日] | アクティビティが最後に更新された日時と、誰が変更したか。<P>テーブルヘッダーをクリックして、日付の昇順または降順でリストを並べ替えます。 |
| [!UICONTROL 優先度] | アクティビティの優先度。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>次の条件に応じて、 [設定](/help/main/administrating-target/reporting.md)、 [!DNL Target] の UI とオプション [!UICONTROL 優先度] 変化する。 従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。 |
| [!UICONTROL プロパティ] | アクティビティの[プロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を表示します。<P>Enterprise ユーザーの権限は、 [Target Premium](/help/main/c-intro/intro.md#premium) 機能。 |
| [!UICONTROL 収益の推定上昇率] | 100％のオーディエンスが勝者エクスペリエンスを閲覧した場合に予測される売上高の増加を表示します。<P>以下の数式を使用して計算します。<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>この数字は、短縮形の表記で小数点の前が 1 桁だけの場合、最大で小数第 1 位に丸められます。例：$1.6M、$60K、$900、$8.5K、$205K<P>勝者となる十分なデータがない、またはコストの見積もりがないアクティビティの場合、このコラムには「---」と表示されます。<P>詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。 |
| [!UICONTROL ソース] | アクティビティが作成された場所を表示します。 [!DNL Adobe Target], [Adobe Target API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)または [AdobeMobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL ロケーション] | アクティビティの URL は、アクティビティが表示される場所を示します。この列を使用すると、アクティビティをすばやく識別して、特定のページで既にアクティビティが実行されているかどうかを判断できます。<P>アクティビティが複数の URL で実行されている場合は、他に使用されている URL の数を示すリンクが表示されます。 該当するアクティビティのすべての URL のリストを表示するには、このリンクをクリックします。<P>URL に基づいて検索できます。 検索ボックスの横にあるドロップダウンリストを使用し、「 」を選択します。 [!UICONTROL URL]. |
| 作成者 | アクティビティを作成した人物の名前。 |
| [!UICONTROL 判定方法] | 各アクティビティで使用される判定方法： [サーバーサイド](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja) または [クライアントサイド](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

## アクティビティのタイプ {#types}

[!DNL Target] には、複数のアクティビティタイプが含まれます。 次の表は、各アクティビティタイプの概要と学習に役立つリンクを示しています。目的に合わせて最適なアクティビティタイプを選択できるように、[Adobe Target Activities ガイド](/help/main/c-activities/target-activities-guide.md)も作成しました。

| アクティビティタイプ | 説明 |
|--- |--- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | A/B テストでは、事前に指定したテスト期間に、複数のバージョンの Web サイトコンテンツを比較し、どのバージョンがコンバージョンを最も多く増やしたのかを確認します。 |
| [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL 自動配分]（ A/B テストのタイプ）2 つ以上のエクスペリエンスの中から勝者を特定し、自動的にその勝者に配分するトラフィックを増やすことでコンバージョンを促進します。その間もテストによる学習は続けられます。 |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | A/B テストの一種である自動ターゲットは、高度な機械学習を使用して、マーケティング担当者が定義した複数の高パフォーマンスなエクスペリエンスを識別し、個々の顧客のプロファイルと類似したプロファイルを持つ以前の訪問者の行動に基づいて、各訪問者に最適なエクスペリエンスを提供します。 |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT) では、ページ上の要素内のオファーの組み合わせを比較し、特定のオーディエンスに対して最も効果が高い組み合わせと、アクティビティの成功に最も効果が高い要素を特定します。 |
| [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL エクスペリエンスのターゲット設定]（XT）では、マーケターが定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP) は、オファーやメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて各訪問者に異なるバリエーションを適合させ、コンテンツをパーソナライズしてコンバージョンを促進します。 |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | レコメンデーションでは、Web サイトでの訪問者のアクティビティに応じて、Web サイトの訪問者に商品を提案する方法を決定します。<P>例えば、リュックサックを購入した顧客に対して、ハイキングシューズやトレッキング用のステッキの購入を提案できます。特定の商品を購入した顧客が購入している他の商品を特定できるアルゴリズムを使用して、多くの場合同時に購入されている商品を示すレコメンデーションを作成できます。または、「これを閲覧した人が他に閲覧したビデオ」アルゴリズムを使用して、視聴しているビデオに類似したビデオをレコメンデーションすることで、訪問者がより長い時間をメディアサイトに費やすよう促すことができます。<P>**注意**：内にレコメンデーションを組み込むこともできます [!UICONTROL A/B テスト], [!UICONTROL 自動配分], [!UICONTROL 自動ターゲット]、および [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ 詳しくは、[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md) を参照してください。この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |

## アクティビティリストへのフィルターの適用 {#filters}

フィルターにアクセスするには、 **[!UICONTROL フィルターを表示]** アイコンをクリックします。

![フィルターオプション](/help/main/c-activities/assets/show-filters-options.png)

メニューでは、次の属性でアクティビティをフィルタリングできます。 |属性|詳細| | — | — | |[!UICONTROL タイプ]|フィルター条件 [アクティビティタイプ](#types).| |[!UICONTROL ステータス]|アクティビティの状態でフィルターします。| |[!UICONTROL レポートソース]|レポートソースでフィルタリングします。<ul><li>[Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md): [!UICONTROL Analytics for Target] (A4T) をレポートソースとして使用する場合。</li><li>[Target](/help/main/c-reports/reports.md): [!DNL Target] を使用します。</li></ul>| |[!UICONTROL Experience Composer]|アクティビティの作成中に使用された Experience Composer のフィルター：<ul><li>[ビジュアル](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): [!UICONTROL Visual Experience Composer] (VEC) を参照してください。</li><li>[フォームベース](/help/main/c-experiences/form-experience-composer.md)：を使用して作成された表示アクティビティ [!UICONTROL フォームベースの Experience Composer].</li></ul>| |[!UICONTROL 指標タイプ]|フィルター条件 [成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md) がアクティビティの作成中に選択されました。<ul><li>コンバージョン</li><li>売上高</li><li>エンゲージメント</li></ul>| |[!UICONTROL 判定方法]|各アクティビティで使用される決定方法でフィルター<ul><li>[サーバーサイド](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja)：サーバー側判定を使用するアクティビティを表示します。</li><li>[クライアントサイド](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)：クライアント側判定を使用するアクティビティを表示します。</li></ul>| |[!UICONTROL アクティビティソース]|各アクティビティの作成に使用するアクティビティソースでフィルタリングします。<ul><li>[!DNL Adobe Target]</li><li>[Adobe Target API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja)</li><li>[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)</li><li>[Adobe Mobile サービス](https://developer.adobe.com/client-sdks/documentation/)</li></ul>| |[!UICONTROL プロパティ]|次の項目でフィルター [プロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) アクティビティが作成された場所です。|

## クイックアクションの実行 {#quick-actions}

次をクリック： **[!UICONTROL その他のアクション]** 各アクティビティ名の横にあるアイコン（横の省略記号）を使用して、アクティビティに対するクイックアクションを実行するメニューを開きます。

![クイックアクションオプション](/help/main/c-activities/assets/quick-actions.png)

（権限とアクティビティのステータスに応じて）次のアクションを使用できます。

| アクション | 説明 |
| --- | --- |
| [!UICONTROL Edit] | アクティビティを変更します。どのアクティビティも編集できます。<P>アクティビティを編集する様々な方法について詳しくは、 [アクティビティを編集またはドラフトとして保存](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL 非アクティブ化] | ライブまたは日時指定のアクティビティを停止します。非アクティブ化されたアクティビティは、再アクティブ化またはアーカイブできます。<P>アクティビティを非アクティブ化またはアーカイブした後に再度アクティブ化した場合、非アクティブ化またはアーカイブ以前からアクティビティに含まれていた訪問者は、再アクティブ化の後も引き続きアクティビティに含まれます。非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL アクティブ化] | 非アクティブなアクティビティまたはアクティブ化の準備が整ったアクティビティを開始します。 |
| [!UICONTROL アーカイブ] | アクティビティをアーカイブに送信します。デフォルトでは、アーカイブされたアクティビティは [!UICONTROL アクティビティ] リスト。 アクティビティリストのフィルターを変更して、アーカイブ済みアクティビティが含まれるようにして、表示されるようにします。アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。<P>アクティビティを非アクティブ化またはアーカイブし、後で再アクティブ化した場合、非アクティブ化またはアーカイブする前にそのアクティビティにいた場合、訪問者は、再アクティブ化後もそのアクティビティの一部となります。 非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL コピー] | アクティビティをコピーします。どのアクティビティもコピーできます。アクティビティをコピーすると、同じ名前に「Copy」と付いた、新しいアクティビティが作成されます。例えば、「ブラウザーオファー」というテストは、「ブラウザーオファー Copy」という名前でコピーされます。<P>ビジュアルオファーは、アクティビティと共にコピーされます。元のアクティビティに影響を与えることなく、コピー内で安全にオファーを編集できます。唯一の例外は、コンテンツ／アセットフォルダー内に保存したオファーおよび画像です。 |
| [!UICONTROL 削除] | ドラフトまたはアクティビティを削除します。<P>**注意**：削除したアクティビティは復元できません。 このアクティビティが二度と必要にならないと確信している場合を除き、 [!UICONTROL アーカイブ] アクション。 その後、必要に応じてアクティビティを再アクティブ化できます。 |

## 注意点

次の詳細に注意してください： [!UICONTROL アクティビティ] リスト：

* アーカイブ済みおよび終了したアクティビティは、[!UICONTROL アクティビティ]リストには表示されません。これらのアクティビティを表示するには、 [フィルターアイコン](#filters) をクリックします。
* 最初にで作成されたアクティビティの場合 [!DNL Target Classic] が非アクティブ化または削除された場合、次の項目から削除されます： [!DNL Target Standard/Premium]. 削除されると、もともと [!DNL Target Classic] で作成されたアクティビティは、[!DNL Target Standard/Premium] の [!UICONTROL アーカイブ]フォルダーに送信されません。アーカイブ済みフォルダー機能は、[!DNL Target Standard/Premium] で作成されたアクティビティにのみ適用されます。
* [!UICONTROL Automated Personalization]（AP）、[!UICONTROL 自動配分]、[!UICONTROL 自動ターゲット]以外のすべてのタイプのアクティビティでは、データソースとして[!DNL Target]または[!DNL Adobe Analytics]のいずれかを使用できます。[!UICONTROL AP]、[!UICONTROL 自動配分]、および [!UICONTROL 自動ターゲット]では、*常に* [!DNL Target] データが使用されます。
* アクティビティは複数のチャネルで利用可能です。

   * Web およびモバイルサイト
   * インターネットに接続された画面およびデバイス（キオスクや ATM を含む）
   * メールや他の購買チャネルまたはパートナーサイト
   * モバイルアプリ
   * タグ付きコンテンツを配信できる他の場所すべて

## 制限事項 {#section_049D4684403A4E07B998067EB8E9BE56}

各 Target アクティビティには、次のコンテンツの制限があります。

| 項目 | 制限 |
|--- |--- |
| 一意のセレクター数 | 300。セレクターが別のエクスペリエンスで繰り返される場合、1 回とカウントされます。 ただし、同じエクスペリエンスで繰り返される場合は、再度カウントされます。 |
| 各エクスペリエンスのオファー | 350 |
| 指標のクリック追跡セレクター数 | 50 |
| 指標の mbox 数 | 50 |
| オーディエンスと場所 | 50 個のオーディエンスと場所 (mbox) の組み合わせは、50 個以下にする必要があります。 |

これらの制限を超えると、アクティビティを保存できません。

アクティビティでこれらの項目の数を増やすと、アクティビティを同期するのにかかる時間も長くなります [!DNL Target].

V の追加制限[!UICONTROL Visual Experience Composer] VEC( [Visual Experience Composer の制限](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## に読み込まれた属性 [!DNL Target] （以外で更新されたアクティビティの場合） [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

If アクティビティが [!DNL Target] は、 [!DNL Target] （例えば、API を使用）、次のアクティビティ属性がに再び読み込まれます。 [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority`、および `marketingCloudMetadata(remoteModifiedBy)`.

この読み込みジョブは、アクティビティページが開かれたときに実行され、最大遅延は 10 分です。

## トレーニングビデオ {#section_BE80D13A2E81460C885F902010E1AD87}

次のビデオでは、この記事で説明する概念の詳細を説明します。

### アクティビティのタイプ（9:03）

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティのタイプについて説明しています。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

