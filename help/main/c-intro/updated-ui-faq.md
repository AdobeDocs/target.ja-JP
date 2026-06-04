---
keywords: target ユーザーインターフェイス；ユーザーインターフェイス；ui；よくある質問；faq
description: 更新された [!DNL Target]t ユーザーインターフェイスに関する質問と回答。
title: 更新された [!DNL Target] UIに関するFAQはどこにありますか？
feature: Overview
exl-id: 75db4791-ca51-472d-99dd-583f7a74b222
TQID: https://experienceleague.adobe.com/yMMNq7GL-lvpzJL9nw9mPm8QHmp0A0hgDK3spB1Z2r0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2013
ht-degree: 9%

---

# [!DNL Target]件のUI更新に関するFAQ

2025年の新機能として、[!DNL Adobe Target]の再設計されたユーザーインターフェイスは、すべてのユーザーに対してよりクリーンで直感的なエクスペリエンスを提供します。 このFAQでは、ナビゲーションの変更、機能の配置、一時的なUI トグルの削除など、[!DNL Target] UIと[!UICONTROL Visual Experience Composer] （VEC）の主要な更新について説明します。 マーケター、開発者、管理者のいずれであっても、スムーズな移行とスマートなワークフローを実現するためのガイドです。

## Target UI バージョンの廃止に関するタイムラインが更新されましたか？

+++詳細を見る
[!DNL Target] チームでは、更新された[!DNL Target] UIとレガシーバージョンを切り替える一時的な機能を切り替えボタンを使用して提供しています。 このオプションは、UI ロールアウトの最終フェーズでのみ使用できます。

![Target UI バージョンの切替スイッチ](/help/main/r-release-notes/assets/toggle.png)

ロールアウトが完了すると、トグルが削除され、すべてのユーザーが更新されたUIに永続的に移行します。 この機能は間もなく段階的に廃止されるので、[!DNL Adobe]は事前に計画することをお勧めします。

### 非推奨タイムライン

最近の問題が特定されたため、主に複雑な顧客カスタマイズに関連して、[!DNL Target] チームは非推奨タイムラインを調整しました。

* **2025年6月17日**：すべてのIMS組織が、更新された[!DNL Target] UIに対して、特定のユーザーまたは組織全体に対して、新しいエクスペリエンスのテストを開始するために有効になりました。

