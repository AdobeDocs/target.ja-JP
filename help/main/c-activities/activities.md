---
keywords: アクティビティリスト；アクティビティ；アクティビティ；アクティビティタイプ；アクティビティの編集；アクティビティ属性；アクティビティリストフィルター；アクティビティの制限；パーソナライズ機能；パーソナライゼーション
description: のアクティビティを使用して  [!DNL Target]  特定のオーディエンス向けにコンテンツをパーソナライズし、ページのデザインをテストする方法を説明します。
title: ' [!DNL Target] を使用してコンテンツをパーソナライズし、ページのデザインをテストするにはどうすればよいですか？'
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 0e2bc5c96671b47532b90f3ecb525a6a0506eb8d
workflow-type: tm+mt
source-wordcount: '2290'
ht-degree: 36%

---

# アクティビティ

[!DNL Adobe Target] のアクティビティを使用すると、特定のオーディエンス対してコンテンツをパーソナライズし、ページのデザインをテストできます。

例えば、夏用の婦人靴の情報をハイライトするランディングページと夏用の一般衣料をハイライトする別のランディングページの 2 つをテストするアクティビティを作成できます。アクティビティによって、これらの各ランディングページをいつ表示するかを制御する条件や、成功度の高いページを判断する指標を定義できます。アクティビティは、特定の条件が満たされたときに開始および終了するよう設定できます。例えば、具体的な日付の範囲による期間の設定や、アクティビティが承認されたときに開始し非アクティブになったときに終了する設定ができます。

アクティビティを作成する際は、入念な計画が必要です。アクティビティの開始時刻と期間を指定します。 その後、オファーの一覧を作成し、それぞれにターゲットとなるオーディエンスを割り当てます。

## アクティビティリスト {#section_DE8E2DB30D534962A931EF8BB48240F5}

[!UICONTROL Activities] リストは、[!DNL Target] を開いたときのデフォルトのビューです。 このページからアクティビティを作成し、既存のアクティビティを管理できます。

また、[!DNL Target] UI の上部にある「[!UICONTROL Activities]」タブをクリックして、[!UICONTROL Activities] リストを表示することもできます。

![アクティビティリスト](/help/main/c-activities/assets/activities-list-new.png)

[!UICONTROL Activities] のリストには、すべてのアクティビティの概要が表示され、様々なアクションを実行できます。

