---
keywords: アクティビティリスト；アクティビティ；アクティビティ；アクティビティタイプ；アクティビティの編集；アクティビティ操作；アクティビティ属性；アクティビティリストフィルター；アクティビティ制限；パーソナライズ；パーソナライズ
description: Adobe [!DNL Target] を使用すると、特定のオーディエンスに対するコンテンツをパーソナライズし、ページデザインをテストできます。
title: Target を使用してコンテンツをパーソナライズし、ページデザインをテストする方法を教えてください。
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '2072'
ht-degree: 92%

---

# アクティビティ

[!DNL Adobe Target] のアクティビティを使用すると、特定のオーディエンス対してコンテンツをパーソナライズし、ページのデザインをテストできます。

例えば、夏用の婦人靴の情報をハイライトするランディングページと夏用の一般衣料をハイライトする別のランディングページの 2 つをテストするアクティビティを作成できます。アクティビティによって、これらの各ランディングページをいつ表示するかを制御する条件や、成功度の高いページを判断する指標を定義できます。アクティビティは、特定の条件が満たされたときに開始および終了するよう設定できます。例えば、具体的な日付の範囲による期間の設定や、アクティビティが承認されたときに開始し非アクティブになったときに終了する設定ができます。

アクティビティを作成する際は、入念な計画が必要です。まず、アクティビティを開始するタイミングと実行期間を決定します。その後、オファーの一覧を作成し、それぞれにターゲットとなるオーディエンスを割り当てます。

## アクティビティのタイプ

Target には、複数のアクティビティタイプがあります。次の表は、各アクティビティタイプの概要と学習に役立つリンクを示しています。目的に合わせて最適なアクティビティタイプを選択できるように、[Adobe Target Activities ガイド](/help/main/c-activities/target-activities-guide.md)も作成しました。