* **2025年6月30日**: [更新 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)が、UI バージョンの切り替えを有効にしたすべてのIMS組織のデフォルトエクスペリエンスになりました。

   * 現在、従来のUIを表示しているお客様は、デフォルトで、ログイン時に更新されたUIを表示するようになりました。
   * UI バージョンの切り替えは7月末まで利用でき、必要に応じて切り替えることができます。

  >[!IMPORTANT]
  >
  > [!DNL Adobe]は、更新された[!DNL Target] UIの使用を強くお勧めします。 切り替えスイッチの動作に[制限があるため、ブロッカーの問題が発生した場合にのみ、従来のUIに切り替えます](#limitations)。

* **2025年7月15日～7月30日**: UI バージョンの切り替えは、段階的に完全に無効になります。 影響を受けるIMS組織は、従来のUIに戻すことができなくなりました。

   * 例外はケースバイケースでレビューされます。
   * トグルの非推奨化に対する遅延は、ブロッカーの問題が解決される間、短期間（数日）のみ付与されます。

ご不明な点がある場合や、この移行中に問題が発生すると予想される場合は、[Adobe カスタマーケア ](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md)にお問い合わせください。

### UI の切替スイッチの動作の制限 {#limitations}

次の情報では、バージョン トグルを使用する際に注意すべき制限事項について説明します。

* **新しいアクティビティの表示**：更新された UI で作成したアクティビティは、レガシー UI に戻すと表示されなくなります。
* **既存のアクティビティの編集**：更新されたUIを使用している間に既存のアクティビティ（もともとレガシーUIで作成された）に加えられた変更が、web サイトに公開されます。 ただし、切り替えても、これらの更新はレガシーUIには表示されません。レガシーUIから行われた最後の更新のみが表示されます。
* **アクティビティの詳細の一貫性**：使用するUIに関係なく、最新の変更がライブ web サイトに反映されます。 ただし、従来のUIには、そのバージョン内から行われた最新の変更のみが表示されます。 更新されたUIで編集されたアクティビティが、従来のUIで表示されるものとは異なる場合、この状況が混乱を引き起こす可能性があります。

### 更新されたUIに関する詳細なリソース

* [[!DNL Target] UI更新に関するFAQ](/help/main/c-intro/updated-ui-faq.md)：このFAQでは、ナビゲーションの変更、機能の場所、一時的なUI バージョンの廃止トグルなど、新しい[!DNL Target] UIと[!UICONTROL Visual Experience Composer] （VEC）に関するよくある質問に対応しています。 マーケター、開発者、管理者のいずれであっても、この FAQ はスムーズに移行し、更新された UI を最大限に活用するのに役立ちます。
* [[!DNL Target Standard/Premium] 25.2.1 （2025年2月17日）リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): [!UICONTROL  アクティビティ ]、[!UICONTROL 推奨事項]、および[!UICONTROL Visual Experience Composer] （VEC）の[!DNL Target]の主要なUI変更の概要を提供します。
* [[!DNL Target Standard/Premium] 25.1.1 （2025年1月9日）リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): [!UICONTROL  オファーライブラリ ]の[!DNL Target]の主要なUI変更の概要を提供します。
* [ [!DNL Target]  UI ](/help/main/c-intro/understand-the-target-ui.md)について：[!DNL Target] に慣れるための概要と、より詳細な情報と手順を説明するリンクを提供します。
* [[!UICONTROL Visual Experience Composer]の変更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015年2月17日）では、更新された[!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新されたバージョンの違いについて説明します。
* [[!UICONTROL Visual Experience Composer] オプション ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新されたVEC UIとそのオプションについて説明します。

+++

## 更新された[!DNL Target] UIに関する詳細はどこで確認できますか？

+++詳細
更新された[!DNL Target] UIについて詳しくは、次のリソースを参照してください。

* [[!DNL Target Standard/Premium] 25.1.1 （2025年1月9日）リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): [!UICONTROL  オファーライブラリ ]の[!DNL Target]の主要なUI変更の概要を提供します。

* [ [!DNL Target]  UI ](/help/main/c-intro/understand-the-target-ui.md)について：[!DNL Target] に慣れるための概要と、より詳細な情報と手順を説明するリンクを提供します。

* [[!UICONTROL Visual Experience Composer]の変更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015年2月17日）では、更新された[!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新されたバージョンの違いについて説明します。

* [[!UICONTROL Visual Experience Composer] オプション ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新されたVEC UIとそのオプションについて説明します。

+++

## 更新されたUIは、現在のすべての[!DNL Target]のお客様、[!UICONTROL 標準]および[!UICONTROL  プレミアム ]に対して使用できますか？

+++詳細
更新されたUIは、[!DNL Target]のお客様、[!UICONTROL Standard]および[!UICONTROL Premium]すべてに使用できます。 アップグレードされたライセンスやSKUは必要ありません。

一時的なUI バージョン トグルのロールアウトと非推奨（廃止予定）について詳しくは、[知っておく必要がある時間制限のある更新](/help/main/r-release-notes/release-notes.md#time-sensitive)を参照してください。

+++

## 従来のUIが廃止される前に、現在のバグのリストは修正されますか？

+++詳細
[!DNL Target] チームは、新しいUI ロールアウトに関連する問題に積極的に対処しています。 アップデートと継続的な改善について詳しくは、リリースノートを参照してください。

一時的なUI バージョン トグルのロールアウトと非推奨（廃止予定）について詳しくは、[知っておく必要がある時間制限のある更新](/help/main/r-release-notes/release-notes.md#time-sensitive)を参照してください。

+++

## お客様が従来のUIを使い続けたい場合、UI バージョンの切り替えスイッチをアカウントに残すことはできますか？

+++詳細
UI バージョン切り替えは、更新された[!DNL Target] UIとレガシーバージョンを切り替える一時的な機能で、切り替えボタンを使用できます。 このオプションは、UI ロールアウトの最終フェーズでのみ使用できます。 ロールアウトが完了すると、トグルが削除され、すべてのユーザーが更新されたUIに永続的に移行します。

UI バージョン トグルの使用には、新しいアクティビティの表示、既存のアクティビティの編集、アクティビティの詳細の一貫性など、いくつかの制限があります。

詳しくは、[時間に応じた更新を参照してください。](/help/main/r-release-notes/release-notes.md#time-sensitive)

+++

## 完全なロールアウトが完了するまで、[!DNL Adobe]は更新されたUIへの移行を遅らせることができますか？

+++詳細
[!DNL Target]には、UI移行のタイミングを遅延またはカスタマイズするオプションはありません。 顧客は段階的に移行され、ロールアウト スケジュールは[!DNL Adobe]によって管理されます。 最新のアップデートについては、リリースノートを参照してください。

UI バージョン トグルの使用には、新しいアクティビティの表示、既存のアクティビティの編集、アクティビティの詳細の一貫性など、いくつかの制限があります。

詳しくは、[時間に応じた更新を参照してください。](/help/main/r-release-notes/release-notes.md#time-sensitive)

+++

## 更新されたVECは、並べ替え、サイズ変更、移動、非表示、削除オプションをどのように処理しますか。これらのオプションは、従来のVECとどのように異なりますか。 {#options}

+++詳細
**[!UICONTROL Rearrange*]*：従来のVECでは、「rearrange」オプションがオーバーレイを使用して、ユーザーが兄弟グループ内の要素を再配置できるようにしました。 運動は兄弟の要素の間の順序を変えることに限定されていました。

更新されたVECでは、この機能は前進および後退アクションによって合理化されます。 これらのコントロールは、重なり順に前後に移動することで、レイアウト内のエレメントの位置を水平方向と垂直方向の両方で調整します。

**サイズ変更**: [!UICONTROL  サイズ変更]機能は、[!UICONTROL  サイズ ] セクションの[!UICONTROL  プロパティ ] パネルにあります。 ユーザーは、要素の幅と高さを直接調整できます。 詳細設定には次のものが含まれます。

* 最小/最大幅および高さコントロール
* オーバーフロー動作の設定。
* メディア要素のオブジェクト適合オプション

これらのツールは、エレメントの寸法とレイアウト動作を正確に制御できます。

**Move**: [!UICONTROL Move] オプションは、[!UICONTROL 位置] セクションの[!UICONTROL  プロパティ ] パネルにあります。 このオプションを使用すると、ユーザーは次のことが可能になります。

* エレメントの位置を設定します（例：絶対、相対、固定）。
* レイヤーのZ インデックスを定義する
* ポジショニングタイプの選択

更新された[!UICONTROL  プロパティ ] パネルは、カスタムのインラインスタイルもサポートしており、プリセットオプションがレイアウトのニーズを満たさない場合でも柔軟性を提供します。

**[!UICONTROL 非表示]**: [!UICONTROL 非表示]機能は[!UICONTROL  プロパティ ] パネルにあります。 要素を選択した後、[!UICONTROL 要素を非表示]をクリックして、削除せずに要素をビューから削除します。 これは、デザインまたはプレビュー中に表示を管理する場合に便利です。

**[!UICONTROL 削除]**: [!UICONTROL 削除]機能には、[!UICONTROL  プロパティ ] パネルからアクセスできます。 エレメントを選択した後、「エレメントを削除」をクリックしてページからエレメントを削除します。 このアクションは、レイアウトから要素を完全に削除します。

+++

## [!UICONTROL  コンポーネント ]、[!UICONTROL 変更]、[!UICONTROL  プロパティ ]のレールを折りたたんで、[!UICONTROL  デザイン ] パネルを拡大できますか？ {#collapse}

+++詳細

はい。レールを折りたたんで、[!UICONTROL Design] キャンバスを拡張して、編集を容易にすることができます。 その方法を次に示します。

>[!NOTE]
>
>[!UICONTROL  コンポーネントを表示] アイコン （![ コンポーネントを表示アイコン ](/help/main/assets/icons/Add.svg)）と[!UICONTROL 変更を表示] アイコン （![変更を表示パネル ](/help/main/assets/icons/History.svg)）は、適切なオプションを表示するための切り替えスイッチとして機能します。

**[!UICONTROL  コンポーネント ] レール**&#x200B;を折りたたむ

[!UICONTROL  コンポーネント ] パネルを折りたたんで[!UICONTROL  デザイン ] キャンバスを拡大し、[!UICONTROL  コンポーネント ] パネルを開いている間に、（![ コンポーネントを表示アイコン ](/help/main/assets/icons/Add.svg)）アイコンをクリックします。

**変更] パネル**&#x200B;を折りたたむ[!UICONTROL 

[!UICONTROL 変更] レールを折りたたんで[!UICONTROL  デザイン ] キャンバスを拡大し、[!UICONTROL 変更] レールを開いている間に、[!UICONTROL 変更]を表示アイコン （![変更を表示](/help/main/assets/icons/History.svg)）をクリックします。

**[!UICONTROL  プロパティ ] レール**&#x200B;を折りたたむ

[!UICONTROL  プロパティ ] レールを折りたたんで[!UICONTROL  デザイン ] キャンバスを拡大するには、レールの右側にある[!UICONTROL  プロパティの表示/非表示] アイコン （![ プロパティ アイコン ](/help/main/assets/icons/Propertie.svg)）をクリックして、[!UICONTROL  プロパティ ] レールを折りたたむか表示します。

+++

## [!UICONTROL  ドラフトとして保存]および[!UICONTROL 同期]の状態は引き続き利用できますか？

+++詳細
ユーザーインターフェイスの最新の更新により、[!UICONTROL  ドラフトとして保存]および[!UICONTROL 同期]状態は使用できなくなります。 詳しくは、*[!UICONTROL アクティビティの概要]*&#x200B;の「[ アクティビティリストにフィルターを適用する](/help/main/c-activities/activities.md#filters)」のステータスを参照してください。

+++

## アクティビティがレガシーUIまたは更新されたUIで作成または編集されたかどうかを確認するにはどうすればよいですか？

+++詳細
更新されたUIで作成または編集されたアクティビティは、ガイド付きの3段階の同じワークフローに従い、UI固有のメタデータまたはフォーマットが従来に作成されたアクティビティに含まれていない場合があります。 インターフェイスには表示されるタグやラベルはありませんが、レイアウト、構造、利用可能なオプション（強化されたターゲティング機能やプレビュー機能など）の違いにより、どのUIが使用されたかを示すことができます。 詳細な識別については、アクティビティの変更履歴を確認するか、実装ログを参照してください。

+++

## レガシーでオファーを作成する場合と更新されたUIの違いは何ですか？ 追加の属性は必要ですか？

+++詳細
[!UICONTROL  オファーライブラリ ] UIでは、すべてのオファーに一貫した属性定義が必要です。 アクティビティのみの（アドホック）オファーを作成する場合、ユーザーはオファー名も指定する必要があります。 この情報は[!UICONTROL  フォームベースのExperience Composer]に表示されるので、コードやコンテンツを確認せずにオファーを識別しやすくなります。

+++

## 更新されたUIのオファープレビューリンクはどうなりましたか？

+++詳細
[!UICONTROL  エクスペリエンスフラグメント ]のプレビューリンクは、選択したフラグメントに対応する情報アイコン（![情報アイコン ](/help/main/assets/icons/InfoOutline.svg)）をクリックすると表示される[!UICONTROL  クイック情報] ポップオーバーで利用できます。

+++

## 更新されたUIで既存のアクティビティを編集する際に、[!UICONTROL 拡張Experience Composer]を無効にする必要があります。 [!DNL Adobe]さんは、他の顧客と同様の動作を観察しましたか？

+++詳細
はい。 [!DNL Adobe Experience Cloud] [!DNL Visual Editing Helper extension]を使用する場合、[!UICONTROL Enhanced Experience Composer] （EEC）を無効にする必要がある場合があります。

詳しくは、[Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)を参照してください。

+++

## 許可リストに加える用の新しいIPの詳細を教えていただけますか？

+++詳細
許可リストに加えるできるIP アドレスについて詳しくは、次の記事を参照してください。

* **Enhanced Experience Composer （EEC）**:「[EECは、パブリック IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF)でアクセスできない内部QA URLを読み込むことはありません」の&#x200B;*Enhanced Experience Composerに関する問題のトラブルシューティング*
* **[!UICONTROL Recommendations]**: Recommendations フィード処理サーバーで使用される[IP アドレス ](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md)を参照してください。

+++

## 新しいRecommendations UIで、環境がデフォルトでステージングにリセットされますか？

+++詳細
環境は、お客様が最後に使用した環境にデフォルトで設定されます。 環境を切り替えるには、[!UICONTROL  カタログ検索] UIの右上隅にある[!UICONTROL 環境] セレクターを使用します。

![環境スイッチ ](/help/main/c-intro/assets/environmnent.png)

+++

## [!DNL Adobe Analytics]または[!DNL Customer Journey Analytics]を[!DNL Target]に接続するのはどの程度複雑ですか？

+++詳細
[!DNL Adobe Analytics] （AA）または[!DNL Customer Journey Analytics] （CJA）を[!DNL Target]と統合する場合、現在の設定に応じて、中程度から高度な作業の範囲を指定できます。 [!DNL Adobe Experience Platform]を使用していて[!DNL Platform Web SDK]を実装している場合、統合がより合理的になります。 ただし、at.jsまたはAppMeasurementを使用する従来の実装では、次のような追加の設定が必要になる場合があります。

* Target （A4T）統合[Analyticsを有効にする](/help/main/c-integrating-target-with-mac/a4t/a4t.md)
* [[!DNL Target]  レポートを [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)に統合します。
* レポートスイートとデータビューのマッピング
* 一貫したID解決（ECID）の確保
* データ収集とアトリビューション設定の検証

+++
