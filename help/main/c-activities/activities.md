---
keywords: アクティビティリスト；アクティビティ；アクティビティタイプ；アクティビティの編集；アクティビティアクション；アクティビティ属性；アクティビティリストフィルター；アクティビティ制限；パーソナライズ；パーソナライゼーション
description: ' [!DNL Adobe Target]  アクティビティを使用して、特定のオーディエンス向けにコンテンツをパーソナライズし、ページデザインをテストします。'
title: ' [!DNL Target]でコンテンツをパーソナライズしてページデザインをテストするにはどうすればよいですか？'
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
TQID: https://experienceleague.adobe.com/q3-Z8r2eEWTISBkZBBJTJ8XarLi-lTa2qsqj961hhEQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2416
ht-degree: 28%

---

# アクティビティの概要

[!DNL Adobe Target]件のアクティビティを使用して、特定のオーディエンス向けにコンテンツをパーソナライズし、ページデザインをテストします。

例えば、夏用の婦人靴の情報をハイライトするランディングページと夏用の一般衣料をハイライトする別のランディングページの 2 つをテストするアクティビティを作成できます。 アクティビティは、これらのランディングページのそれぞれがいつ表示されるかを制御する条件と、どのページがより成功するかを決定する指標を決定します。 アクティビティは、特定の日付の間など、特定の条件が満たされた場合に開始および終了するように設定されます。 または、アクティビティが承認されたときに開始し、非アクティブになったときに終了するかを選択できます。

アクティビティを作成する際は、入念な計画が必要です。 アクティビティの開始時刻と期間を指定します。 その後、オファーの一覧を作成し、それぞれにターゲットとなるオーディエンスを割り当てます。

## アクティビティリスト {#section_DE8E2DB30D534962A931EF8BB48240F5}

[!UICONTROL Activities] リストは、[!DNL Target]を開いたときの既定のビューです。 このページからアクティビティを作成し、既存のアクティビティを管理できます。

[!DNL Target] UIの上部にある「[!UICONTROL Activities]」タブをクリックして、[!UICONTROL Activities] リストを表示することもできます。

[!UICONTROL Activities] リストには、[!DNL Target]実装内のすべてのアクティビティの概要が表示され、様々なアクションを実行できます。

次の表は、[!DNL Target] UIの[!UICONTROL Activities] リストの様々な要素を理解するのに役立ちます。

