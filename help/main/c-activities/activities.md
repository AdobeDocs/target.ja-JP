---
keywords: アクティビティリスト；アクティビティ；アクティビティ；アクティビティタイプ；アクティビティの編集；アクティビティ属性；アクティビティリストフィルター；アクティビティの制限；パーソナライズ機能；パーソナライゼーション
description: アクティビティを使用して、特定のオーディエンス向けにコンテンツをパーソナライズし  [!DNL Adobe Target]  ページのデザインをテストします。
title: ' [!DNL Target] を使用してコンテンツをパーソナライズし、ページのデザインをテストするにはどうすればよいですか？'
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: c445775bc96623f9742f648a82ed9b4e64bd463a
workflow-type: tm+mt
source-wordcount: '2291'
ht-degree: 25%

---

# アクティビティの概要

特定のオーディエンス向けに、アクティビティを使用してコンテンツをパーソナライズし、ページのデザイン [!DNL Adobe Target] テストします。

例えば、夏用の婦人靴の情報をハイライトするランディングページと夏用の一般衣料をハイライトする別のランディングページの 2 つをテストするアクティビティを作成できます。アクティビティは、これらの各ランディングページが表示されるタイミングを制御する条件と、より成功したページを決定する指標を決定します。 アクティビティは、特定の日付の間など、特定の条件が満たされた場合に開始し終了するように設定されます。 または、アクティビティが承認されたときに開始し、非アクティブ化されたときに終了するように選択できます。

アクティビティを作成する際は、入念な計画が必要です。アクティビティの開始時刻と期間を指定します。 その後、オファーの一覧を作成し、それぞれにターゲットとなるオーディエンスを割り当てます。

## アクティビティリスト {#section_DE8E2DB30D534962A931EF8BB48240F5}

[!UICONTROL Activities] リストは、[!DNL Target] を開いたときのデフォルトのビューです。 このページからアクティビティを作成し、既存のアクティビティを管理できます。

また、[!UICONTROL Activities] UI の上部にある「[!UICONTROL Activities]」タブをクリックして、[!DNL Target] リストを表示することもできます。

[!UICONTROL Activities] リストには、[!DNL Target] 実装のすべてのアクティビティの概要が表示され、様々なアクションを実行できます。

次の表に、[!UICONTROL Activities] UI の [!DNL Target] リストの様々な要素を示します。

