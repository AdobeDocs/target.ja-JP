---
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
description: このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合のレポートの表示に関するよくある質問に対する回答が含まれています。
title: レポートの表示 - A4T FAQ
feature: null
topic: Standard
uuid: d51991f7-cdda-4a59-b64c-7ef1c3f8380d
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1992'
ht-degree: 63%

---


# レポートの表示 - A4T FAQ{#view-reports-a-t-faq}

This topic contains answers to questions that are frequently asked about viewing reports when using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## Can I view my Target activity data in Analysis Workspace? {#workspace}

を使用して、 [!DNL Analysis Workspace][!DNL Target] アクティビティとエクスペリエンスを分析できます。 ターゲット [分析パネル](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) では、最大3つの成功指標に対して上昇率と信頼性を確認できます。 テーブルやビジュアライゼーションを使用して、より深く掘り下げることもできます。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## Analysis Workspaceでセグメントを適用できる場所 {#segmentation}

セグメントは、最も一般的に、セグメントドロップゾーンのパネルの上部に適用されます。 セグメントは、パネル内のすべてのテーブルおよびビジュアライゼーションに適用されます。 この手法は、テストがユーザーのサブセットに与える影響（例えば、このテストが英国の人々に対してどのように機能したか）を確認するのに最も役立ちます。

## 特定のターゲットアクティビティに対してヒットセグメントを適用すると、無関係なエクスペリエンスが返されるのはなぜですか。 {#activity-segmentation}

[!DNL Target] に送信される [!DNL Analytics] 変数には、デフォルトで 90 日間の有効期限があります。(注意：この有効期限は、必要に応じてカスタマーケアが調整できます)。 訪問者は、この有効期限枠を通してサイトをナビゲートする際、多くの [!DNL Target] アクティビティの一部となり、すべてディメンションに収集されます。

その結果、あるアクティビティがヒットに存在するようにセグメント化すると、そのアクティビティに含まれるすべてのエクスペリエンスと ** 、そのヒットに永続的なその他のエクスペリエンスがすべて取得されます。

## 標準化指標（カウント手法）として訪問者、訪問またはアクティビティのインプレッションを使用する必要がありますか。 {#metrics}

A4Tレポートで指標を標準化する方法には、いくつかの方法があります。 この指標は、カウント手法とも呼ばれ、上昇率計算の分母になります。 また、信頼性計算が適用される前のデータの集計方法に影響します。

* ***実訪問者数***&#x200B;は、あるユーザーが初めてアクティビティの対象になったときに 1 回増加します。
* ***訪問回数***&#x200B;は、あるユーザー（実訪問者）がアクティビティに入るとセッションのたびに 1 回増加します（その後の訪問でそのアクティビティが表示されない場合も含む）。
* ***アクティビティのインプレッション***&#x200B;は、アクティビティコンテンツが配信されるたびに増加します(で測定 [!DNL Target])。

アクティビティが含まれているページを訪問者が閲覧すると、該当するアクティビティの名前を含む変数がその訪問者に対して設定されます。各カウント方法を比較する方法については、以下の詳細なシナリオを参照してください。

次の点に留意してください。

* All of the above metrics trigger when a user qualifies for an activity and content is returned from [!DNL [!DNL Target]]. したがって、必ずしもそのユーザーがオファーを見たかどうかはわかりません。アクティビティエクスペリエンスがスクロールしないと見えない場所にある場合、[!DNL Target] によってオファーが配信されていても、ユーザーがページを下にスクロールしなければ、オファーは見られていないことになります。
* （[!UICONTROL  によって測定される）]アクティビティのインプレッション[!DNL Target]と（[!UICONTROL  によって測定される）]インスタンス[!DNL Analytics]は同じ値になります。ただし、同じアクティビティで複数の mbox 呼び出しが同じページに対しておこなわれた場合を例外です。この場合、[!UICONTROL アクティビティのインプレッション]は複数回カウントされますが、[!UICONTROL インスタンス]は 1 回しかカウントされません。

## Analysis Workspaceで「アクティビティインプレッション」と「アクティビティコンバージョン」がReports &amp; Analyticsよりも高いのはなぜですか。 {#sametouch}

[!DNL Reports & Analytics] 「アクティビティのインプレッション数」と「アクティビティのコンバージョン」に同じタッチのアトリビューションモデルを適用します。これに対して、生の指標が [!DNL Analysis Workspace][!DNL Target] 表示されます。これは、ディメンションの持続性によって水増しされる可能性があります。