| 要素 | 説明 |
|--- |--- |
| [!UICONTROL Show filters] アイコン<P>![&#x200B; フィルターアイコンを表示](/help/main/assets/icons/Filter.svg) | リストの上部にある&#x200B;**[!UICONTROL Show Filters]** アイコンをクリックして、フィルターにアクセスすると、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、[!UICONTROL Decisioning Source]、[!UICONTROL Activity Source]、および[!UICONTROL Properties]でアクティビティをフィルタリングできます。<P>設定したフィルターは、現在のセッション全体で永続的です。<P>詳しくは、以下の[!UICONTROL Activities] リスト [&#128279;](#filters)にフィルターを適用するを参照してください。 |
| フィールドを検索 | アクティビティをすばやく検索するか、[!UICONTROL Activity] リストに表示されるアクティビティの数を減らします。 ドロップダウンを使用して、[!UICONTROL Activity Name]、[!UICONTROL URL]または[!UICONTROL ID]で検索できます。<P>設定した検索オプションは、現在のセッション全体で永続的です。 |
| [!UICONTROL Create Activity] | アクティビティを作成します。<P>様々なアクティビティタイプの作成について詳しくは、次を参照してください。 <ul><li>[[!UICONTROL A/B Test] アクティビティを作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[[!UICONTROL Auto-Allocate] アクティビティを作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[[!UICONTROL Auto-Target] アクティビティを作成](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[[!UICONTROL Automated Personalization] アクティビティを作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[[!UICONTROL Experience Targeting] アクティビティを作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[&#x200B; アクティビティの作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[[!UICONTROL Recommendations] アクティビティを作成](/help/main/c-recommendations/recommendations.md)</li></ul>各タイプについて詳しくは、以下の「[&#x200B; アクティビティタイプ &#x200B;](#types)」を参照してください。 |
| [!UICONTROL Create mobile preview link]<P>![その他のアクション メニュー](/help/main/assets/icons/MoreVertical.svg) | [&#x200B; モバイルプレビューリンク &#x200B;](https://experienceleague.adobe.com/ja/docs/target-dev/developer/mobile-apps/target-mobile-preview)を使用すると、モバイルアプリのアクティビティに対して簡単なエンドツーエンドのQAを実行できます。<P>**その他のオプション** アイコンをクリックし、**モバイルプレビューリンクの作成**&#x200B;を選択してから、モバイルでテストするアクティビティを選択します。 |
| テーブルをカスタマイズ<P>![&#x200B; テーブルのカスタマイズ アイコン &#x200B;](/help/main/assets/icons/ColumnSetting.svg) | ページの右上にある「**[!UICONTROL Customize Table]**」アイコンをクリックし、目的の列を選択または選択解除して、[!UICONTROL Activity] リストに表示される列を変更します。<P>変更はアカウントに適用され、[!DNL Target]からログアウトした後もアクティブのままになります。 |
| 一括操作のチェックボックス<P>![一括操作アイコン &#x200B;](/help/main/assets/icons/Rectangle.svg) | すべてのアクティビティまたは選択したアクティビティに対して一括操作を実行します。<P>使用可能なアクションのリスト（権限とアクティビティのステータスに応じて）については、以下の「[&#x200B; クイックアクションを実行](#quick-actions)」を参照してください。 |
| [!UICONTROL Type] | アクティビティタイプ。 [!UICONTROL Type]列を使用すると、各アクティビティをタイプ別にすばやく識別できます。 <ul><li>**AB-M**：手動[!UICONTROL A/B Test]</li><li>**AB-AA**: [!UICONTROL Auto-Allocate]</li><li>**AB-AT**: [!UICONTROL Auto-Target]</li><li>**AP**: [!UICONTROL Automated Personalization]</li><li>**XT**: [!UICONTROL Experience Targeting]</li><li>**MVT**: [!UICONTROL Multivariate Test]</li><li>**REC**: [!UICONTROL Recommendations]</li></ul>各タイプについて詳しくは、以下の「[&#x200B; アクティビティタイプ &#x200B;](#types)」を参照してください。 |
| [!UICONTROL Name] | アクティビティの名前。 各アクティビティ名の横にある&#x200B;**[!UICONTROL Quick Info]** アイコン（![&#x200B; クイック情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)）をクリックして、[!UICONTROL Activity ID]、[!UICONTROL Activity Objective]、[!UICONTROL Activity Location]、[!UICONTROL Goal]、および[!UICONTROL Status]などのポップアップカードでそのアクティビティに関する詳細情報を表示します。<P>各アクティビティ名の横にある&#x200B;**[!UICONTROL More actions]** アイコン（![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックして、アクティビティに対してクイックアクションを実行できるメニューを開きます。 次のアクションを使用できます（権限とアクティビティのステータスによって異なります）: [!UICONTROL Edit]、[!UICONTROL Activate]、[!UICONTROL Deactivate]、[!UICONTROL Copy]、[!UICONTROL Delete]、および[!UICONTROL Archive]。<P>各アクションについて詳しくは、以下の「[&#x200B; クイックアクションを実行する](#quick-actions)」を参照してください。<P>表ヘッダーをクリックして、リストをアルファベット順に昇順または降順で並べ替えます。 |
| [!UICONTROL Status] | アクティビティのステータスは、次のいずれかになります。<ul><li>**[!UICONTROL Live]**: アクティビティは現在実行中です。</li><li>**[!UICONTROL Scheduled]**：指定された開始日時にアクティビティをアクティブ化する準備ができました。</li><li>**[!UICONTROL Inactive]**: アクティビティが一時停止または非アクティブ化されました。</li><li>**[!UICONTROL Ended]**: アクティビティの指定された終了日時に達し、アクティビティが提供されなくなりました。</li><li>**[!UICONTROL Archived]**: アクティビティがアーカイブされました。 アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。</li></ul>**メモ**: API メソッドを使用して[!DNL Target] UI外のアクティビティをアクティブ化するなど、特定のアクションを実行する場合、更新が[!DNL Target] UIに反映されるまでに最大10分かかる場合があります。 |
| [!UICONTROL Last Updated] | アクティビティが最後に更新された日時とユーザー。<P>表ヘッダーをクリックして、リストを日付ごとに昇順または降順で並べ替えます。 |
| [!UICONTROL Priority] | アクティビティの優先度。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>[設定](/help/main/administrating-target/reporting.md)に応じて、[!DNL Target]のUIと[!UICONTROL Priority]のオプションは異なります。 [!UICONTROL Low]、[!UICONTROL Medium]または[!UICONTROL High]の従来の設定を使用するか、0 ～ 999の細かい優先度を有効にできます。<P>優先度設定について詳しくは、*目標と設定*&#x200B;の&#x200B;*アクティビティ設定*&#x200B;の[優先度](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)を参照してください。 |
| [!UICONTROL Property] | アクティビティの[プロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を表示します。<P>エンタープライズユーザー権限は[Target Premium](/help/main/c-intro/intro.md#premium)機能です。 |
| [!UICONTROL Estimated Lift in Revenue] | 100％のオーディエンスが勝者エクスペリエンスを閲覧した場合に予測される売上高の増加を表示します。<P>以下の数式を使用して計算します。<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>この数字は、短縮形の表記で小数点の前が 1 桁だけの場合、最大で小数第 1 位に丸められます。 例：$1.6M、$60K、$900、$8.5K、$205K<P>勝者となる十分なデータがない、またはコストの見積もりがないアクティビティの場合、このコラムには「---」と表示されます。<P>詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。 |
| [!UICONTROL Source] | アクティビティが作成された場所を表示します：[!DNL Adobe Target]、[Adobe Target API](https://experienceleague.adobe.com/ja/docs/target-dev/developer/overview)、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja)、[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)、または[Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/)。 |
| [!UICONTROL Author] | アクティビティを作成したユーザーの名前。 |
| [!UICONTROL Decisioning Method] | 各アクティビティで使用される決定方法：[&#x200B; サーバーサイド &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja)または[&#x200B; クライアントサイド &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html?lang=ja)。 |

<!--|[!UICONTROL Location]|The URL for the activity identifies where the activity is displayed. This column helps you quickly identify an activity and determine whether a particular page already has an activity running on it.<P>If an activity runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity.<P>You can search based on the URL. Use the drop-down list next to the search box and select [!UICONTROL URL].|-->

## アクティビティのタイプ {#types}

[!DNL Target]には、複数のアクティビティ タイプが含まれています。 次の表は、各アクティビティタイプの概要と学習に役立つリンクを示しています。 目的に最適なアクティビティタイプをより適切に選択するには、[Adobe Target アクティビティガイド &#x200B;](/help/main/c-activities/target-activities-guide.md)を使用してください。

| アクティビティタイプ | 説明 |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | A/B テストでは、ふたつ以上のバージョンのweb サイトのコンテンツを比較し、事前に指定したテスト期間中に、どのバージョンがコンバージョンを最も向上させるかを確認します。 |
| [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | A/B テストの一種である[!UICONTROL Auto-Allocate]は、2つ以上のエクスペリエンスの中から勝者を特定し、テストの実行と学習を続ける間に、勝者により多くのトラフィックを自動的に再割り当てしてコンバージョンを増加させます。 |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | A/B テストの一種であるAuto-Targetは、高度なマシンラーニングを使用して、パフォーマンスの高いマーケター定義のエクスペリエンスを複数特定し、個々の顧客のプロファイルと類似のプロファイルを持つ以前の訪問者の行動に基づいて各訪問者に最もカスタマイズされたエクスペリエンスを提供し、コンテンツをパーソナライズし、コンバージョンを促進します。 |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] （MVT）は、ページ上の要素のオファーの組み合わせを比較して、特定のオーディエンスに対して最も効果的な組み合わせを判断し、アクティビティの成功に最も影響を与える要素を特定します。 |
| [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] （XT）は、マーケターが定義した一連のルールと条件に基づいて、特定のオーディエンスにコンテンツを配信します。 |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] （AP）は、オファーまたはメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて各訪問者に異なるバリエーションを一致させ、コンテンツをパーソナライズし、コンバージョンを促進します。 |
| [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | レコメンデーションは、web サイトでの訪問者のアクティビティに応じて、web サイト訪問者に商品をどのように提案するかを決定します。<P>例えば、リュックサックを購入した顧客に対して、ハイキングシューズやトレッキング用のステッキの購入を提案できます。 特定の商品を購入した顧客が購入している他の商品を特定できるアルゴリズムを使用して、多くの場合同時に購入されている商品を示すレコメンデーションを作成できます。 あるいは、「これを見た人がその人を見た」アルゴリズムを使用して、視聴中の動画と類似する動画をレコメンドすることで、訪問者にメディアサイトでの時間を増やすよう促すことができます。<P>**メモ**: [!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]および[!UICONTROL Experience Targeting] （XT）アクティビティ内に推奨事項を含めることもできます。 詳しくは、[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)をご覧ください。 この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |

## アクティビティ リストへのフィルターの適用 {#filters}

リストの上部にある&#x200B;**[!UICONTROL Show Filters]** アイコン（![&#x200B; フィルターを表示アイコン &#x200B;](/help/main/assets/icons/Filter.svg)）をクリックして、フィルターにアクセスします。

メニューでは、次の属性でアクティビティをフィルタリングできます。

| 属性 | 詳細 |
| --- | --- |
| [!UICONTROL Type] | [&#x200B; アクティビティの種類](#types)でフィルタリングします。 |
| [!UICONTROL Status] | アクティビティステータスでフィルタリング。<ul><li>**[!UICONTROL Live]**: アクティビティは現在実行中です。</li><li>**[!UICONTROL Scheduled]**：指定された開始日時にアクティビティをアクティブ化する準備ができました。</li><li>**[!UICONTROL Inactive]**: アクティビティが一時停止または非アクティブ化されました。</li><li>**[!UICONTROL Ended]**: アクティビティの指定された終了日時に達し、アクティビティが提供されなくなりました。</li><li>**[!UICONTROL Archived]**: アクティビティがアーカイブされました。 アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。</li></ul>非推奨の[!UICONTROL Save as Draft]および[!UICONTROL Syncing] ステータスについて詳しくは、この表の下のメモを参照してください。 |
| [!UICONTROL Reporting Source] | レポートソースでフィルタリング。<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md): [!UICONTROL Analytics for Target] （A4T）をレポートソースとして使用するアクティビティを表示します。</li><li>[[!DNL Target]](/help/main/c-reports/reports.md): [!DNL Target]をレポートソースとして使用するアクティビティを表示します。</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md): [!DNL Adobe Customer Analytics]をレポートソースとして使用するアクティビティを表示します。</li></ul> |
| [!UICONTROL Experience Composer] | アクティビティの作成中に使用されたエクスペリエンスコンポーザーをフィルタリングします。<ul><li>[Visual](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): [!UICONTROL Visual Experience Composer] （VEC）を使用して作成されたアクティビティを表示します。</li><li>[&#x200B; フォームベース &#x200B;](/help/main/c-experiences/form-experience-composer.md): [!UICONTROL Form-Based Experience Composer]を使用して作成されたアクティビティを表示します。</li></ul> |
| [!UICONTROL Metrics Type] | アクティビティの作成中に[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md)が選択されたフィルター。<ul><li>[!UICONTROL Conversion]</li><li>[!UICONTROL Revenue]</li><li>[!UICONTROL Engagement]</li><li>[!UICONTROL Use an Analytics metric]</lI></ul> |
| [!UICONTROL Decisioning Method] | 各アクティビティで使用される決定方法でフィルタリングします。<ul><li>[&#x200B; サーバーサイド &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja): サーバーサイド決定を使用するアクティビティを表示します。</li><li>[&#x200B; クライアントサイド &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html?lang=ja): クライアントサイド決定を使用するアクティビティを表示します。</li></ul> |
| [!UICONTROL Activity Source] | 各アクティビティの作成に使用するアクティビティソースでフィルタリングします。<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Property] | アクティビティが作成された[&#x200B; プロパティ &#x200B;](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)でフィルタリングします。 |


>[!NOTE]
>
>**更新されたUIのアクティビティ状態に関する更新**: ユーザーインターフェイスの最新の更新により、[!UICONTROL Save as Draft]と[!UICONTROL Syncing]の状態は使用できなくなります。 これは、すべてのアクティビティの作成と編集が、GraphQL レイヤーを使用してバックエンド [!DNL Target] デリバリーシステム内で直接行われるようになり、より合理化された効率的なプロセスが実現されたためです。
>
>以前は、アクティビティは最初[!DNL Target] フロントエンドに保存され、次にバックエンド [!DNL Target]配信システムに同期されていました。このシステムでは、中間状態が必要でした。 これはもはや事実ではないので、これらの状態は削除されました。
>
>[!DNL Adobe]様は、一部のお客様が[!UICONTROL Save as Draft]機能に関心を示したことを理解しています。 このフィードバックは評価しますが、この機能は現在サポートされていません。

## クイックアクションの実行 {#quick-actions}

各アクティビティ名の横にある&#x200B;**[!UICONTROL More actions]** アイコン（![詳細アクションメニュー](/help/main/assets/icons/MoreVertical.svg)）をクリックして、アクティビティに対してクイックアクションを実行できるメニューを開きます。

次のアクションを使用できます（権限とアクティビティステータスによって異なります）。

| アクション | 説明 |
| --- | --- |
| [!UICONTROL Edit] | アクティビティを変更します。 どのアクティビティも編集できます。<P>アクティビティを編集する様々な方法について詳しくは、[&#x200B; アクティビティの編集またはドラフトとして保存](/help/main/c-activities/edit-activity.md)を参照してください。 |
| [!UICONTROL Deactivate] | ライブまたは日時指定のアクティビティを停止します。 非アクティブ化されたアクティビティは、再アクティブ化またはアーカイブできます。<P>アクティビティを非アクティブ化またはアーカイブした後に再度アクティブ化した場合、非アクティブ化またはアーカイブ以前からアクティビティに含まれていた訪問者は、再アクティブ化の後も引き続きアクティビティに含まれます。 非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL Activate] | 非アクティブなアクティビティまたはアクティブ化する準備ができているアクティビティを開始します。 |
| [!UICONTROL Archive] | アクティビティをアーカイブに送信します。 既定では、アーカイブされたアクティビティは[!UICONTROL Activities] リストに表示されなくなります。 [!UICONTROL Activities] リストのフィルターを変更して、アーカイブされたアクティビティを含めて表示します。 アーカイブ済みアクティビティをアクティブ化して、再度使用することができます。<P>アクティビティを非アクティブ化またはアーカイブし、その後に再アクティブ化した場合、そのアクティビティが非アクティブ化またはアーカイブされる前に訪問者がそのアクティビティ内にいた場合、再アクティブ化後も訪問者はそのアクティビティの一部であり続けます。 非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| [!UICONTROL Copy] | アクティビティをコピーします。 どのアクティビティもコピーできます。 アクティビティをコピーすると、同じ名前に「Copy」と付いた、新しいアクティビティが作成されます。 例えば、「ブラウザーオファー」というテストは、「ブラウザーオファー Copy」という名前でコピーされます。<P>ビジュアルオファーは、アクティビティと共にコピーされます。 元のアクティビティに影響を与えることなく、コピー内で安全にオファーを編集できます。 唯一の例外は、コンテンツ／アセットフォルダー内に保存したオファーおよび画像です。 |
| [!UICONTROL Delete] | ドラフトまたはアクティビティを削除します。<P>**メモ**：削除されたアクティビティを復元できません。 このアクティビティが二度と必要でないことを確認しない限り、[!UICONTROL Archive] アクションを使用します。 その後、必要に応じてアクティビティを再アクティブ化できます。 |

## 注意点

[!UICONTROL Activity] リストに関する次の詳細に注意してください。

* [!UICONTROL Archived]と[!UICONTROL Ended]のアクティビティが[!UICONTROL Activities] リストに表示されません。 これらのアクティビティを表示するには、リストの上部にある[&#x200B; フィルターアイコン &#x200B;](#filters) （![&#x200B; フィルターアイコン &#x200B;](/help/main/assets/icons/Filter.svg)）を使用してアクティビティをフィルタリングします。
* 最初に[!DNL Target Classic]で作成されたアクティビティが非アクティブ化または削除されると、[!DNL Target Standard/Premium]から削除されます。 最初に[!DNL Target Classic]で作成された削除済みアクティビティは、[!DNL Target Standard/Premium]の[!UICONTROL Archive] フォルダーには送信されません。 アーカイブ済みフォルダー機能は、[!DNL Target Standard/Premium] で作成されたアクティビティにのみ適用されます。
* [!UICONTROL Automated Personalization] （AP）、[!UICONTROL Auto-Allocate]および[!UICONTROL Auto-Target]以外のすべてのアクティビティタイプでは、[!DNL Target]または[!DNL Adobe Analytics]のいずれかをデータソースとして使用できます。 [!UICONTROL Automated Personalization]、[!UICONTROL Auto-Allocate]および[!UICONTROL Auto-Target] *常に*&#x200B;は[!DNL Target] データを使用します。
* アクティビティは複数のチャネルで利用可能です。

   * Web およびモバイルサイト
   * インターネットに接続された画面およびデバイス（キオスクや ATM を含む）
   * メールや他の購買チャネルまたはパートナーサイト
   * モバイルアプリ
   * タグ付きコンテンツを配信できる他の場所すべて

## 制限事項 {#section_049D4684403A4E07B998067EB8E9BE56}

各[!DNL Target] アクティビティには、次のコンテンツ制限があります。

| 項目 | 制限 |
|--- |--- |
| 一意のセレクター数 | 300異なるエクスペリエンスでセレクターを繰り返すと、1回カウントされます。 ただし、同じエクスペリエンスで繰り返される場合は、再度カウントされます。 |
| 各エクスペリエンスのオファー | 350 |
| 指標のクリック追跡セレクター数 | 50 |
| 指標の mbox 数 | 50 |
| オーディエンスと場所 | 50のオーディエンスと場所（mbox）の組み合わせは50を超えてはなりません。 |

これらの制限を超えると、アクティビティを保存できません。

アクティビティ内のこれらの項目の数を増やすと、アクティビティを[!DNL Target]間で同期するのにかかる時間も長くなります。

[!UICONTROL Visual Experience Composer] （VEC）のその他の制限については、[Visual Experience Composerの制限](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)を参照してください。

## [!DNL Target]以外で更新されたアクティビティの属性が[!DNL Target]にインポートされました {#section_802B0D174E6A44E1A96F404CA81AAE44}

[!DNL Target]で作成されたアクティビティが[!DNL Target]以外から（例えばAPI経由で）更新された場合、次のアクティビティ属性が[!DNL Target]に読み込まれます：`thirdpartyId`、`startDate`、`endDate`、`status`、`priority`、および`marketingCloudMetadata(remoteModifiedBy)`。

この読み込みジョブは、[!UICONTROL Activities] リストを開いたときに実行されます。最大遅延は10分です。