| 要素 | 説明 |
|--- |--- |
| [!UICONTROL Show filters] アイコン<P>![ フィルターアイコンを表示 ](/help/main/assets/icons/Filter.svg) | フィルターにアクセスするには、リストの上部付近にある **[!UICONTROL Show Filters]** アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、[!UICONTROL Decisioning Source]、[!UICONTROL Activity Source] および [!UICONTROL Properties] でアクティビティをフィルタリングします。<P>設定するフィルターは、現在のセッション全体で永続的です。<P>詳しくは、以下の [ リストにフィルターを適用する [!UICONTROL Activities] を参 ](#filters) してください。 |
| 検索フィールド | アクティビティをすばやく見つけたり、[!UICONTROL Activity] リストに表示されるアクティビティの数を減らしたりします。 ドロップダウンを使用して、[!UICONTROL Activity Name]、[!UICONTROL URL] または [!UICONTROL ID] で検索できます。<P>設定する検索オプションは、現在のセッション全体で永続的です。 |
| [!UICONTROL Create Activity] | アクティビティを作成します。<P>様々なアクティビティタイプの作成について詳しくは、以下を参照してください。 <ul><li>[[!UICONTROL A/B Test] アクティビティの作成 ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[[!UICONTROL Auto-Allocate] アクティビティの作成 ](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[[!UICONTROL Auto-Target] アクティビティの作成 ](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[[!UICONTROL Automated Personalization] アクティビティの作成 ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[[!UICONTROL Experience Targeting] アクティビティの作成 ](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[ アクティビティの作成 ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[[!UICONTROL Recommendations] アクティビティの作成 ](/help/main/c-recommendations/recommendations.md)</li></ul>各タイプについて詳しくは、以下の [ アクティビティタイプ ](#types) を参照してください。 |
| [!UICONTROL Create mobile preview link]<P>![ その他のアクションメニュー ](/help/main/assets/icons/MoreVertical.svg) | [ モバイルプレビューリンク ](https://experienceleague.adobe.com/en/docs/target-dev/developer/mobile-apps/target-mobile-preview) を使用すると、モバイルアプリアクティビティのエンドツーエンドの簡単な QA を実行できます。<P>**その他のオプション** アイコンをクリックし、**モバイルプレビューリンクを作成** を選択したあと、モバイルでテストするアクティビティを選択します。 |
| テーブルをカスタマイズ<P>![ 「テーブルをカスタマイズ」アイコン ](/help/main/assets/icons/ColumnSetting.svg) | ページの右上にある [!UICONTROL Activity] アイコンをクリックし、目的の列を選択または選択解除して、**[!UICONTROL Customize Table]** リストに表示する列を変更します。<P>変更内容はアカウントに適用され、[!DNL Target] からログアウトした後もアクティブです。 |
| 一括操作チェックボックス<P>![ 一括操作アイコン ](/help/main/assets/icons/Rectangle.svg) | すべてのアクティビティまたは選択したアクティビティで一括操作を実行します。<P>（権限とアクティビティのステータスに応じて）使用可能なアクションのリストについては、以下の [ クイックアクションの実行 ](#quick-actions) を参照してください。 |
| [!UICONTROL Type] | アクティビティタイプ。 [!UICONTROL Type] 列を使用すると、タイプ別に各アクティビティをすばやく識別できます。 <ul><li>**AB-M**：手動 [!UICONTROL A/B Test]</li><li>**AB-AA**: [!UICONTROL Auto-Allocate]</li><li>**AB-AT**: [!UICONTROL Auto-Target]</li><li>**AP**: [!UICONTROL Automated Personalization]</li><li>**XT**: [!UICONTROL Experience Targeting]</li><li>**MVT**: [!UICONTROL Multivariate Test]</li><li>**REC**: [!UICONTROL Recommendations]</li></ul>各タイプについて詳しくは、以下の [ アクティビティタイプ ](#types) を参照してください。 |
| [!UICONTROL Name] | アクティビティの名前。 各アクティビティ名の横にある **[!UICONTROL Quick Info]** アイコン ![ クイック情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックすると、[!UICONTROL Activity ID]、[!UICONTROL Activity Objective]、[!UICONTROL Activity Location]、[!UICONTROL Goal]、[!UICONTROL Status] など、ポップアップカードにそのアクティビティに関する詳細情報が表示されます。<P>各アクティビティ名の横にある **[!UICONTROL More actions]** のアイコン ![ その他のアクションアイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてメニューを開き、アクティビティに対してクイックアクションを実行できます。 （権限とアクティビティのステータスに応じて） [!UICONTROL Edit]、[!UICONTROL Activate]、[!UICONTROL Deactivate]、[!UICONTROL Copy]、[!UICONTROL Delete] および [!UICONTROL Archive] のアクションを使用できます。<P>各アクションについて詳しくは、以下の [ クイックアクションの実行 ](#quick-actions) を参照してください。<P>テーブルのヘッダーをクリックすると、名前の昇順または降順でアルファベット順にリストを並べ替えることができます。 |
| [!UICONTROL Status] | アクティビティのステータスは、次のいずれかになります。<ul><li>**[!UICONTROL Live]**：アクティビティは現在実行中です。</li><li>**[!UICONTROL Scheduled]**：指定された開始日時に達すると、アクティビティをアクティブ化する準備が整います。</li><li>**[!UICONTROL Inactive]**: アクティビティが一時停止または非アクティブ化されました。</li><li>**[!UICONTROL Ended]**：指定されたアクティビティの終了日時に達し、アクティビティは提供されなくなりました。</li><li>**[!UICONTROL Archived]**：アクティビティがアーカイブされました。 アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。</li></ul>**注意**: API メソッドを使用して [!DNL Target] UI 外でアクティビティをアクティブ化するなどの、特定のアクションを実行した場合は、更新内容が [!DNL Target] UI に反映されるまで最大 10 分かかる場合があります。 |
| [!UICONTROL Last Updated] | アクティビティが最後に更新された日時。<P>テーブルのヘッダーをクリックして、日付順で昇順または降順にリストを並べ替えます。 |
| [!UICONTROL Priority] | アクティビティの優先度。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>[ 設定 ](/help/main/administrating-target/reporting.md) によって、の [!DNL Target] UI とオプションは異な [!UICONTROL Priority] ます。 従来の設定である [!UICONTROL Low]、[!UICONTROL Medium]、[!UICONTROL High] を使用するか、0～999 の細かい優先度を有効にすることができます。<P>優先度の設定について詳しくは、[ 目標と設定 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) の *アクティビティ設定* の *優先度* を参照してください。 |
| [!UICONTROL Property] | アクティビティの[プロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を表示します。<P>エンタープライズユーザー権限は [0}Target Premium} 機能です。](/help/main/c-intro/intro.md#premium) |
| [!UICONTROL Estimated Lift in Revenue] | 100％のオーディエンスが勝者エクスペリエンスを閲覧した場合に予測される売上高の増加を表示します。<P>以下の数式を使用して計算します。<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>この数字は、短縮形の表記で小数点の前が 1 桁だけの場合、最大で小数第 1 位に丸められます。例：$1.6M、$60K、$900、$8.5K、$205K<P>勝者となる十分なデータがない、またはコストの見積もりがないアクティビティの場合、このコラムには「---」と表示されます。<P>詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。 |
| [!UICONTROL Source] | アクティビティが作成された場所を示します：[!DNL Adobe Target]、[Adobe Target API](https://experienceleague.adobe.com/en/docs/target-dev/developer/overview)、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja)、[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja) または [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/)。 |
| [!UICONTROL Author] | アクティビティを作成したユーザーの名前。 |
| [!UICONTROL Decisioning Method] | 各アクティビティで使用される判定方法：[ サーバーサイド ](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja) または [ クライアントサイド ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)。 |

<!--|[!UICONTROL Location]|The URL for the activity identifies where the activity is displayed. This column helps you quickly identify an activity and determine whether a particular page already has an activity running on it.<P>If an activity runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity.<P>You can search based on the URL. Use the drop-down list next to the search box and select [!UICONTROL URL].|-->

## アクティビティのタイプ {#types}

[!DNL Target] には、複数のアクティビティタイプがあります。 次の表は、各アクティビティタイプの概要と学習に役立つリンクを示しています。目的に合わせて最適なアクティビティタイプを選択できるように、[Adobe Target アクティビティガイド ](/help/main/c-activities/target-activities-guide.md) を使用してください。

| アクティビティタイプ | 説明 |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | A/B テストでは、複数のバージョンの web サイトコンテンツを比較し、事前に指定したテスト期間中に、どのバージョンがコンバージョンを最も多く増やすことができるのかを確認できます。 |
| [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | A/B テストの一種である [!UICONTROL Auto-Allocate] は、複数のエクスペリエンスの中から勝者を特定し、より多くのトラフィックをその勝者に自動的に再割り当てしてコンバージョンを増やし、その間もテストによる学習と実行を続けます。 |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | A/B テストの一種である自動ターゲットは、高度な機械学習を使用して、マーケターが定義した複数の高パフォーマンスのエクスペリエンスを特定し、個々の顧客のプロファイルと類似プロファイルを持つ以前の訪問者の行動に基づいて各訪問者に最適なエクスペリエンスを提供して、コンテンツをパーソナライズしコンバージョンを促進します。 |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] （MVT）では、ページ上の要素内のオファーの組み合わせを比較し、特定のオーディエンスに対して最も効果が高い組み合わせと、アクティビティの成功に最も効果が高い要素を特定します。 |
| [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] （XT）では、マーケターが定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。 |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] （AP）は、オファーやメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて各訪問者に様々なバリエーションをマッチさせ、コンテンツをパーソナライズしてコンバージョンを促進します。 |
| [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | レコメンデーションは、サイト上の訪問者のアクティビティに応じて、web サイトの訪問者に製品を提案する方法を決定します。<P>例えば、リュックサックを購入した顧客に対して、ハイキングシューズやトレッキング用のステッキの購入を提案できます。特定の商品を購入した顧客が購入している他の商品を特定できるアルゴリズムを使用して、多くの場合同時に購入されている商品を示すレコメンデーションを作成できます。または、「これを閲覧したユーザー」アルゴリズムを使用して、訪問者が視聴しているビデオに類似したビデオをレコメンデーションすることで、メディアサイトにより多くの時間を費やすよう促すことができます。<P>**メモ**:[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]、[!UICONTROL Experience Targeting] （XT）アクティビティ内にレコメンデーションを含めることもできます。 詳しくは、[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md) を参照してください。この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |

## アクティビティリストへのフィルターの適用 {#filters}

フィルターにアクセスするには、リスト上部付近の **[!UICONTROL Show Filters]** アイコン ![ フィルターを表示アイコン ](/help/main/assets/icons/Filter.svg)）をクリックします。

メニューでは、次の属性でアクティビティをフィルタリングできます。

| 属性 | 詳細 |
| --- | --- |
| [!UICONTROL Type] | [ アクティビティタイプ ](#types) でフィルタリングします。 |
| [!UICONTROL Status] | アクティビティステータスでフィルタリングします。<ul><li>**[!UICONTROL Live]**：アクティビティは現在実行中です。</li><li>**[!UICONTROL Scheduled]**：指定された開始日時に達すると、アクティビティをアクティブ化する準備が整います。</li><li>**[!UICONTROL Inactive]**: アクティビティが一時停止または非アクティブ化されました。</li><li>**[!UICONTROL Ended]**：指定されたアクティビティの終了日時に達し、アクティビティは提供されなくなりました。</li><li>**[!UICONTROL Archived]**：アクティビティがアーカイブされました。 アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。</li></ul>非推奨（廃止予定）の [!UICONTROL Save as Draft] と [!UICONTROL Syncing] のステータスについて詳しくは、この表の下のメモを参照してください。 |
| [!UICONTROL Reporting Source] | レポートソースでフィルタリングします。<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md):[!UICONTROL Analytics for Target] （A4T）をレポートソースとして使用するアクティビティを表示します。</li><li>[[!DNL Target]](/help/main/c-reports/reports.md): [!DNL Target] をレポートソースとして使用するアクティビティを表示します。</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md): [!DNL Adobe Customer Analytics] をレポートソースとして使用するアクティビティを表示します。</li></ul> |
| [!UICONTROL Experience Composer] | アクティビティの作成中に Experience Composer が使用されたフィルター：<ul><li>[ ビジュアル ](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md):[!UICONTROL Visual Experience Composer] （VEC）を使用して作成されたアクティビティを表示します。</li><li>[ フォームベース ](/help/main/c-experiences/form-experience-composer.md):[!UICONTROL Form-Based Experience Composer] を使用して作成されたアクティビティを表示します。</li></ul> |
| [!UICONTROL Metrics Type] | アクティビティの作成中に [ 成功指標 ](/help/main/c-activities/r-success-metrics/success-metrics.md) が選択されたフィルター。<ul><li>[!UICONTROL Conversion]</li><li>[!UICONTROL Revenue]</li><li>[!UICONTROL Engagement]</li><li>[!UICONTROL Use an Analytics metric]</lI></ul> |
| [!UICONTROL Decisioning Method] | 各アクティビティで使用される判定方法でフィルタリングします。<ul><li>[ サーバー側 ](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja)：サーバー側判定を使用するアクティビティを表示します。</li><li>[ クライアント側 ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)：クライアント側判定を使用するアクティビティを表示します。</li></ul> |
| [!UICONTROL Activity Source] | 各アクティビティの作成に使用されるアクティビティソースでフィルタリングします。<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Property] | アクティビティが作成された [ プロパティ ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) でフィルタリングします。 |


>[!NOTE]
>
>**更新された UI でアクティビティ状態を更新**：ユーザーインターフェイスの最新の更新により、[!UICONTROL Save as Draft] と [!UICONTROL Syncing] の状態は使用できなくなりました。 これは、すべてのアクティビティの作成と編集が、GraphQL レイヤーを使用してバックエンド [!DNL Target] 配信システム内で直接行われ、より合理化され効率的なプロセスが確保されるからです。
>
>以前は、アクティビティは、まず [!DNL Target] UI に保存されてから、これらの中間状態を必要とする [!DNL Target] 配信システムに同期されていました。 現在は該当しないので、これらの状態は削除されました。
>
>[!DNL Adobe] では、一部のお客様が [!UICONTROL Save as Draft] 機能に関心を持っていることを理解しています。 このフィードバックをお待ちしておりますが、この機能は現在サポートされていません。

## クイックアクションの実行 {#quick-actions}

各アクティビティ名の横にある **[!UICONTROL More actions]** アイコン ![ その他のアクションメニュー ](/help/main/assets/icons/MoreVertical.svg)）をクリックしてメニューを開き、アクティビティに対してクイックアクションを実行できます。

使用できるアクションは次のとおりです（権限とアクティビティのステータスによって異なります）。

| アクション | 説明 |
| --- | --- |
| [!UICONTROL Edit] | アクティビティを変更します。どのアクティビティも編集できます。<P>アクティビティを編集できる様々な方法について詳しくは、[ アクティビティを編集またはドラフトとして保存 ](/help/main/c-activities/edit-activity.md) を参照してください。 |
| [!UICONTROL Deactivate] | ライブまたは日時指定のアクティビティを停止します。非アクティブ化されたアクティビティは、再アクティブ化またはアーカイブできます。<P>アクティビティを非アクティブ化またはアーカイブした後に再度アクティブ化した場合、非アクティブ化またはアーカイブ以前からアクティビティに含まれていた訪問者は、再アクティブ化の後も引き続きアクティビティに含まれます。非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL Activate] | 非アクティブなアクティビティまたはアクティブ化する準備が整ったアクティビティを開始します。 |
| [!UICONTROL Archive] | アクティビティをアーカイブに送信します。デフォルトでは、アーカイブされたアクティビティは [!UICONTROL Activities] リストに表示されなくなります。 [!UICONTROL Activities] リストのフィルターを変更してアーカイブされたアクティビティを含めると、アクティビティを表示できます。 アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。<P>アクティビティをディアクティベートまたはアーカイブしてから、後で再アクティベートすると、ある訪問者が、アクティベートを解除またはアーカイブする前にそのアクティビティにあった場合、その訪問者は再アクティベート後も引き続きそのアクティビティの対象となります。 非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL Copy] | アクティビティをコピーします。どのアクティビティもコピーできます。アクティビティをコピーすると、同じ名前に「Copy」と付いた、新しいアクティビティが作成されます。例えば、「ブラウザーオファー」というテストは、「ブラウザーオファー Copy」という名前でコピーされます。<P>ビジュアルオファーは、アクティビティと共にコピーされます。元のアクティビティに影響を与えることなく、コピー内で安全にオファーを編集できます。唯一の例外は、コンテンツ／アセットフォルダー内に保存したオファーおよび画像です。 |
| [!UICONTROL Delete] | ドラフトまたはアクティビティを削除します。<P>**注意**：削除されたアクティビティは復元できません。 このアクティビティが再び必要になることがない場合を除き、[!UICONTROL Archive] のアクションを使用します。 その後、必要に応じてアクティビティを再アクティブ化できます。 |

## 注意点

[!UICONTROL Activity] リストに関する次の詳細に注意してください。

* [!UICONTROL Archived] アクティビティと [!UICONTROL Ended] アクティビティは、[!UICONTROL Activities] リストには表示されません。 これらのアクティビティを表示するには、リストの上部にある [ フィルターアイコン ](#filters) （![ フィルターを表示アイコン ](/help/main/assets/icons/Filter.svg)）を使用してアクティビティをフィルタリングします。
* [!DNL Target Classic] で最初に作成されたアクティビティが非アクティブ化または削除されると、[!DNL Target Standard/Premium] から削除されます。 最初に [!DNL Target Classic] で作成した削除されたアクティビティは、[!UICONTROL Archive] の [!DNL Target Standard/Premium] フォルダーには送信されません。 アーカイブ済みフォルダー機能は、[!DNL Target Standard/Premium] で作成されたアクティビティにのみ適用されます。
* [!UICONTROL Automated Personalization] （AP）、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] 以外のすべてのアクティビティタイプでは、データソースとして [!DNL Target] または [!DNL Adobe Analytics] のいずれかを使用できます。 [!UICONTROL Automated Personalization]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] は *常に* データ [!DNL Target] 使用します。
* アクティビティは複数のチャネルで利用可能です。

   * Web およびモバイルサイト
   * インターネットに接続された画面およびデバイス（キオスクや ATM を含む）
   * メールや他の購買チャネルまたはパートナーサイト
   * モバイルアプリ
   * タグ付きコンテンツを配信できる他の場所すべて

## 制限事項 {#section_049D4684403A4E07B998067EB8E9BE56}

各 [!DNL Target] アクティビティには、次のコンテンツ制限があります。

| 項目 | 制限 |
|--- |--- |
| 一意のセレクター数 | 300。異なるエクスペリエンスでセレクターが繰り返される場合は、1 回とカウントされます。 ただし、同じエクスペリエンスで繰り返される場合は、再度カウントされます。 |
| 各エクスペリエンスのオファー | 350 |
| 指標のクリック追跡セレクター数 | 50 |
| 指標の mbox 数 | 50 |
| オーディエンスと場所 | オーディエンスと場所（mbox）の 50 の組み合わせは、50 以下にする必要があります。 |

これらの制限を超えると、アクティビティを保存できません。

アクティビティ内のこれらの項目の数を増やすと、アクティビティを [!DNL Target] 間で同期するのに要する時間も長くなります。

[!UICONTROL Visual Experience Composer] （VEC）のその他の制限については、[Visual Experience Composer の制限事項 ](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) を参照してください。

## [!DNL Target] 以外で更新されたアクティビティの属性を [!DNL Target] に読み込む {#section_802B0D174E6A44E1A96F404CA81AAE44}

[!DNL Target] で作成されたアクティビティが [!DNL Target] の外部から更新された場合（例：API を使用）、[!DNL Target]、`thirdpartyId`、`startDate`、`endDate`、`status` および `priority` のアクティビティ属性が `marketingCloudMetadata(remoteModifiedBy)` にインポートされます。

このインポートジョブは、[!UICONTROL Activities] ータリストが開かれたときに、最大 10 分の遅延で実行されます。

