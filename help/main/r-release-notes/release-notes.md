---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート；現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 098415849152065b734cbebbab8dcf1d0805e202
workflow-type: tm+mt
source-wordcount: '1779'
ht-degree: 25%

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

![Target UI バージョンの切替スイッチ](/help/main/r-release-notes/assets/toggle.png)

ロールアウトが完了すると、切り替えが削除され、すべてのユーザーは更新された UI に恒久的に移行します。 [!DNL Adobe] では、この機能はすぐに廃止される予定なので、事前に計画することをお勧めします。

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

#### UI の切替スイッチの動作の制限 {#limitations}

次の情報は、バージョン切り替えを使用する際に注意する必要がある制限事項を示しています。

* **新しいアクティビティの表示**：更新された UI で作成したアクティビティは、レガシー UI に戻すと表示されなくなります。
* **既存のアクティビティの編集**：更新された UI の使用中に、既存のアクティビティ（元々はレガシー UI で作成したもの）に加えられた変更が web サイトに公開されます。 ただし、これらの更新は、元の場所に戻した場合はレガシー UI に表示されず、レガシー UI から最後に作成された更新のみが表示されます。
* **アクティビティ詳細の一貫性**：使用する UI に関係なく、最新の変更はライブ web サイトに反映されます。 ただし、レガシー UI に表示されるのは、そのバージョン内で行われた最新の変更のみです。 更新後の UI で編集されたアクティビティが、従来の UI で表示されたアクティビティと異なる場合は、この状況が原因で混乱が生じる可能性があります。

#### 更新された UI について学ぶための追加リソース

