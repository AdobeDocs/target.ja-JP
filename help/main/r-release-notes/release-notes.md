---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート、現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2c7a915d6dadcf38daa397dbdc2f86fb007a951e
workflow-type: tm+mt
source-wordcount: '2514'
ht-degree: 13%

---

# [!DNL Target] リリースノート（最新）

[!DNL Adobe Target] の最新の機能、機能強化および修正点について説明します。 これらのリリースノートでは、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、その他のプラットフォームコンポーネントのアップデート（該当する場合）についても説明します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## 必要となる、時間に依存する更新 {#time-sensitive}

[!BADGE &#x200B; 重要 &#x200B;]{type=Informative}

[!DNL Adobe Target] および実装に関する、時間的制約のある更新については、[!DNL Adobe] では、[!UICONTROL Experience League] を通じて詳細なリリースノートとドキュメントを提供しています。 実装に関連する主なハイライトを次に示します。

### [!DNL Target] UI バージョンの切り替えの廃止

+++詳細を表示
[!DNL Target] チームでは、トグルボタンを使用して、更新された [!DNL Target] UI とレガシーバージョンを切り替えられる一時機能を提供しています。 このオプションは、UI ロールアウトの最終フェーズでのみ使用できます。

![Target UI のバージョン切り替え ](/help/main/r-release-notes/assets/toggle.png)

ロールアウトが完了すると、切り替えスイッチが削除され、すべてのユーザーは更新された UI に永続的に移行します。 [!DNL Adobe] では、この機能はすぐに廃止される予定なので、事前に計画することをお勧めします。

#### 廃止タイムライン

最近の問題（主に複雑な顧客のカスタマイズに関連）が特定されたので、[!DNL Target] チームは廃止のタイムラインを調整しました。

* **2025 年 6 月 17 日**：すべての IMS 組織は、特定のユーザーまたは組織全体について、更新された [!DNL Target] UI で新しいエクスペリエンスのテストを開始できるように有効化されました。

* **2025 年 6 月 30 日**: [updated [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md) は、「UI バージョン」切り替えを有効にしたすべての IMS 組織のデフォルトのエクスペリエンスになりました。

   * 現在レガシー UI を表示しているお客様には、デフォルトで、ログイン時に更新された UI が表示されるようになりました。
   * UI バージョンの切り替えは 7 月末まで引き続き使用でき、必要に応じてユーザーを切り替えることができます。

  >[!IMPORTANT]
  >
  > [!DNL Adobe] では、更新された [!DNL Target] UI の使用を強くお勧めします。 [ 切り替えスイッチの動作の制限 ](#limitations) により、ブロッカーの問題が発生した場合にのみ、従来の UI に戻します。

* **2025 年 7 月 15 日～7 月 30 日**:UI バージョンの切り替えは、段階的に永続的に無効になります。 影響を受ける IMS 組織は、レガシー UI に戻すことができなくなりました。

   * 例外はケースバイケースでレビューされます。
   * トグルの非推奨（廃止予定）への遅延は、ブロッカーの問題が解決されている間、短期間（数日）のみ許可されます。

ご不明な点がある場合や [ この移行中に問題が発生する可能性がある場合は、](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md)Adobe カスタマーケアにお問い合わせください。

#### UI の切り替え動作の制限 {#limitations}

次の情報は、バージョン切り替えを使用する際に注意する必要がある制限事項を示しています。

* **新しいアクティビティの表示**：レガシー UI に切り替えた場合、更新された UI で作成されたアクティビティは表示されません。
* **既存のアクティビティの編集**：更新された UI の使用中に既存のアクティビティ（元々はレガシー UI で作成したもの）に加えられた変更が、web サイトに公開されます。 ただし、これらの更新は、戻してもレガシー UI には表示されません。レガシー UI から最後に作成された更新のみが表示されます。
* **アクティビティ詳細の一貫性**：使用する UI に関係なく、最新の変更がライブ web サイトに反映されます。 ただし、レガシー UI に表示されるのは、そのバージョン内で行われた最新の変更のみです。 更新された UI で編集されたアクティビティが、レガシー UI で表示されるものとは異なる表示になる場合は、混乱を招く可能性があります。

#### 更新された UI について学ぶための追加リソース

* [[!DNL Target] UI 更新 FAQ](/help/main/c-intro/updated-ui-faq.md)：この FAQ は、ナビゲーションの変更、機能の場所、一時的な UI バージョンの切り替えスイッチの廃止など、新しい [!DNL Target] UI と [!UICONTROL Visual Experience Composer] （VEC）に関するよくある質問に対応しています。 マーケター、開発者、管理者を問わず、この FAQ はスムーズに移行し、更新された UI を最大限に活用するのに役立ちます。
* [[!DNL Target Standard/Premium] 25.2.1 （2025 年 2 月 17 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2):[!DNL Target]、[!UICONTROL Activities] および [!UICONTROL Recommendations] （VEC）の [!UICONTROL Visual Experience Composer] の主な UI の変更点の概要を説明します。
* [[!DNL Target Standard/Premium] 25.1.1 （2025 年 1 月 9 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1):[!DNL Target] の [!UICONTROL Offers Library] での主な UI の変更点の概要を説明します。
* [ [!DNL Target] UI について ](/help/main/c-intro/understand-the-target-ui.md):[!DNL Target] に慣れるのに役立つ概要と、より詳細な情報と手順を説明するリンクを提供します。
* [[!UICONTROL Visual Experience Composer] の変更点 ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015 年 2 月 17 日（PT））では、更新された [!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新バージョンの違いについて説明します。
* [[!UICONTROL Visual Experience Composer] options](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新された VEC UI とそのオプションについて説明します。

+++

## [!DNL Target Standard/Premium] 25.7.1（2025年7月9日（PT））

最近の問題（主に複雑な顧客のカスタマイズに関連）が特定されたので、このリリースには次の修正と更新が含まれています。

**アクティビティ**

+++詳細を見る
* [!UICONTROL Activity QA] URL に不要なクエリパラメーター `at_preview_evaluate_as_true_audience_ids` が含まれていた問題を修正しました。 （TGT-52907）
* プレビュー URL に、ユーザーが明示的に入力したオーディエンス以外の追加オーディエンスが誤って含まれる問題を修正しました。 QA リンクまたはプレビューリンクを生成する際に、指定されたオーディエンスのみが適用されるように、この動作が修正されました。 （TGT-52912）
* トラフィック配分の設定中に最初に [!UICONTROL Auto-Target] （AA）を選択した場合、ユーザーが [!UICONTROL Auto-Allocate] （AT） アクティビティを作成できない問題を修正しました。 この問題により、バックエンドの検証エラーが発生し、アクティビティを保存できなくなりました。 （TGT-53096）

+++

**オーディエンス**

+++詳細を見る
* [!UICONTROL Approver] の役割を持つユーザーが、アクティビティのみのオーディエンスの絞り込みを追加または保存できない問題を修正しました。 これを試みると、ユーザーにはアクティビティを承認および管理するための十分な権限がある場合でも、「[ エディター ]」権限が必要であるという 403 Forbidden エラーが発生しました。 （TGT-52984）
* [!UICONTROL Remove Audience Refinement] オプションを使用してアクティビティ固有のオーディエンスを削除すると、オーディエンスが同じアクティビティ内で再選択するためにオーディエンスリストに表示されなくなる問題を修正しました。 この動作により、同じオーディエンスをゼロから再作成しない限り、ユーザーは同じオーディエンスを再度追加できませんでした。 （TGT-52979）
* アクティビティのみのオーディエンスの絞り込みが、アクティビティが保存される前であっても、場所から削除された直後に UI から消える問題を修正しました。 この動作は、期待される機能およびツールヒントのガイダンスと矛盾しており、「このライブラリの未使用のオーディエンスは、アクティビティが保存されると削除されます」と記載されています。 （TGT-52982）
* [!UICONTROL All Visitors] 以外のオーディエンスをアクティビティに割り当てようとした際の問題を修正しました。 保存すると、「リクエストを完了できません。 問題が解決しない場合は、[!UICONTROL Adobe Client Care] にお問い合わせください。」 （TGT-53008）
* アクティビティエディター内で新しいオーディエンスを作成して割り当てた後に、アクティビティの保存がブロックされる問題を修正しました。 表示されたエラーメッセージは「リクエストを完了できません。 問題が解決しない場合は、[!UICONTROL Adobe Client Care] にお問い合わせください。」 （TGT-52977）

+++

**[!UICONTROL Analytics for Target]（A4T）**

+++詳細を見る
* 既存のアクティビティをコピーし、レポートソースを [!DNL Adobe Analytics] （A4T）に変更すると、「無効なユーザー入力」エラーが発生する問題を修正しました。 [!DNL Analytics]、`restart_same_experience`、`restart_random_experience` など、`restart_new_experience` レポートと互換性のない特定の指標アクションが元のアクティビティから保持された場合に、このエラーがトリガーされました。 （TGT-52900）
* [!DNL Adobe Analytics] の手順で、[!UICONTROL Goals & Settings] （A4T）をレポートソースとして選択する際に、顧客がアクティビティを作成または保存できなかった問題を修正しました。 この問題は、特に [!UICONTROL Custom Event] 定の指標（「カスタムイベント 16」など）を選択する際に発生し、「無効なユーザー入力」というエラーが発生していました。 （TGT-52910）
* 「[!UICONTROL View in Analytics]」リンクをクリックすると、対象の [!DNL Analytics] ダッシュボードではなくホームページにユーザーがリダイレクトされる問題を修正しました。 （TGT-53092 および TGT-53093）
<!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)
* Fixed an issue when viewing a [!DNL Recommendations] activity in the updated [!UICONTROL Overview] UI, the [!UICONTROL Goals & Settings] section fails to load when [!DNL Adobe Analytics] (A4T) is selected as the reporting source. The following error message was displayed: "Something went wrong. We cannot complete your request. Please contact Adobe Client Care if the problem persists." (TGT-52999)-->

+++

**[!UICONTROL Experiences]および[!UICONTROL Offers]**

+++詳細を表示
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* すべてのコンテンツオプションが削除された後、[!UICONTROL Manage Content] 機能が場所の状態を適切に検証しなかった問題を修正しました。 これにより、アクティビティ設定を保存または続行しようとすると、動作の不一致やエラーが発生する可能性があります。 （TGT-52801）
* 新しいページを追加し、異なるエクスペリエンス内の特定の要素を削除する際に、「無効な入力」エラーが発生する問題を修正しました。 このエラーは、特にエクスペリエンス間の切り替えや共有ページ構造の変更を行う際に、要素の操作中に重複 `LocalIds` が生成されることが原因でトリガーされました。 （TGT-52720）
* [!UICONTROL Generate Adhoc Offer] 機能を使用すると、[!UICONTROL Manage Content] パネルに未定義の場所が表示される問題を修正しました。 （TGT-53076 および TGT-53070）
* [!UICONTROL Targeting] の手順から [!UICONTROL Experiences] に戻る際に、HTML オファーを使用して行った変更が見つからない場合があるお客様への動作を明確にしました。 この顧客の場合、影響を受ける web サイトは、ページの読み込みごとに変更される複数の DOM セレクターを動的に生成しました。 その結果、エディターを再度開くと、変更に元々使用されていたセレクターが見つからなくなり、変更が見つからないか無効のように見えます。 これは設計どおりの動作です。 エディターで変更が視覚的に保持されるように、ページの再読み込み時に変更されない、安定した一貫性のあるセレクターをクライアントで使用することをお勧めします。 （TGT-52874）
* 除外されたエクスペリエンスの一部であるオファーを削除または非アクティブ化しようとすると、「無効なユーザー入力」エラーがトリガーされる問題を修正しました。 この問題は、含まれているエクスペリエンスでオファーが積極的に使用されていなかったにもかかわらず発生しました。 （TGT-52917）

+++

**フォームベースの Experience Composer**

+++詳細を見る
* フォームベースのアクティビティで、エクスペリエンスを複製し、複製されたエクスペリエンスの 1 つでカスタムコードを編集すると、すべての複製されたエクスペリエンスにこれらの変更が意図せず適用される問題を修正しました。 各エクスペリエンスは、複製後に独自のカスタムコードを保持するようになりました。 （TGT-51600）

+++

**ローカリゼーション**

+++詳細を見る
* 「プレビューエクスペリエンス」文字列の韓国語ロケール（ko-KR）のコンテキスト翻訳の問題を修正しました。 （TGT-52928）
* 複数のテキスト文字列の簡体字中国語（zh_CN）翻訳で識別される用語の不一致を修正しました。 （TGT-52954 および TGT-52955）

+++

**[!DNL Recommendations]**

+++詳細を見る
* 新しい [!DNL Recommendations] フィード [ ステータス ](/help/main/c-recommendations/c-products/feeds.md#status):[!UICONTROL Partial Import Failed] を追加しました。 （KB-2215）
* [!DNL Recommendations] を使用してアクティビティを追加する場合に、アクティビティ作成ワークフローに影響す [!UICONTROL promotions] 問題を修正しました。 ユーザーが「[!UICONTROL Promote by Attribute]」を選択してフィルタールール（[!UICONTROL Parameter Matching] など）を追加した場合、アクティビティを保存して再編集した後、選択したルールタイプとオペランドの値が保持されませんでした。 再度開くと、フィルタールールのタイプが予期せず変更され、オペランド値が欠落することがありました。 （TGT-53059）
* [!DNL Recommendations] UI で、単一のルールで作成されたプロモーションが、ルールのロジックに関係なく、誤って解釈され、「項目のリスト」プロモーションタイプとして表示される問題を修正しました。 （TGT-53063）
* 更新された [!UICONTROL Overview]UI を使用する際に、[!UICONTROL Download Recommendations Data] を含む [!UICONTROL Experience Targeting] （XT）アクティビティで「[!DNL Recommendations]」ボタンが表示されない問題を修正しました。 （TGT-52730 および TGT-52756）
* 以前は、Recommendations UI には、フィードから正常に読み込まれたエンティティ数のみが表示されていました。 ただし、バックエンドメッセージの形式には、読み込まれたエンティティの数と、形式のエンティティの合計数の両方が含まれます（`# of entities imported / # of total entities`）。 この不一致により、ユーザーには UI の最初の値（読み込まれたカウント）のみが表示され、混乱が生じていました。 UI に両方の数値が表示されるようになりました。 （TGT-53073）

+++

**レポート**

+++詳細を見る
* [!UICONTROL Export order details to CSV] ページから「[!UICONTROL Reports]」を選択すると、空のファイルがダウンロードされる問題を修正しました。 この問題は、有効な注文データがアクティビティに存在する場合でも発生していました。 （TGT-52225）
* 新しいレポートオーディエンスを作成して割り当てた後にアクティビティを保存しようとする際の問題を修正しました。 返されたエラーメッセージは「アクセスが拒否されました。 この操作を実行するには、[ エディター ]」のすべての権限が必要です。 この問題は、ユーザーが承認者レベルのアクセス権を持っているにもかかわらず発生しました。 （TGT-53103）

+++

**[!UICONTROL Visual Experience Composer]（VEC）**

+++詳細を見る
* ビューに変更を適用すると、ビューが複製され、アクティビティが「無効なユーザー入力」エラーを返す問題を解決しました。 この修正により、重複や検証エラーがトリガーされずに、ビューの変更が正しく適用されます。 （TGT-52886）
* カスタムコードの変更が間違ったエクスペリエンスに対して正しく表示されない問題を修正しました。 具体的には、あるエクスペリエンス向けの変更が別のエクスペリエンスで示されたため、混乱が生じ、ライブアクティビティの設定が誤る可能性がありました。 （TGT-52776）
* 新しい VEC UI でカスタムコードの変更を編集または保存できない問題を修正しました。 具体的には、

   * カスタムコードブロックを編集して保存した後、変更内容が UI や QA プレビューに反映されませんでした。
   * アクティビティを閉じて再び開かない限り、変更を削除できない場合がありました。
   * 回避策として、ユーザーはコードをコピーし、変更を削除した後、更新されたコンテンツを使用して手動でコードを再作成する必要がありました。 （TGT-53072）

* カスタムコードを編集および保存すると、[!UICONTROL Modifications] パネルが応答しなくなる問題を修正しました。 （TGT-53075）
* バリアントエクスペリエンスでカスタムコードに対して行った変更が、意図せず [!UICONTROL Control] スタムエクスペリエンスに反映される問題を修正しました。 これにより、配信動作に意図しない変更が生じました。 [!UICONTROL Control] エクスペリエンスが、他のエクスペリエンスで行われたカスタムコードの編集から分離されたままになりました。 （TGT-52413）
* エディターが完全に読み込まれる前にユーザーが 2 番目のエクスペリエンスをクリックした場合、あるエクスペリエンス（エクスペリエンス B など）に加えられた変更が意図せず別のエクスペリエンス（エクスペリエンス A）に複製される問題を修正しました。 また、最初に選択したエクスペリエンスに変更がなかった場合、この動作によって変更が失われる可能性もあります。 （TGT-52597）
* アクティビティ作成の [!UICONTROL Modifications] のステップで行われた変更が一貫して保存されなかった問題を修正しました。 場合によっては、すべての手順を完了して「[!UICONTROL Save]」をクリックしても、保存プロセス中に目に見えるエラーが発生しなかったにもかかわらず、「[!UICONTROL Modifications]」セクションで追加されたカスタムスクリプトがライブサイトに反映されないことがあります。 （TGT-52661）
* カスタムコードの変更が正しく保存されず、同じアクティビティ内の複数のエクスペリエンスに意図せずミラーリングされる問題を修正しました。 また、特定のアクティビティを開いたり更新したりする際にアクセスの問題が発生し、空白の画面が表示されていました。 これらの問題が解決され、安定したアクティビティ編集と正確なエクスペリエンス分離が実現しました。 （TGT-52594）
* ユーザーが [!UICONTROL Browse Mode] ージ内で別の URL を参照できない問題を修正しました。 これにより、テスターとエディターは同じアクティビティセッション内の代替ページを検証またはプレビューできませんでした。 （TGT-53052）
* アクティビティの作成中に複数の [!UICONTROL Visual Experience Composer] （VEC）インスタンスが同時に開く問題を修正しました。 この問題は、ユーザーが [!UICONTROL Enhanced Experience Composer] （EEC）を無効にし、[!UICONTROL Page Delivery] の手順で web サイトの URL から末尾のスラッシュを削除した場合に発生しました。 （TGT-52782）
* ユーザーが別の指標を選択した後でも、[!UICONTROL Revenue] の手順の [!UICONTROL Goals & Settings] 指標ドロップダウンが誤って [!UICONTROL Revenue per Visit] （RPVISIT）にデフォルト設定される問題を修正しました。  指標の設定パネルを折りたたんで再展開すると、以前に選択した値がリセットされる問題が発生しました。 （TGT-52811 および TGT-52878）
* [!UICONTROL Automated Personalization] （AP）および [!UICONTROL Multivariate Testing] （MVT）アクティビティにおけるオファーの命名とコンテンツの翻訳に関連するアクティビティ作成ワークフローの問題をいくつか修正しました。

  対処された主な問題：

   * 同じ名前の複数のHTML オファー（「エクスペリエンス」など）を作成すると、「オファー名の重複は許可されていません」エラーがトリガーされますが、UI に競合を引き起こしているオファーが明確に示されませんでした。
   * 右のパネルを使用してオファーの名前を変更すると、UI 内の名前が更新されますが、変更が「[!UICONTROL Manage Content]」タブまたは「[!UICONTROL Offers]」タブに反映されなかったので、永続的な検証エラーが発生します。
   * MVT アクティビティでは、名前を変更した後に重複した名前エラーが保持されませんでしたが、更新されたオファー名がタブ間で一貫して反映されることはできませんでした。 （TGT-52933）

+++

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| [ドキュメントの変更点](/help/main/r-release-notes/doc-change.md) | リリースノートに記載されていない、このガイドの更新点に関する詳細情報を表示します。 |
| [以前のリリースのリリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 以前のリリースの Target Standard および Target Premium の新機能および拡張機能に関する情報を確認できます。 |
| [Adobe Experience Cloud リリースノート ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [Adobe 優先製品のアップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