| 要素 | 説明 |
|--- |--- |
| 左側のナビゲーションパネル | 保存済みまたはライブアクティビティと、失敗または [ ドラフトアクティビティ ](/help/main/c-activities/edit-activity.md) を切り替えます。 |
| [!UICONTROL Show filters] アイコン<P>![ フィルターアイコンを表示 ](/help/main/c-activities/assets/show-filters-icon.png) | フィルターにアクセスするには、リスト上部付近の **[!UICONTROL Show Filters]** アイコンをクリックします。<P>詳しくは、以下の [ アクティビティリストにフィルターを適用する ](#filters) を参照してください。 |
| 検索ボックス | アクティビティをすばやく見つけたり、[!UICONTROL Activity] リストに表示されるアクティビティの数を減らしたりします。 [!UICONTROL Name]、[!UICONTROL URL] または [!UICONTROL ID] で検索できます。 |
| [!UICONTROL Create Activity] | アクティビティを作成します。 様々なアクティビティタイプの作成について詳しくは、以下を参照してください。 <ul><li>[A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[自動配分アクティビティの作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[自動ターゲットアクティビティの作成](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Automated Personalizationアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[ 「エクスペリエンスのターゲット設定」アクティビティの作成 ](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[多変量分析テストの作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Recommendations アクティビティの作成](/help/main/c-recommendations/recommendations.md)</li></ul>各タイプについて詳しくは、以下の [ アクティビティタイプ ](#types) を参照してください。 |
| [!UICONTROL Create mobile preview link]<P>![ その他のアクションメニュー ](/help/main/c-activities/assets/icon-create-mobile-link.png) | [ モバイルプレビューリンク ](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=ja) を使用すると、モバイルアプリアクティビティのエンドツーエンドの簡単な QA を実行できます。<P>**その他のオプション** アイコン（縦並びの省略記号）をクリックし、**モバイルプレビューリンクを作成** を選択したあと、モバイルでテストするアクティビティを選択します。 |
| テーブルをカスタマイズ<P>![ 「テーブルをカスタマイズ」アイコン ](/help/main/c-activities/assets/icon-customize-table.png) | テーブルの右上にある **[!UICONTROL Customize Table]** アイコンをクリックし、目的の列を選択または選択解除して、[!UICONTROL Activity] ータリストに表示する列を変更します。<P>変更内容はアカウントに適用され、[!DNL Target] からログアウトした後もアクティブです。 |
| 一括操作チェックボックス | すべてのアクティビティまたは選択したアクティビティで一括操作を実行します。<P>（権限とアクティビティのステータスに応じて）使用可能なアクションのリストについては、以下の [ クイックアクションの実行 ](#quick-actions) を参照してください。 |
| [!UICONTROL Type] | アクティビティタイプ。 [!UICONTROL Type] 列を使用すると、タイプ別に各アクティビティをすばやく識別できます。 <ul><li>AB-M：手動 [!UICONTROL A/B Test]</li><li>AB-AA: [!UICONTROL Auto-Allocate]</li><li>AB-AT: [!UICONTROL Auto-Target]</li><li>AP: [!UICONTROL Automated Personalization]</li><li>XT: [!UICONTROL Experience Targeting]</li><li>MVT: [!UICONTROL Multivariate Test]</li><li>REC: [!UICONTROL Recommendations]</li></ul>各タイプについて詳しくは、以下の [ アクティビティタイプ ](#types) を参照してください。 |
| [!UICONTROL Name] | アクティビティの名前。 アクティビティ名をクリックすると、そのアクティビティの [!UICONTROL Overview] ページが表示されます。 <P>各アクティビティ名の横にある「**[!UICONTROL Quick Info]**」アイコンをクリックすると、そのアクティビティの詳細がポップアップカードに表示されます。<p>各アクティビティ名の横にある「**[!UICONTROL More actions]**」アイコン（水平省略記号）をクリックしてメニューを開くと、アクティビティに対してクイックアクションを実行できます。 （権限とアクティビティのステータスに応じて） [!UICONTROL Edit]、[!UICONTROL Activate]、[!UICONTROL Deactivate]、[!UICONTROL Copy]、[!UICONTROL Delete] および [!UICONTROL Archive] のアクションを使用できます。 各アクションについて詳しくは、以下の [ クイックアクションの実行 ](#quick-actions) を参照してください。<P>テーブルのヘッダーをクリックすると、名前の昇順または降順でアルファベット順にリストを並べ替えることができます。 |
| [!UICONTROL Status] | アクティビティのステータスは、次のいずれかになります。<ul><li>**ライブ**：アクティビティは現在実行中です。</li><li>**ドラフト**：アクティビティの設定が開始されましたが、アクティビティは [ ドラフトモード ](/help/main/c-activities/edit-activity.md) で、まだ実行する準備が整っていません。</li><li>**スケジュール済み**：アクティビティは、指定された開始日時になるとアクティブ化されます。</li><li>**非アクティブ**：アクティビティは一時停止しているか、非アクティブになっています。</li><li>**同期中**：アクティビティが保存され、[!DNL Target] 配信ネットワークに同期されています。</li><li>**終了**：指定されたアクティビティの終了日時に達し、アクティビティは提供されなくなりました。</li><li>**アーカイブ済み**： アクティビティはアーカイブされています。アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。</li></ul>**注意**: API メソッドを使用して [!DNL Target] UI 外でアクティビティをアクティブ化するなどの、特定のアクションを実行した場合は、更新内容が [!DNL Target] UI に反映されるまで最大 10 分かかる場合があります。 |
| [!UICONTROL Last Updated] | アクティビティが最後に更新された日時。<P>テーブルのヘッダーをクリックして、日付順で昇順または降順にリストを並べ替えます。 |
| [!UICONTROL Priority] | アクティビティの優先度。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>[ 設定 ](/help/main/administrating-target/reporting.md) によって、の [!DNL Target] UI とオプションは異な [!UICONTROL Priority] ます。 従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。 |
| [!UICONTROL Property] | アクティビティの[プロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を表示します。<P>エンタープライズユーザー権限は、[Target Premium](/help/main/c-intro/intro.md#premium) 機能です。 |
| [!UICONTROL Estimated Lift in Revenue] | 100％のオーディエンスが勝者エクスペリエンスを閲覧した場合に予測される売上高の増加を表示します。<P>以下の数式を使用して計算します。<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>この数字は、短縮形の表記で小数点の前が 1 桁だけの場合、最大で小数第 1 位に丸められます。例：$1.6M、$60K、$900、$8.5K、$205K<P>勝者となる十分なデータがない、またはコストの見積もりがないアクティビティの場合、このコラムには「---」と表示されます。<P>詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。 |
| [!UICONTROL Source] | アクティビティが作成された場所を示します：[!DNL Adobe Target]、[Adobe Target API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja)、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja)、[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)、[Adobeモバイルサービス ](https://developer.adobe.com/client-sdks/documentation/)。 |
| [!UICONTROL Location] | アクティビティの URL は、アクティビティが表示される場所を示します。この列を使用すると、アクティビティをすばやく識別して、特定のページで既にアクティビティが実行されているかどうかを判断できます。<P>1 つのアクティビティを複数の URL で実行する場合、リンクには、使用される URL の数が表示されます。 該当するアクティビティのすべての URL のリストを表示するには、このリンクをクリックします。<P>URL に基づいて検索できます。 「検索」ボックスの隣のドロップダウンリストを使用して、「[!UICONTROL URL]」を選択します。 |
| 作成者 | アクティビティを作成したユーザーの名前。 |
| [!UICONTROL Decisioning Method] | 各アクティビティで使用される判定方法：[ サーバーサイド ](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja) または [ クライアントサイド ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)。 |

## アクティビティのタイプ {#types}

[!DNL Target] には、複数のアクティビティタイプがあります。 次の表は、各アクティビティタイプの概要と学習に役立つリンクを示しています。目的に合わせて最適なアクティビティタイプを選択できるように、[Adobe Target Activities ガイド](/help/main/c-activities/target-activities-guide.md)も作成しました。

| アクティビティタイプ | 説明 |
|--- |--- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | A/B テストでは、複数のバージョンの web サイトコンテンツを比較し、事前に指定したテスト期間中に、どのバージョンがコンバージョンを最も多く増やすことができるのかを確認できます。 |
| [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | A/B テストの一種である [!UICONTROL Auto-Allocate] は、複数のエクスペリエンスの中から勝者を特定し、より多くのトラフィックをその勝者に自動的に再割り当てしてコンバージョンを増やし、その間もテストによる学習と実行を続けます。 |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | A/B テストの一種である自動ターゲットは、高度な機械学習を使用して、マーケターが定義した複数の高パフォーマンスのエクスペリエンスを特定し、個々の顧客のプロファイルと類似プロファイルを持つ以前の訪問者の行動に基づいて各訪問者に最適なエクスペリエンスを提供して、コンテンツをパーソナライズしコンバージョンを促進します。 |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] （MVT）では、ページ上の要素内のオファーの組み合わせを比較し、特定のオーディエンスに対して最も効果が高い組み合わせと、アクティビティの成功に最も効果が高い要素を特定します。 |
| [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] （XT）では、マーケターが定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] （AP）は、オファーやメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて各訪問者に様々なバリエーションをマッチさせ、コンテンツをパーソナライズしてコンバージョンを促進します。 |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | レコメンデーションは、サイト上の訪問者のアクティビティに応じて、web サイトの訪問者に製品を提案する方法を決定します。<P>例えば、リュックサックを購入した顧客に対して、ハイキングシューズやトレッキング用のステッキの購入を提案できます。特定の商品を購入した顧客が購入している他の商品を特定できるアルゴリズムを使用して、多くの場合同時に購入されている商品を示すレコメンデーションを作成できます。または、「これを閲覧したユーザー」アルゴリズムを使用して、訪問者が視聴しているビデオに類似したビデオをレコメンデーションすることで、メディアサイトにより多くの時間を費やすよう促すことができます。<P>**メモ**:[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]、[!UICONTROL Experience Targeting] （XT）アクティビティ内にレコメンデーションを含めることもできます。 詳しくは、[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md) を参照してください。この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |

## アクティビティリストへのフィルターの適用 {#filters}

フィルターにアクセスするには、リスト上部付近の **[!UICONTROL Show Filters]** アイコンをクリックします。

![ フィルターオプション ](/help/main/c-activities/assets/show-filters-options.png)

メニューでは、次の属性でアクティビティをフィルタリングできます。

| 属性 | 詳細 |
| --- | --- |
| [!UICONTROL Type] | [ アクティビティタイプ ](#types) でフィルタリングします。 |
| [!UICONTROL Status] | アクティビティステータスでフィルタリングします。 |
| [!UICONTROL Reporting Source] | レポートソースでフィルタリングします。<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md):[!UICONTROL Analytics for Target] （A4T）をレポートソースとして使用するアクティビティを表示します。</li><li>[[!DNL Target]](/help/main/c-reports/reports.md): [!DNL Target] をレポートソースとして使用するアクティビティを表示します。</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md): [!DNL Adobe Customer Analytics] をレポートソースとして使用するアクティビティを表示します。</li></ul> |
| [!UICONTROL Experience Composer] | アクティビティの作成中に Experience Composer が使用されたフィルター：<ul><li>[ ビジュアル ](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md):[!UICONTROL Visual Experience Composer] （VEC）を使用して作成されたアクティビティを表示します。</li><li>[ フォームベース ](/help/main/c-experiences/form-experience-composer.md):[!UICONTROL Form-Based Experience Composer] を使用して作成されたアクティビティを表示します。</li></ul> |
| [!UICONTROL Metrics Type] | アクティビティの作成中に [ 成功指標 ](/help/main/c-activities/r-success-metrics/success-metrics.md) が選択されたフィルター。<ul><li>コンバージョン</li><li>売上高</li><li>エンゲージメント</li></ul> |
| [!UICONTROL Decisioning Method] | 各アクティビティで使用される判定方法でフィルタリングします<ul><li>[ サーバー側 ](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja)：サーバー側判定を使用するアクティビティを表示します。</li><li>[ クライアント側 ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)：クライアント側判定を使用するアクティビティを表示します。</li></ul> |
| [!UICONTROL Activity Source] | 各アクティビティの作成に使用されるアクティビティソースでフィルタリングします。<ul><li>[!DNL Adobe Target]</li><li>[Adobe Target API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja)</li><li>[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)</li><li>[Adobe Mobile サービス](https://developer.adobe.com/client-sdks/documentation/)</li></ul> |
| [!UICONTROL Property] | アクティビティが作成された [ プロパティ ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) でフィルタリングします。 |

## クイックアクションの実行 {#quick-actions}

各アクティビティ名の横にある「**[!UICONTROL More actions]**」アイコン（水平省略記号）をクリックしてメニューを開くと、アクティビティに対してクイックアクションを実行できます。

![ クイックアクションオプション ](/help/main/c-activities/assets/quick-actions.png)

使用できるアクションは次のとおりです（権限とアクティビティのステータスによって異なります）。

| アクション | 説明 |
| --- | --- |
| [!UICONTROL Edit] | アクティビティを変更します。どのアクティビティも編集できます。<P>アクティビティを編集できる様々な方法について詳しくは、[ アクティビティを編集またはドラフトとして保存 ](/help/main/c-activities/edit-activity.md) を参照してください。 |
| [!UICONTROL Deactivate] | ライブまたは日時指定のアクティビティを停止します。非アクティブ化されたアクティビティは、再アクティブ化またはアーカイブできます。<P>アクティビティを非アクティブ化またはアーカイブした後に再度アクティブ化した場合、非アクティブ化またはアーカイブ以前からアクティビティに含まれていた訪問者は、再アクティブ化の後も引き続きアクティビティに含まれます。非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL Activate] | 非アクティブなアクティビティまたはアクティブ化する準備が整ったアクティビティを開始します。 |
| [!UICONTROL Archive] | アクティビティをアーカイブに送信します。デフォルトでは、アーカイブされたアクティビティは [!UICONTROL Activities] リストに表示されなくなります。 アクティビティリストのフィルターを変更して、アーカイブ済みアクティビティが含まれるようにして、表示されるようにします。アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。<P>アクティビティをディアクティベートまたはアーカイブしてから、後で再アクティベートすると、ある訪問者が、アクティベートを解除またはアーカイブする前にそのアクティビティにあった場合、その訪問者は再アクティベート後も引き続きそのアクティビティの対象となります。 非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL Copy] | アクティビティをコピーします。どのアクティビティもコピーできます。アクティビティをコピーすると、同じ名前に「Copy」と付いた、新しいアクティビティが作成されます。例えば、「ブラウザーオファー」というテストは、「ブラウザーオファー Copy」という名前でコピーされます。<P>ビジュアルオファーは、アクティビティと共にコピーされます。元のアクティビティに影響を与えることなく、コピー内で安全にオファーを編集できます。唯一の例外は、コンテンツ／アセットフォルダー内に保存したオファーおよび画像です。 |
| [!UICONTROL Delete] | ドラフトまたはアクティビティを削除します。<P>**注意**：削除されたアクティビティは復元できません。 このアクティビティが再び必要になることがない場合を除き、[!UICONTROL Archive] のアクションを使用します。 その後、必要に応じてアクティビティを再アクティブ化できます。 |

## 注意点

[!UICONTROL Activity] リストに関する次の詳細に注意してください。

* アーカイブされたアクティビティと終了したアクティビティは、[!UICONTROL Activities] リストには表示されません。 これらのアクティビティを表示するには、リストの上部にある [ フィルターアイコン ](#filters) を使用してアクティビティをフィルタリングします。
* [!DNL Target Classic] で最初に作成されたアクティビティが非アクティブ化または削除されると、[!DNL Target Standard/Premium] から削除されます。 最初に [!DNL Target Classic] で作成した削除されたアクティビティは、[!DNL Target Standard/Premium] の [!UICONTROL Archive] フォルダーには送信されません。 アーカイブ済みフォルダー機能は、[!DNL Target Standard/Premium] で作成されたアクティビティにのみ適用されます。
* [!UICONTROL Automated Personalization] （AP）、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] 以外のすべてのアクティビティタイプでは、データソースとして [!DNL Target] または [!DNL Adobe Analytics] のいずれかを使用できます。 [!UICONTROL AP]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] は *常に* データ [!DNL Target] 使用します。
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
| 一意のセレクター数 | 300。異なるエクスペリエンスでセレクターが繰り返される場合は、1 回とカウントされます。 ただし、同じエクスペリエンスで繰り返される場合は、再度カウントされます。 |
| 各エクスペリエンスのオファー | 350 |
| 指標のクリック追跡セレクター数 | 50 |
| 指標の mbox 数 | 50 |
| オーディエンスと場所 | オーディエンスと場所（mbox）の 50 の組み合わせは、50 以下にする必要があります。 |

これらの制限を超えると、アクティビティを保存できません。

アクティビティ内のこれらの項目の数を増やすと、アクティビティを [!DNL Target] 間で同期するのに要する時間も長くなります。

V[!UICONTROL isual Experience Composer] VEC のその他の制限については、[Visual Experience Composer の制限事項 ](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) を参照してください。

## [!DNL Target] 以外で更新されたアクティビティの属性を [!DNL Target] に読み込む {#section_802B0D174E6A44E1A96F404CA81AAE44}

[!DNL Target] で作成されたアクティビティが [!DNL Target] の外部から更新された場合（例：API を使用）、`thirdpartyId`、`startDate`、`endDate`、`status`、`priority` および `marketingCloudMetadata(remoteModifiedBy)` のアクティビティ属性が [!DNL Target] にインポートされます。

このインポートジョブは、アクティビティページが開かれたときに、最大 10 分の遅延で実行されます。

## トレーニングビデオ {#section_BE80D13A2E81460C885F902010E1AD87}

次のビデオでは、この記事で説明した概念について詳しく説明しています。

### アクティビティのタイプ（9:03）

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティのタイプについて説明しています。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