To evaluate accurate [!UICONTROL Activity Impressions] and [!UICONTROL Activity Conversions] metrics in [!DNL Analysis Workspace], ensure that both metrics have [!UICONTROL Same Touch] attribution models applied. モデルは、列設定の歯車をクリックして、[!UICONTROL デフォルト以外のアトリビューションモデル]を有効にしてから、[!UICONTROL 同じタッチ]を選択することで適用できます。アトリビューションについて詳しくは、 [属性IQの概要](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) ( *Analyticsツールガイド*)を参照してください。

## アクティビティの設定中にマーケティング担当者が Analytics 指標を選択する場合、「アクティビティコンバージョン」は何を意味しますか？{#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Activity conversions&quot; will be empty if an [!DNL Analytics] metric was selected as the conversion metric for the activity.

## Analytics レポートで「未指定」と表示されるのはなぜですか？これはどういう意味ですか。{#unspecified}

他のレポートの場合、「未指定」は、データが分類ルールを満たしていなかったことを意味しますが、A4T の場合は、これは発生しないはずです。「未指定」と表示される場合、分類サービスがまだ実行されていません。アクティビティデータがレポートに表示されるまで、通常、24 ～ 72 時間かかります。それまではアクティビティがこのレポートに表示されないとしても、これらのアクティビティに結び付けられたすべての訪問者データは、キャプチャされ、分類が完了すると表示されます。

分類期間後、これらのレポートでは、データが Web サイトから収集された約 1 時間後にデータが表示されます。レポート内のすべての指標、セグメントおよび値は、アクティビティを設定したときに選択したレポートスイートから収集されます。

## アクティビティを非アクティブ化した後も Target 指標が Analytics に送信されるのはなぜですか？{#section_38AA8380A4D54A18972F1EF3E73E22EF}

[!DNL Target] に送信される [!DNL Analytics] 変数には、デフォルトで 90 日間の有効期限があります。この有効期限は、必要に応じてカスタマーケアが調整できます。 この設定は、すべてのアクティビティでグローバルなので、1 つの事例のために調整することはしないでください。

You might see [!DNL Target] variables sent to [!DNL Analytics] after the expiration period because the expiration is 90 days, but only if that user never sees another A4T-enabled [!DNL Target] activity. ユーザーが 45 日目にサイトに戻り、別のアクティビティを表示すると、A4T eVar 全体の値で、カウンターが 90 日にリセットされます。つまり、最初のキャンペーンは、1 日目から最大 45 + 90 = 135 日間残っていることになります。If the user keeps coming back, you might get to the point where you see metrics sent to [!DNL Analytics] in your reporting from much older activities. ユーザーが cookie を削除してサイトに戻らないと、このアクティビティ内の数は減少しますが、依然として表示されます。

つまり、アクティビティがアクティブであった期間に参加した参加者については、アクティビティが終了した後も、最長 90 日間はそのアクティビティでページビューや訪問数などが収集されます。ただし、[!UICONTROL アクティビティのインプレッション]指標を見ると、アクティビティの終了後にはインプレッションが表示されていません。

これは、期待どおりの正常な動作です。A4T 変数は、他の eVar のように機能します。有効期間（90 日）が経過するまで、値はユーザーに関連付けられます。その結果、アクティビティが 2 週間のみアクティブである場合、値は、少なくとも次の 90 日間はユーザーに関連付けられます。

ベストプラクティスは、アクティビティがライブだった期間のみのアクティビティのレポートを表示することです。The dates should be set correctly by default when you view the activity in [!DNL Analytics], so unless you have manually extended the date this shouldn’t be an issue from a reporting standpoint.

例として、A4T 変数が 90 日後に期限切れになり、テストが 1 月 1 日から 1 月 15 日までアクティブである場合を見てみましょう。

1 月 1 日に、ユーザーがサイトを訪れて、アクティビティ XYZ を 1 回表示し、その後 5 ページを表示しました。次の 2 週間の間、ユーザーはサイトに戻りませんでした。このユーザーのデータは、以下のようになります。

| アクティビティ名 | インスタンス数（インプレッション数） | ページビュー数 | 訪問回数 | 実訪問者数 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

ユーザーは 2 月 1 日に戻り、さらに 5 ページを表示して、追加の Target アクティビティは発生しませんでした。元のアクティビティは既にアクティブでなくなっています。アクティビティはアクティブではありませんが、eVar の永続性により、まだユーザーをフォローしています。現在のデータは、以下のようになります。

| アクティビティ名 | インスタンス数（インプレッション数） | ページビュー数 | 訪問回数 | 実訪問者数 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

ユーザーは 3 月 1 日に戻り、新しいアクティビティ、ABC を表示します。また、ユーザーは 5 ページを表示します。アクティビティ XYZ は、永続性により、まだユーザーをフォローしており、このユーザーには ABC が設定されたので、レポートには 2 行の項目が表示されます。

