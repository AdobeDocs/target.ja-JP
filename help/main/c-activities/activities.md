---
keywords: アクティビティリスト；アクティビティ；アクティビティ；アクティビティタイプ；アクティビティの編集；アクティビティ属性；アクティビティリストフィルター；アクティビティの制限；パーソナライズ機能；パーソナライゼーション
description: でのアクティビティの仕組みを説明します [!DNL Target] では、特定のオーディエンス対してコンテンツをパーソナライズし、ページのデザインをテストできます。
title: を使用してコンテンツをパーソナライズし、ページのデザインをテストする方法 [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: be63fa4c89f229e3f4566cb400e1268d2cdf08d2
workflow-type: tm+mt
source-wordcount: '2290'
ht-degree: 36%

---

# アクティビティ

でのアクティビティ [!DNL Adobe Target] では、特定のオーディエンス対してコンテンツをパーソナライズし、ページのデザインをテストできます。

例えば、夏用の婦人靴の情報をハイライトするランディングページと夏用の一般衣料をハイライトする別のランディングページの 2 つをテストするアクティビティを作成できます。アクティビティによって、これらの各ランディングページをいつ表示するかを制御する条件や、成功度の高いページを判断する指標を定義できます。アクティビティは、特定の条件が満たされたときに開始および終了するよう設定できます。例えば、具体的な日付の範囲による期間の設定や、アクティビティが承認されたときに開始し非アクティブになったときに終了する設定ができます。

アクティビティを作成する際は、入念な計画が必要です。アクティビティの開始時刻と期間を指定します。 その後、オファーの一覧を作成し、それぞれにターゲットとなるオーディエンスを割り当てます。

## アクティビティリスト {#section_DE8E2DB30D534962A931EF8BB48240F5}

この [!UICONTROL Activities] リストは、を開いたときのデフォルトのビューです [!DNL Target]. このページからアクティビティを作成し、既存のアクティビティを管理できます。

を表示することもできます [!UICONTROL Activities] 「」をクリックしてリストを表示する [!UICONTROL Activities] 上部のタブ [!DNL Target] UI。

![アクティビティリスト](/help/main/c-activities/assets/activities-list-new.png)

この [!UICONTROL Activities] リストでは、すべてのアクティビティの概要が表示され、様々なアクションを実行できます。

| 要素 | 説明 |
|--- |--- |
| 左側のナビゲーションパネル | 保存済みまたはライブアクティビティと失敗または [ドラフトアクティビティ](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Show filters] アイコン<P>![フィルターアイコンを表示](/help/main/c-activities/assets/show-filters-icon.png) | 「」をクリックしてフィルターにアクセスする **[!UICONTROL Show Filters]** アイコンがリスト上部付近に表示されます。<P>詳しくは、を参照してください [アクティビティリストへのフィルターの適用](#filters) 下。 |
| 検索ボックス | アクティビティをすばやく見つけたり、 [!UICONTROL Activity] リスト。 次から検索できます [!UICONTROL Name], [!UICONTROL URL]、または [!UICONTROL ID]. |
| [!UICONTROL Create Activity] | アクティビティを作成します。 様々なアクティビティタイプの作成について詳しくは、以下を参照してください。 <ul><li>[A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[自動配分アクティビティの作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[自動ターゲットアクティビティの作成](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Automated Personalizationアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[多変量分析テストの作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Recommendations アクティビティの作成](/help/main/c-recommendations/recommendations.md)</li></ul>各タイプの詳細については、を参照してください [アクティビティタイプ](#types) 下。 |
| [!UICONTROL Create mobile preview link]<P>![その他のアクションメニュー](/help/main/c-activities/assets/icon-create-mobile-link.png) | 使用方法 [モバイルプレビューリンク](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=ja) モバイルアプリアクティビティのエンドツーエンドの QA を容易に実行する。<P>「」をクリックします **その他のオプション** アイコン（垂直省略記号）をクリックし、 **モバイルプレビューリンクを作成**&#x200B;次に、モバイルでテストするアクティビティを選択します。 |
| テーブルをカスタマイズ<P>![「テーブルをカスタマイズ」アイコン](/help/main/c-activities/assets/icon-customize-table.png) | に表示する列の変更 [!UICONTROL Activity] 「」をクリックしてリストを表示する **[!UICONTROL Customize Table]** アイコンをクリックし、目的の列を選択または選択解除します。<P>変更内容はアカウントに適用され、からログアウトした後もアクティブです [!DNL Target]. |
| 一括操作チェックボックス | すべてのアクティビティまたは選択したアクティビティで一括操作を実行します。<P>使用可能なアクションのリストについては（権限とアクティビティのステータスに応じて）を参照してください。 [クイックアクションの実行](#quick-actions) 下。 |
| [!UICONTROL Type] | アクティビティタイプ。 この [!UICONTROL Type] 列を使用すると、タイプ別に各アクティビティをすばやく識別できます。 <ul><li>AB-M：手動 [!UICONTROL A/B Test]</li><li>AB-AA: [!UICONTROL Auto-Allocate]</li><li>AB-AT: [!UICONTROL Auto-Target]</li><li>アプリ： [!UICONTROL Automated Personalization]</li><li>XT: [!UICONTROL Experience Targeting]</li><li>MVT: [!UICONTROL Multivariate Test]</li><li>レコード : [!UICONTROL Recommendations]</li></ul>各タイプの詳細については、を参照してください [アクティビティタイプ](#types) 下。 |
| [!UICONTROL Name] | アクティビティの名前。 アクティビティ名をクリックすると、そのアクティビティが表示されます [!UICONTROL Overview] ページ。 <P>「」をクリックします **[!UICONTROL Quick Info]** 各アクティビティ名の横にあるアイコンをクリックすると、そのアクティビティの詳細がポップアップカードに表示されます。<p>「」をクリックします **[!UICONTROL More actions]** 各アクティビティ名の横にあるアイコン（水平省略記号）をクリックすると、アクティビティに対してクイックアクションを実行できるメニューが開きます。 使用できるアクションは次のとおりです（権限とアクティビティのステータスによって異なります）。 [!UICONTROL Edit], [!UICONTROL Activate], [!UICONTROL Deactivate], [!UICONTROL Copy], [!UICONTROL Delete]、および [!UICONTROL Archive]. 各アクションの詳細については、を参照してください [クイックアクションの実行](#quick-actions) 下。<P>テーブルのヘッダーをクリックすると、名前の昇順または降順でアルファベット順にリストを並べ替えることができます。 |
| [!UICONTROL Status] | アクティビティのステータスは、次のいずれかになります。<ul><li>**ライブ**：アクティビティは現在実行中です。</li><li>**ドラフト**：アクティビティの設定が開始されましたが、アクティビティはにあります [ドラフトモード](/help/main/c-activities/edit-activity.md) およびはまだ実行する準備ができていません。</li><li>**スケジュール済み**：アクティビティは、指定された開始日時になるとアクティブ化されます。</li><li>**非アクティブ**：アクティビティは一時停止しているか、非アクティブになっています。</li><li>**同期中**：アクティビティが保存され、に同期されています [!DNL Target] 配信ネットワーク。</li><li>**終了**：指定されたアクティビティの終了日時に達し、アクティビティが提供されなくなった。</li><li>**アーカイブ済み**： アクティビティはアーカイブされています。アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。</li></ul>**注意**：の外部でアクティビティをアクティブ化するなど、特定のアクションを実行する場合 [!DNL Target] UI で API メソッドを使用する場合、更新がに反映されるまで最大 10 分かかる場合があります [!DNL Target] UI。 |
| [!UICONTROL Last Updated] | アクティビティが最後に更新された日時。<P>テーブルのヘッダーをクリックして、日付順で昇順または降順にリストを並べ替えます。 |
| [!UICONTROL Priority] | アクティビティの優先度。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>状況によって [設定](/help/main/administrating-target/reporting.md), [!DNL Target] の UI とオプション [!UICONTROL Priority] 変化する。 従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。 |
| [!UICONTROL Property] | アクティビティの[プロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を表示します。<P>エンタープライズユーザー権限はです [Target Premium](/help/main/c-intro/intro.md#premium) 機能 |
| [!UICONTROL Estimated Lift in Revenue] | 100％のオーディエンスが勝者エクスペリエンスを閲覧した場合に予測される売上高の増加を表示します。<P>以下の数式を使用して計算します。<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>この数字は、短縮形の表記で小数点の前が 1 桁だけの場合、最大で小数第 1 位に丸められます。例：$1.6M、$60K、$900、$8.5K、$205K<P>勝者となる十分なデータがない、またはコストの見積もりがないアクティビティの場合、このコラムには「---」と表示されます。<P>詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。 |
| [!UICONTROL Source] | アクティビティが作成された場所を示します。 [!DNL Adobe Target], [ADOBE TARGET API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)、または [Mobile Services のAdobe](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Location] | アクティビティの URL は、アクティビティが表示される場所を示します。この列を使用すると、アクティビティをすばやく識別して、特定のページで既にアクティビティが実行されているかどうかを判断できます。<P>1 つのアクティビティを複数の URL で実行する場合、リンクには、使用される URL の数が表示されます。 該当するアクティビティのすべての URL のリストを表示するには、このリンクをクリックします。<P>URL に基づいて検索できます。 検索ボックスの横にあるドロップダウンリストを使用して、以下の項目を選択します。 [!UICONTROL URL]. |
| 作成者 | アクティビティを作成したユーザーの名前。 |
| [!UICONTROL Decisioning Method] | 各アクティビティで使用される判定方法： [サーバー側](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja) または [クライアントサイド](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

## アクティビティのタイプ {#types}

[!DNL Target] には、複数のアクティビティタイプが含まれます。 次の表は、各アクティビティタイプの概要と学習に役立つリンクを示しています。目的に合わせて最適なアクティビティタイプを選択できるように、[Adobe Target Activities ガイド](/help/main/c-activities/target-activities-guide.md)も作成しました。

| アクティビティタイプ | 説明 |
|--- |--- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | A/B テストでは、複数のバージョンの web サイトコンテンツを比較し、事前に指定したテスト期間中に、どのバージョンがコンバージョンを最も多く増やすことができるのかを確認できます。 |
| [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate]A/B テストの一種で、複数のエクスペリエンスの中から勝者を特定し、より多くのトラフィックをその勝者に自動的に再割り当てしてコンバージョンを増やし、その間もテストによる学習と実行を継続します。 |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | A/B テストの一種である自動ターゲットは、高度な機械学習を使用して、マーケターが定義した複数の高パフォーマンスのエクスペリエンスを特定し、個々の顧客のプロファイルと類似プロファイルを持つ以前の訪問者の行動に基づいて各訪問者に最適なエクスペリエンスを提供して、コンテンツをパーソナライズしコンバージョンを促進します。 |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] （MVT）はページ上の要素内のオファーの組み合わせを比較し、特定のオーディエンスに対して最も効果が高い組み合わせと、アクティビティの成功に最も効果が高い要素を特定します。 |
| [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] （XT）は、マーケターが定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] （AP）は、オファーやメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて各訪問者に様々なバリエーションをマッチさせ、コンテンツをパーソナライズしてコンバージョンを促進します。 |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | レコメンデーションは、サイト上の訪問者のアクティビティに応じて、web サイトの訪問者に製品を提案する方法を決定します。<P>例えば、リュックサックを購入した顧客に対して、ハイキングシューズやトレッキング用のステッキの購入を提案できます。特定の商品を購入した顧客が購入している他の商品を特定できるアルゴリズムを使用して、多くの場合同時に購入されている商品を示すレコメンデーションを作成できます。または、「これを閲覧したユーザー」アルゴリズムを使用して、訪問者が視聴しているビデオに類似したビデオをレコメンデーションすることで、メディアサイトにより多くの時間を費やすよう促すことができます。<P>**メモ**：内にレコメンデーションを含めることもできます [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]、および [!UICONTROL Experience Targeting] （XT） アクティビティ。 詳しくは、[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md) を参照してください。この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |

## アクティビティリストへのフィルターの適用 {#filters}

「」をクリックしてフィルターにアクセスする **[!UICONTROL Show Filters]** アイコンがリスト上部付近に表示されます。

![フィルターオプション](/help/main/c-activities/assets/show-filters-options.png)

メニューでは、次の属性でアクティビティをフィルタリングできます。 |属性|詳細| | — | — | |[!UICONTROL Type]|フィルター条件： [アクティビティタイプ](#types).| |[!UICONTROL Status]|アクティビティの状態でフィルターします。| |[!UICONTROL Reporting Source]|レポートソースでフィルタリングします。<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)：を使用するアクティビティの表示 [!UICONTROL Analytics for Target] レポートソースとしての（A4T）。</li><li>[[!DNL Target]](/help/main/c-reports/reports.md)：を使用するアクティビティの表示 [!DNL Target] をレポートソースとして使用します。</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)：を使用するアクティビティの表示 [!DNL Adobe Customer Analytics] をレポートソースとして使用します。</li></ul>| |[!UICONTROL Experience Composer]|アクティビティの作成中に Experience Composer が使用されたフィルター：<ul><li>[ビジュアル](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)：を使用して作成されたアクティビティを表示 [!UICONTROL Visual Experience Composer] （VEC）。</li><li>[フォームベース](/help/main/c-experiences/form-experience-composer.md)：を使用して作成されたアクティビティを表示 [!UICONTROL Form-Based Experience Composer].</li></ul>| |[!UICONTROL Metrics Type]|次の条件でフィルター [成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md) は、アクティビティの作成時に選択されました。<ul><li>コンバージョン</li><li>売上高</li><li>エンゲージメント</li></ul>| |[!UICONTROL Decisioning Method]|各アクティビティで使用される判定方法でフィルタリングします<ul><li>[サーバー側](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja)：サーバー側判定を使用するアクティビティを表示します。</li><li>[クライアントサイド](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)：クライアントサイド決定を使用するアクティビティを表示します。</li></ul>| |[!UICONTROL Activity Source]|各アクティビティの作成に使用されるアクティビティソースでフィルタリングします。<ul><li>[!DNL Adobe Target]</li><li>[ADOBE TARGET API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja)</li><li>[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)</li><li>[Adobe Mobile サービス](https://developer.adobe.com/client-sdks/documentation/)</li></ul>| |[!UICONTROL Property]|フィルター基準： [プロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) アクティビティが作成された。|

## クイックアクションの実行 {#quick-actions}

「」をクリックします **[!UICONTROL More actions]** 各アクティビティ名の横にあるアイコン（水平省略記号）をクリックすると、アクティビティに対してクイックアクションを実行できるメニューが開きます。

![クイックアクションオプション](/help/main/c-activities/assets/quick-actions.png)

使用できるアクションは次のとおりです（権限とアクティビティのステータスによって異なります）。

| アクション | 説明 |
| --- | --- |
| [!UICONTROL Edit] | アクティビティを変更します。どのアクティビティも編集できます。<P>アクティビティを編集する様々な方法について詳しくは、を参照してください。 [アクティビティを編集またはドラフトとして保存](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Deactivate] | ライブまたは日時指定のアクティビティを停止します。非アクティブ化されたアクティビティは、再アクティブ化またはアーカイブできます。<P>アクティビティを非アクティブ化またはアーカイブした後に再度アクティブ化した場合、非アクティブ化またはアーカイブ以前からアクティビティに含まれていた訪問者は、再アクティブ化の後も引き続きアクティビティに含まれます。非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL Activate] | 非アクティブなアクティビティまたはアクティブ化する準備が整ったアクティビティを開始します。 |
| [!UICONTROL Archive] | アクティビティをアーカイブに送信します。デフォルトでは、アーカイブされたアクティビティはに表示されなくなります [!UICONTROL Activities] リスト。 アクティビティリストのフィルターを変更して、アーカイブ済みアクティビティが含まれるようにして、表示されるようにします。アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。<P>アクティビティをディアクティベートまたはアーカイブしてから、後で再アクティベートすると、ある訪問者が、アクティベートを解除またはアーカイブする前にそのアクティビティにあった場合、その訪問者は再アクティベート後も引き続きそのアクティビティの対象となります。 非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL Copy] | アクティビティをコピーします。どのアクティビティもコピーできます。アクティビティをコピーすると、同じ名前に「Copy」と付いた、新しいアクティビティが作成されます。例えば、「ブラウザーオファー」というテストは、「ブラウザーオファー Copy」という名前でコピーされます。<P>ビジュアルオファーは、アクティビティと共にコピーされます。元のアクティビティに影響を与えることなく、コピー内で安全にオファーを編集できます。唯一の例外は、コンテンツ／アセットフォルダー内に保存したオファーおよび画像です。 |
| [!UICONTROL Delete] | ドラフトまたはアクティビティを削除します。<P>**メモ**：削除したアクティビティは復元できません。 このアクティビティが二度と必要にならないことが確実でない限り、を使用します [!UICONTROL Archive] アクション。 その後、必要に応じてアクティビティを再アクティブ化できます。 |

## 注意点

に関する次の詳細に注意してください [!UICONTROL Activity] リスト :

* アーカイブされたアクティビティと終了されたアクティビティがに表示されない [!UICONTROL Activities] リスト。 これらのアクティビティを表示するには、を使用してフィルタリングします [フィルターアイコン](#filters) リストの上部。
* アクティビティが最初にで作成された日時 [!DNL Target Classic] は非アクティブ化または削除されました。次から削除されました [!DNL Target Standard/Premium]. で最初に作成された削除されたアクティビティ [!DNL Target Classic] に送信されない [!UICONTROL Archive] フォルダー： [!DNL Target Standard/Premium]. アーカイブ済みフォルダー機能は、[!DNL Target Standard/Premium] で作成されたアクティビティにのみ適用されます。
* 以外のすべてのアクティビティタイプ [!UICONTROL Automated Personalization] （AP）、 [!UICONTROL Auto-Allocate]、および [!UICONTROL Auto-Target] 次のいずれかを使用するように選択できます [!DNL Target] または [!DNL Adobe Analytics] をデータソースとして使用します。 [!UICONTROL AP], [!UICONTROL Auto-Allocate]、および [!UICONTROL Auto-Target] *常に* use [!DNL Target] データ。
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

アクティビティ内のこれらの項目の数を増やすと、アクティビティの同期に要する時間も長くなります [!DNL Target].

V の追加の制限に対して[!UICONTROL isual Experience Composer] VEC、を参照 [Visual Experience Composer の制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## に読み込まれる属性 [!DNL Target] 以外で更新されたアクティビティの [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

アクティビティがで作成された場合 [!DNL Target] は次の外部から更新されました [!DNL Target] （例えば、API を使用して）次のアクティビティ属性がに読み込まれます。 [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority`、および `marketingCloudMetadata(remoteModifiedBy)`.

このインポートジョブは、アクティビティページが開かれたときに、最大 10 分の遅延で実行されます。

## トレーニングビデオ {#section_BE80D13A2E81460C885F902010E1AD87}

次のビデオでは、この記事で説明した概念について詳しく説明しています。

### アクティビティのタイプ（9:03）

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティのタイプについて説明しています。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