* [[!DNL Target] UI の更新に関する FAQ](/help/main/c-intro/updated-ui-faq.md)：この FAQ では、ナビゲーションの変更、機能の場所、一時的な UI バージョンの切替スイッチの非推奨（廃止予定）など、新しい [!DNL Target] UI と [!UICONTROL Visual Experience Composer]（VEC）に関するよくある質問について説明します。マーケター、開発者、管理者のいずれであっても、この FAQ はスムーズに移行し、更新された UI を最大限に活用するのに役立ちます。
* [[!DNL Target Standard/Premium]  25.2.1（2025年2月17日（PT））リリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：[!UICONTROL Activities]、[!UICONTROL Recommendations]、[!UICONTROL Visual Experience Composer]（VEC）の [!DNL Target] での主な UI の変更の概要について説明します。
* [[!DNL Target Standard/Premium]  25.1.1（2025年1月9日（PT））リリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：[!UICONTROL Offers Library] の [!DNL Target] での主な UI の変更の概要について説明します。
* [ [!DNL Target]  UI ](/help/main/c-intro/understand-the-target-ui.md)について：[!DNL Target] に慣れるための概要と、より詳細な情報と手順を説明するリンクを提供します。
* [[!UICONTROL Visual Experience Composer] の変更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)：[!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015年2月17日（PT））では、更新された [!UICONTROL Visual Experience Composer]（VEC）が導入されています。この記事では、VEC のレガシーバージョンと更新されたバージョンの違いについて説明します。
* [[!UICONTROL Visual Experience Composer] オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新された VEC UI とそのオプションについて説明します。

+++

## データストリームの更新（2025 年 9 月 19 日）

データストリーム ID とサンドボックスの組み合わせは、[!DNL Adobe Target] の宛先接続で一意である必要があります。

データストリーム ID とサンドボックス名の組み合わせ [!DNL Target]IMS 組織内で一意にする必要があることを強制するために、宛先接続の検証ロジックを更新しました。つまり、

* 複数の [!DNL Target] ース宛先接続で、同じデータストリーム ID とサンドボックス名のペアを再利用することはできません。
* 異なるサンドボックスで設定されている場合に限り、同じデータストリーム ID を異なる接続に使用できます。
* このルールは、「なし」が選択されている場合を含め、すべてのデータストリーム選択に適用されます。

この更新により、一貫性のある設定が保証され、マルチサンドボックス環境間での競合が回避されます。 詳しくは、[Adobe Target宛先 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} ガイドの *Experience Platform接続* を参照してください。

## [!DNL Target Standard/Premium] 25.9.1 （2025 年 9 月 5 日）

このリリースには、次の更新および修正が含まれています。

**[!UICONTROL Experience Fragments]**

+++詳細を表示
* **オファーのユーザー属性 [!UICONTROL AEM Experience Fragment] 改善されました。** VEC で、[!UICONTROL Last updated] （XF）の「[!UICONTROL AEM Experience Fragment]」フィールドにユーザー名ではなくコード ID が正しく表示されない問題を修正しました。 この不一致は、更新された UI でのオファー選択時に発生し、最後のエディターの名前を正しく表示していた従来の UI およびHTML オファーとの一貫性を失わせました。 この修正により、オファータイプ間で一貫したユーザー属性が保証され、透明性が向上し、期待される動作に合わせることができます。 （TGT-52880 および TGT-52898）

+++

**Offer Decisioning**

+++詳細を表示
* **ODE オファーで解決されたオファー決定エラー。** [!DNL Target] を通じて挿入されたオファー決定エンジン（ODE）オファーで、形式メタデータが欠落していることにより 400 エラーが返される問題を修正しました。 このエラーメッセージは、MIME タイプが null で、オファーの決定が正常に処理されないことを示しました。 この修正により、オファーメタデータの適切な処理、パーソナライズされたコンテンツ配信の機能の復元、マーケティングキャンペーンの中断のない実行が可能になります。 （TGT-53635）
* **ODS オファーレンダリングの問題が解決されました。** 更新された UI で VEC を使用してアクティビティを作成した場合、[!DNL Offer Decision Service] （AJO）を介して作成された [!DNL Adobe Journey Optimizer] （ODS）オファーがレンダリングされない問題を修正しました。 同じ設定が従来の UI で正しく動作したため、混乱が生じ、キャンペーンの実行がブロックされました。 この修正により、両方の UI バージョンで一貫したオファー配信が保証され、AJO駆動型パーソナライゼーションで期待される動作が復元されます。

+++

**レポート**

+++詳細を表示
* **更新されたレポートの概要 UI の「レポート」セクションの「ダウンロード」オプションが復元されました。** 新しい概要 UI で、「レポート」セクションに「[!UICONTROL Download]」ボタンが見つからず、ユーザーが属性重要度スコアを書き出せない問題を解決しました。 この更新により、完全な書き出し機能が復元され、分析およびレポート用のダウンロード可能なデータに効率的にアクセスできるようになります。 （TGT-53222）
* **[!UICONTROL Download full CSV report]ビュー [!UICONTROL Important attributes] ボタンが復元されました。** 更新されたアクティビティ作成 UI で、レポートビューの「[!UICONTROL Download full CSV report]」セクションに「[!UICONTROL Important Attributes]」ボタンが表示されない問題を解決しました。 この修正により、ダウンロード可能なインサイトへのアクセスが復元され、更新された UI とレガシー UI の両方で一貫した機能が確保されます。 （TGT-53238）
* **更新された概要 UI の [!UICONTROL Auto Target] レポートに影響する UI の問題を解決。** 更新された概要インターフェイスの複数の UI の問題を修正し、アクティビティのレポート [!UICONTROL Auto Target] 影響を与えました。 以下の修正が含まれます。

   * 概要レポートにリフト指標と信頼性指標がない
   * 「モデルが作成されました」チェックボックスのカラーインジケーターが正しくありません
   * [!DNL Analytics] ータにデータの相違があるにもかかわらず、機能しないグラフレポート
   * [!UICONTROL Automated Segments] および [!UICONTROL Important Attributes] レポートのダウンロードリンクがありません
   * 壊れた [!UICONTROL Automated Segments] レポートの表示

  これらの修正により、期待されるレポート動作が復元され、更新された UI 全体での [!UICONTROL Auto Target] パフォーマンスの可視性が向上します。 （TGT-53484）

+++

**[!UICONTROL Visual Experience Composer]**

+++詳細を表示
* **更新された UI でパラメーターのプレゼンス条件を修正したフォームの検証。** 更新された UI で、「[!UICONTROL Custom mbox parameter value is present]」または「[!UICONTROL Parameter is present]」を選択する際に、顧客が誤って値を入力する必要があった問題を解決しました。 この動作は、目的のロジックと競合し、値に関係なくパラメーターの存在を単にチェックします。 この修正により、フォームの検証が期待される動作に合わせられ、よりスムーズなアクティビティ設定が可能になり、更新された UI の完全な採用がサポートされます。 （TGT-53638）
* **ページ配信のパラメータープレゼンスルール用に修正されたフォームロジック。」** 更新された UI で、「[!UICONTROL Parameter is present]」、「[!UICONTROL Parameter is not present]」、「[!UICONTROL Parameter value is present]」、「[!UICONTROL Parameter value is not present]」などのページ配信ルールを選択する際に、ユーザーが追加のパラメーター値を入力する必要が誤って発生していた問題を解決しました。 この動作は、従来の UI と一貫性がなく、値を指定せずにパラメーターの存在を検出するという意図されたロジックと矛盾していました。 この修正により、期待されたルール設定動作が復元され、アクティビティの設定が合理化され、ユーザビリティが向上します。 （TGT-53640）
* **更新された UI で、複数ページのルールビルダーの検証ロジックが改善されました。** 更新された UI 内の複数ページルールビルダーでの複数の検証の問題を解決しました。 以下の修正が含まれます。

   * mbox パラメーターが空の場合にルールを作成できない
   * 無効なルール状態に対する適切なエラーメッセージの表示
   * オペランド値を必要としない単項演算子およびパラメーターベース演算子の検証ロジックを修正しています
   * 保存機能を復元して単項演算子を使用したハッシュフラグメントルールを有効にする

  これらの更新により、正確なルール設定が保証され、複雑なページ配信シナリオでの操作性が向上します。 （TGT-53722）
* **A/B および MVT アクティビティで解決された場所名の変更の問題。** 更新された UI で、[!UICONTROL A/B Test] または [!UICONTROL Multivariate Test] （MVT）アクティビティの場所の名前変更が、場所リスト、ターゲット設定、戻りの間を移動した後も保持されなかったバグを修正しました。 この更新により、場所の名前の変更が保存され、アクティビティワークフロー全体で一貫して反映されます。 （TGT-52367）
* **更新された UI で、MVT および AP アクティビティの場所の名前の永続性を修正しました。** 更新された UI で、[!UICONTROL Multivariate Test] （MVT）および [!UICONTROL Automated Personalization] （AP）アクティビティで編集された場所名が正しく保存されない問題を修正しました。 場所の名前を変更した後、タブ間を移動（[!UICONTROL Targeting] や [!UICONTROL Experiences] など）すると、名前が以前の状態に戻りました。 この修正により、タブ間で一貫した場所の命名が確保され、アクティビティの設定時の信頼性が向上します。 （TGT-52927）
* **MVT アクティビティのエクスペリエンスを管理パネルで場所のラベル付けが修正されました。** 更新された UI で、[!UICONTROL Manage Experiences] （MVT）アクティビティの [!UICONTROL Multivariate Test] パネルに一貫性のない場所番号が表示される問題を修正しました。 この修正により、場所ラベルが順次となり、ユーザー定義の変更と正しく連携するようになり、エクスペリエンスの設定中の明確さと使いやすさが向上します。 （TGT-52929）

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