| アクティビティ名 | インスタンス数（インプレッション数） | ページビュー数 | 訪問回数 | 実訪問者数 |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

その後、ユーザーは 4 月 1 日に戻り、別の 5 ページを表示して、買い物をしました。最初の eVar 値の 90 日の有効期限は 4 月 1 日にリセットされたので、レポートに表示されます。そして、ユーザーに表示されるすべての Target アクティビティは、コンバージョンのクレジットを受け取りますが、コンバージョンの合計は重複除外されます。

| アクティビティ名 | インスタンス数（インプレッション数） | ページビュー数 | 訪問回数 | 実訪問者数 | 購入回数 |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| 合計 | 2 | 20 | 3 | 1 | 1 |

両方のエクスペリエンスがコンバージョン前に表示されているので、両方とも注文の「クレジット」を受け取ります。しかし、システムでの注文は 1 回のみなので、合計にはそれが反映されています。For [!DNL Target] reporting, because you aren’t putting a [!DNL Target] activity against another activity to see which is more successful, it doesn’t matter that all activities the user saw got credit. 1 つのアクティビティ内の 2 つの項目の結果を比較しており、ユーザーは同じアクティビティで異なるエクスペリエンスを表示できないので、注文クレジットの二次汚染を心配する必要はありません。

For more information, see [Conversion Variables (eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## Analytics と Analytics for Target（A4T）が実訪問者数指標の数を違うように計算するのはなぜですか？{#section_0C3B648AB54041F9A2AA839D51791883}

スチューデントの t 検定（信頼感指標）を使用してテストの勝者を選択する A/B テストを実行する場合、前提の 1 つは、固定された時間範囲があるということです。その固定サンプルサイズを調べていない限り、テストは統計的に有効ではありません。

The [!UICONTROL Unique Visitors] metric is different in [!DNL Analytics] and [!DNL Target] only when you are looking at a period of time that is shorter than the actual test. サンプルサイズに到達していない場合、テストは信頼できるものにはなりません。詳しくは、[Evan Miller の Web サイト](https://www.evanmiller.org/index.html)の [How Not to Run an A/B Test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)（英語）を参照してください。

The [!UICONTROL Unique Visitors] metric displays the number of people who have been exposed to the test who have visited the site during the specified time period. そうした人々は、依然としてテストに参加しており、カウントされる必要があります。1 週間の間に対象となった人数のみを表示したい場合、アクティビティのインプレッションがある訪問者のセグメントを作成して、レポートに適用できます。

You can shorten the amount of time the [!DNL Target] variable persists down to a session; however, that is usually problematic for tests where the conversion event isn’t as likely to happen within the same session.

## Analytics で、複数のエクスペリエンスで同じ訪問者がカウントされる場合があるのはなぜですか？{#section_1397E972D31C4207A142E4D2D6D794A2}

The following list explains reasons why the same visitor could be counted in multiple experiences in [!DNL Analytics]:

* The [!DNL Target] profile expired but the [!DNL Analytics] cookie is still there. In this situation, [!DNL Target] re-evaluates the user but [!DNL Analytics] considers the visitor to be the same person.
* 訪問者が `mbox3rdPartyId` を使用している場合、その匿名の訪問者がサードパーティの ID プロファイルと統合されると、 はサードパーティの ID と適合させるために、訪問者に別のエクスペリエンスを割り当てます。[!DNL Target]詳しくは、[mbox3rdPartyId のリアルタイムプロファイル同期](../../../c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732)を参照してください。
* [!DNL Analytics] は、異なるデバイスを同じ訪問者としてトラッキングする場合と、それらのデバイスをトラッキングする場合とでは異なる方法でトラッキングする場合があ [!DNL Target] ります。のサードパーティIDの設定 [!DNL Target] は、Analyticsの設定とは異なります。

## A4Tは仮想レポートスイートをサポートしていますか?

仮想レポートスイートはレポートスイートリストに含まれて&#x200B;*いません*。また、仮想レポートスイートのオーディエンスは A4T レポートではサポートされていません。

## アクティビティをアクティブ化した後に、A4T を使用するそのアクティビティのトラフィック割り当ての割合を変更できますか？

Changing the traffic allocation percentage in an activity after activation can cause inconsistent reporting in [!DNL Analytics] because the change impacts only new visitors. 再訪問者は影響を受けません。

ベストプラクティスとして、既存のアクティビティを停止し、アクティブ化の後に割合を変更するのではなく、新しいアクティビティを作成する必要があります。新規訪問者と再訪問者のデータから新しいアクティビティをレポートすることで、レポートの不一致が生じることはありません。