| アクティビティタイプ | 説明 |
|--- |--- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | A/B テストでは、事前に設定したテスト期間中に複数のバージョンの Web サイトコンテンツを比較し、どのバージョンがコンバージョンを最も多く増やすことができるのかを見極めます。<br>**メモ：**[ A/B テストアクティビティ内に レコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)を組み込めるようになりました。この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |
| [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 自動配分では、2 つ以上のエクスペリエンスの中から勝者を特定したうえで、自動的にその勝者に配分するトラフィックを増やすことでコンバージョンを促進します。その間もテストによる学習は続けられます。<br>**メモ：**[エクスペリエンスターゲット設定アクティビティ内にレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)を組み込めるようになりました。この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<br>![Target Premium](/help/main/assets/premium.png) | 自動ターゲットでは、高度な機械学習を利用して、マーケティング担当者が定義した高パフォーマンスのエクスペリエンスを複数特定したうえで、個々の顧客プロファイルや同様のプロファイルを持つ過去の訪問者の行動を基にして、各訪問者に詳細にカスタマイズしたエクスペリエンスを配信しながら、コンテンツをパーソナライズしてコンバージョンを促進していきます。<br>**メモ：**[自動ターゲットアクティビティ内にレコメンデーションを](/help/main/c-recommendations/recommendations-as-an-offer.md)含めることができるようになりました。この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |
| [Analytics データの使用](/help/main/c-activities/t-test-ab/t-test-create-ab/create-a4t.md)（A4T） | レポートソースとして [!DNL Adobe Analytics] を使用するようアクティビティを設定することができます。このタイプのアクティビティでは、[!DNL Adobe Experience Cloud] アカウントを [!DNL Analytics] と [!DNL Target] の両方にリンクする必要があります。 |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Multivariate Testing（MVT）では、ページ上の要素内のオファーの組み合わせを比較し、特定のオーディエンスに対して最も効果が高い組み合わせと、アクティビティの成功に最も効果が高い要素を特定します。 |
| [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) | エクスペリエンスのターゲット設定（XT）では、マーケティング担当者が定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。<br>**メモ：**[エクスペリエンスターゲット設定アクティビティ内にレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)を組み込めるようになりました。この機能を使用するには、[Target Premium ライセンス](/help/main/c-intro/intro.md#premium)が必要です。 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>![（Target Premium）](/help/main/assets/premium.png) | Automated Personalization（AP）では、オファーやメッセージを組み合わせて、高度な機械学習を使用することで、個々の顧客プロファイルに合わせて各訪問者に様々なバリエーションを表示しながら、コンテンツをパーソナライズしてコンバージョンを促進していきます。 |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<br>![（Target Premium）](/help/main/assets/premium.png) | レコメンデーションでは、Web サイトでのユーザーのアクティビティを基にして、そのユーザーに商品を提案する方法を決定します。<br>例えば、リュックサックを購入した顧客に対して、ハイキングシューズやトレッキング用のステッキの購入を提案できます。特定の商品を購入した顧客が購入している他の商品を特定できるアルゴリズムを使用して、多くの場合同時に購入されている商品を示すレコメンデーションを作成できます。また、特定のビデオを視聴した訪問者が視聴している他のビデオを特定できるアルゴリズムを使用して、訪問者が視聴したビデオと似たビデオを提案することで、訪問者がメディアサイト上でより多くの時間滞在するように誘導することもできます。<br>**メモ：** A/B テスト（自動配分と自動ターゲットを含む）アクティビティおよびエクスペリエンスターゲット設定（XT）アクティビティ内にレコメンデーションを組み込めるようになりました。[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)を参照してください。 |

## アクティビティリスト {#section_DE8E2DB30D534962A931EF8BB48240F5}

[!UICONTROL アクティビティ]リストは、[!DNL Target] を開いたときのデフォルトのビューです。このページから新しいアクティビティを作成したり、既存のアクティビティを管理したりできます。

[!DNL Target] UI の上部にある「[!UICONTROL アクティビティ]」タブをクリックして[!UICONTROL アクティビティ]リストを表示することもできます。

![アクティビティリスト](/help/main/c-activities/assets/activities-list.png)

アクティビティリストには、すべてのアクティビティの概要が表示されます。

| 要素 | 説明 |
|--- |--- |
| タイプ | A/B または MVT などのアクティビティタイプ。 |
| 名前 | アクティビティの名前。 |
| URL | URL は、名前の下に薄い色のテキストで表示されます。<br>アクティビティの URL は、アクティビティが表示される場所を示します。これにより、アクティビティをすばやく特定して、特定のページで既にテストが実行されているかどうかを判断できます。<br>テストが複数の URL で実行されている場合は、他に使用されている URL の数を示すリンクが表示されます。該当するアクティビティのすべての URL のリストを表示するには、このリンクをクリックします。<br>URL に基づいて検索できます。検索ボックスの横にあるドロップダウンリストを使用し、「[!UICONTROL URL を検索]」を選択します。 |
| ステータス | アクティビティのステータスは、次のいずれかになります。<ul><li>**ライブ**：アクティビティは現在実行中です。</li><li>**ドラフト**： アクティビティの設定は開始していますが、アクティビティはまだ実行できる状態ではありません。</li><li>**スケジュール済み**：アクティビティは、指定された開始日時になるとアクティブ化されます。</li><li>**非アクティブ**：アクティビティは一時停止しているか、非アクティブになっています。</li><li>**同期中**： アクティビティは保存済みで、Target 配信ネットワークと同期中です。</li><li>**終了**： アクティビティの指定終了日時になり、アクティビティが提供されなくなりました。</li><li>**アーカイブ済み**： アクティビティはアーカイブされています。アーカイブ済みアクティビティをアクティブ化して、もう一度使用することができます。</li></ul>**メモ意**：API メソッドを使用した UI 外でのアクティビティのアクティブ化など、特定のアクションを実行する場合、更新が UI に反映されるまで最大 10 分かかる場合があります。 |
| ソース | アクティビティが作成された場所を示します。<ul><li>Adobe Target</li><li>Adobe Target Classic</li><li>Adobe Experience Manager（AEM）</li><li>Adobe Mobile Services（AMS）</li></ul> |
| オンデバイス判定の対象 | オンデバイス判定の対象となるアクティビティを作成すると、オンデバイス判定の対象となるラベルがアクティビティの概要ページに表示されます。<br>このラベルは、アクティビティが常にオンデバイス判定経由で配信されるとは限りません。 at.js 2.5.0 以降がオンデバイス判定を使用するように設定されている場合にのみ、このアクティビティはデバイス上で実行されます。 at.js 2.5.0 以降がオンデバイスを使用するように設定されていない場合、このアクティビティは、at.js からおこなわれるサーバー呼び出しを介して引き続き配信されます。<br>詳しくは、 [オンデバイス判定](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/on-device-decisioning/). |
| プロパティ | アクティビティの[プロパティ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を表示します。 |
| 収益の推定上昇率 | 100％のオーディエンスが勝者エクスペリエンスを閲覧した場合に予測される売上高の増加を表示します。<br>計算式は次のとおりです。<br>`(<winning experience> - <control experience>)*<total number of visitors>`<br>短縮形の表記で小数点の前が 1 桁だけの場合、この番号は少数第 2 位までで四捨五入されます。例： $1.6M、$60K、$900、$8.5K、$205K<br>勝者となる十分なデータがない、またはコストの見積もりがないアクティビティの場合、この列には「---」と表示されます。<br>詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。 |
| 最終更新日 | アクティビティが最後に更新された日付と更新者の名前。 |

使用できるアクションを表示するには、アクティビティにマウスポインターを置きます。

![アクティビティリストにマウスポインターを置いたときに使用可能なアクション](/help/main/c-activities/assets/activities_list_hover.png)

（権限に応じて）次のアクションが使用可能です。

| アクション | 説明 |
| --- | --- |
| 編集 | アクティビティを変更します。どのアクティビティも編集できます。<br>アクティビティを編集する様々な方法について詳しくは、「[アクティビティの編集またはドラフトとして保存](/help/main/c-activities/edit-activity.md)」を参照してください。 |
| 非アクティブ化 | ライブまたは日時指定のアクティビティを停止します。非アクティブ化されたキャンペーンは再アクティブ化またはアーカイブできます。<br>アクティビティを非アクティブ化またはアーカイブした後に再アクティブ化した場合、再アクティブ化またはアーカイブ以前からアクティビティに含まれていた訪問者は、再アクティブ化の後も引き続きアクティビティに含まれます。非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| アクティブ化 | 非アクティブまたは準備完了（Ready）のアクティビティを開始します。 |
| アーカイブ | アクティビティをアーカイブに送信します。デフォルトでは、アーカイブ済みアクティビティは、アクティビティリストに表示されません。アクティビティリストのフィルターを変更して、アーカイブ済みアクティビティが含まれるようにして、表示されるようにします。アーカイブ済みアクティビティをアクティブ化して、もう一度使用することができます。<br>アクティビティを非アクティブ化またはアーカイブした後に再度アクティブ化した場合、非アクティブ化またはアーカイブ以前からアクティビティに含まれていた訪問者は、再アクティブ化の後も引き続きアクティビティに含まれます。非アクティブ化またはアーカイブと再アクティブ化までの間に記録されるコンバージョン指標は、アクティビティによるものとはされません。 |
| コピー | アクティビティをコピーします。どのアクティビティもコピーできます。アクティビティをコピーすると、同じ名前に「Copy」と付いた、新しいアクティビティが作成されます。例えば、「ブラウザーオファー」というテストは、「ブラウザーオファー Copy」という名前でコピーされます。<br>ビジュアルオファーは、アクティビティと共にコピーされます。元のアクティビティに影響を与えることなく、コピー内で安全にオファーを編集できます。唯一の例外は、コンテンツ／アセットフォルダー内に保存したオファーおよび画像です。 |
| 削除 | ドラフトまたはアクティビティを削除します。<BR>**注意**：削除されたアクティビティを元に戻すことはできません。このアクティビティが再び必要になることがないと確信できない限り、[!UICONTROL アーカイブ]操作を使用します。その後、必要に応じてアクティビティを再アクティブ化できます。 |

アクティビティリストについては、次の点に注意してください。

* アーカイブ済みおよび終了したアクティビティは、[!UICONTROL アクティビティ]リストには表示されません。これらのアクティビティを表示するには、左側のレールのアドバンスフィルター設定を使用してフィルタリングします。
* もともと [!DNL Target Classic] で作成されたアクティビティを非アクティブ化または削除すると、そのアクティビティはすぐに [!DNL Target Standard/Premium] から削除されます。削除されると、もともと [!DNL Target Classic] で作成されたアクティビティは、[!DNL Target Standard/Premium] の [!UICONTROL アーカイブ]フォルダーに送信されません。アーカイブ済みフォルダー機能は、[!DNL Target Standard/Premium] で作成されたアクティビティにのみ適用されます。
* [!UICONTROL 自動パーソナライゼーション]（AP）、[!UICONTROL 自動配分]、[!UICONTROL 自動ターゲット]以外のすべてのタイプのアクティビティでは、データソースとして[!DNL Target]または[!DNL Adobe Analytics]のいずれかを使用できます。[!UICONTROL AP]、[!UICONTROL 自動配分]、および [!UICONTROL 自動ターゲット]では、*常に* [!DNL Target] データが使用されます。
* アクティビティは複数のチャネルで利用可能です。

   * Web およびモバイルサイト
   * インターネットに接続された画面およびデバイス（キオスクや ATM を含む）
   * メールや他の購買チャネルまたはパートナーサイト
   * モバイルアプリ
   * タグ付きコンテンツを配信できる他の場所すべて

## アクティビティリストの並べ替えとフィルタリング {#section_41DAD479FFF740E2BB67BF4825955670}

デフォルトのリストは、アクティビティが最後に変更された日付で並べ替えられ、最新のものから順に表示されています。ただし、リストをカスタマイズして確認したいアクティビティを表示するのに役立つ、いくつかのフィルタリングオプションがあります。

### 検索 {#search-heading}

検索フィールドを使用して、検索条件に一致するアクティビティを検索します。

![アクティビティ検索](/help/main/c-activities/assets/activities_search_new.png)

検索フィールドには、検索を絞り込むのに役立つドロップダウンメニューが含まれています。次の検索フィルターから 1 つ指定します。[!UICONTROL アクティビティ名] と [!UICONTROL URL]。

### アクティビティリストフィルター

リストフィルターを選択することで、どのアクティビティをアクティビティリストに表示するかを指定できます。

![タイプによるアクティビティのフィルタリング](/help/main/c-activities/assets/activities_filters_new.png)

以下のオプションでフィルターできます。各カテゴリでは、何も選択されていない場合、デフォルトは「すべて」です。

| フィルターカテゴリ | フィルター |
|--- |--- |
| タイプ | A/B テスト：[手動](/help/main/c-activities/t-test-ab/test-ab.md)、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。<br>[自動パーソナライゼーション](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>[エクスペリエンスターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md)<br>[多変量分析テストレコメンデーション](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)<br>[](/help/main/c-recommendations/recommendations.md) |
| ステータス | ライブ<br>ドラフト<br>スケジュール済み<br>非アクティブ<br>同期中<br>終了<br>アーカイブ済み |
| オンデバイス判定の対象 | はい<br>いいえ |
| レポートソース | Target<br>Analytics |
| Experience Composer | 視覚的<br>フォームベース |
| 指標のタイプ | コンバージョン<br>売上高<br>エンゲージメント |
| アクティビティソース | Adobe Target<br>Adobe Target Classic<br>Adobe Experience Manager<br>Adobe Mobile Services |

### アクティビティ属性で並べ替え

次の見出しをクリックして、選択した見出しに応じてアクティビティをリストする順番を昇順と降順で切り替えます。

* タイプ
* 名前

![アクティビティリストの昇順](/help/main/c-activities/assets/activities_list_ascending.png)

![今日のヒントを無効にする](/help/main/c-activities/assets/tip-disable-new.png)

## 制限事項 {#section_049D4684403A4E07B998067EB8E9BE56}

各 Target アクティビティには、次のコンテンツの制限があります。

| 項目 | 制限 |
|--- |--- |
| 一意のセレクター数 | 300。セレクターが異なるエクスペリエンスで繰り返される場合、1 回とカウントされます。ただし、同じエクスペリエンスで繰り返される場合は、再度カウントされます。 |
| 各エクスペリエンスのオファー | 350 |
| 指標のクリック追跡セレクター数 | 50 |
| 指標の mbox 数 | 50 |
| オーディエンスと場所 | 50。オーディエンスと場所（mbox）の組み合わせは、50 個以下にする必要があります。 |

これらの制限を超えると、アクティビティを保存できません。

アクティビティでこれらの項目の数が増えると、Target のアクティビティを同期するのにかかる時間も長くなります。

Visual Experience Composer の追加の制限事項については、[Visual Experience Composer の制限事項](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)の説明を参照してください。

## に読み込まれた属性 [!DNL Target] （以外で更新されたアクティビティの場合） [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

[!DNL Target] で作成されたアクティビティが [!DNL Target] 以外（Adobe I/O など）で更新されると、次のアクティビティ属性が [!DNL Target] に再び読み込まれます。

`thirdpartyId`

`startDate`

`endDate`

`status`

`priority`

`marketingCloudMetadata(remoteModifiedBy)`

このインポートジョブは、アクティビティページが開かれたときに実行されます（最大遅延時間は 10 分）。（KB-1526）

## トレーニングビデオ {#section_BE80D13A2E81460C885F902010E1AD87}

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### アクティビティタイプ（9:03）![概要バッジ](/help/main/assets/overview.png)

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティタイプについて説明しています。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプに適用される 3 ステップのガイドによるワークフローについての説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

