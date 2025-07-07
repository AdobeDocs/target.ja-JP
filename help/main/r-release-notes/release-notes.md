---
keywords: リリースノート；新機能；リリース；アップデート；アップデート；リリース；機能強化；機能強化；修正；バグ修正；アップデート、現在のアップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 34693e5c94328b5f1ad1d692d6a986cadb6349c4
workflow-type: tm+mt
source-wordcount: '3112'
ht-degree: 12%

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

## [!DNL Target Standard/Premium] 25.6.4（2025年6月27日（PT））

このリリースには、次の修正および更新が含まれています。

* レガシー VEC で使用可能な機能と連携するために、更新された [!UICONTROL Rearrange] （VEC） UI に [!UICONTROL Visual Experience Composer] オプションを追加しました。 （TGT-46957 および TGT-52876）
* [!UICONTROL A/B Test] アクティビティでバリアントエクスペリエンス（エクスペリエンス B など）に加えた変更が保持されない問題を修正しました。 エクスペリエンスを切り替えると、バリアントに対する変更が消えます。 この問題は、コントロールエクスペリエンスには影響しませんでした。 （TGT-52664）
* 特定の顧客がアクティビティを作成または保存できない一方で、他の顧客が問題なく同じアクションを実行できる問題を修正しました。 複数のアカウントで問題が矛盾していました。（TGT-52842）
* 更新された VEC で、ユーザーが [!UICONTROL Page Load event] （レガシー UI に存在していた機能）に変更を移動できなかった問題を修正しました。 （TGT-52617）
* 更新された UI で、変更を作成する際に [!UICONTROL page load] で [!DNL Target] イベントが表示されない問題を修正しました。更新はビューにのみ適用されます。 （TGT-52604）
* 一部のアクティビティの変更が、更新された VEC に正しく表示されない問題を修正しました。 （TGT-52818）
* [!UICONTROL Automated Personalization] （AP）アクティビティのレポートデータを取得する際に発生していたヌルポインター例外を修正しました。 （TGT-52362）
* [!UICONTROL Automated Personalization] （AP）アクティビティで、オファーレベルの詳細が.CSV ファイルに表示されない問題を修正しました。 （TGT-52675）
* 更新された VEC で変更を適用すると、期待される [!UICONTROL Experience Fragment] を含め、変更内容が最初は正しく表示される問題を修正しました。 ただし、エクスペリエンスを切り替えたり、追加の編集を行ったりすると、セレクターの問題が原因で一部の変更が適用されません。 （TGT-52679）
* 既存のアクティビティを複製して新しいアクティビティを作成した場合、複製されたアクティビティの QA リンクで、元のアクティビティのページ URL が誤って保持される問題を修正しました。 （TGT-52775）
* 更新された VEC で [!UICONTROL On-device Decisioning] が意図せず使用できない問題を修正しました。 （TGT-52371）
* 製品 [!DNL Recommendations] ーディエンスアクティビティを編集できない問題を修正しました。 Target UI を使用して VEC にアクセスしようとすると、[!UICONTROL Overview] ページにエラーが表示され、編集できませんでした。 （TGT-52823）
* エクスペリエンス名が 50 文字を超えた場合に、[!DNL Recommendations] アクティビティを保存できない問題を修正しました。 （TGT-52619）
* 新しい UI で条件を変更した後、顧客が Recommendations アクティビティを保存できない問題を修正しました。 この問題は権限に関連していると考えられ、類似の役割を持つすべてのユーザーに影響するわけではありません。 （TGT-52816）
* [!UICONTROL Editor] の役割を持つユーザーが [!DNL Recommendations] アクティビティを編集できない問題を修正しました。 デザインを変更し、アクティビティを保存しようとすると、ユーザーが関連するワークスペースで既にその役割を持っている場合でも、「[editor]」権限が必要であるという 403 Forbidden エラーが発生しました。 （TGT-52836）

## [!DNL Target Standard/Premium] 25.6.3（2025年6月20日（PT））

このリリースには、次の修正および更新が含まれています。

* あるワークスペースから別のワークスペースにアクティビティをコピーすると、「null であってはならない」や「エラーが発生しました」などのエラーがトリガーされる問題を修正しました。 （TGT-52474）
* 特定のアクティビティに対して [!UICONTROL Automated Segments] および [!UICONTROL Important Attributes] レポートが生成されない問題を修正しました。 （TGT-52904）
* 更新された VEC で、[!UICONTROL Automated Personalization] （AP）アクティビティのデフォルトのコンテンツ処理がレガシー UI と一致しなかった問題を修正しました。 グループが明示的に追加されていない場合、システムは「デフォルトコンテンツ」という名前のデフォルト `optionGroup` を `optionGroupLocalId = 0` で自動的に追加するようになりました。 このグループにはデフォルトのオプション（例：`optionLocalId: 0`）が含まれています。 デフォルトコンテンツが削除されると、対応するオプショングループも削除されます。 （TGT-52651）
* [!UICONTROL Multivariate Test] （MVT）アクティビティで、以前に削除したエクスペリエンスの `experienceLocalId` を再利用することが誤って禁止されていた問題を修正しました。 （TGT-52672）
* エクスペリエンスフラグメントを含むアクティビティをコピーまたは編集できない問題を修正しました。 これが次のエラーをトリガーしました：`Enum "AemOfferType" cannot represent value: "html"`。 （TGT-52635）
* スラッシュ（/）などの無効な文字が原因で、アクティビティの場所の URL にクエリパラメーターを表示できなかった問題を修正しました。 （TNT52845）
* バックエンド API を介した [!DNL A/B Test] アクティビティの更新の検証エラーメッセージを改善しました。 重複した場所名が存在する場合、`locations.selectors` に「重複した名前は許可されません」とメッセージが明確に表示されるようになりました。 （TGT-52589）
* リクエストペイロードで認識されないプロパティが原因で、ライブ [!UICONTROL Recommendations] アクティビティを更新する際に発生していたエラーを修正しました。 「無効な JSON」が正しく処理されるようになりました。 認識できないプロパティ名」エラーが発生しました。 （TGT-52723）
* [!DNL Recommendations] デザインを作成できない問題を修正しました。 [!UICONTROL Create] をクリックすると、「スクリプト内でエンティティ変数が少なくとも 1 つ使用されている必要があります」というメッセージがトリガーされます。 （TGT-52395 および TGT-52899）
* [!DNL Recommendations] デザインを変更せずに再保存するとブロックされる問題を修正しました。 （TGT-52879）
* [!UICONTROL Recommendations] アクティビティを保存する際に「400 無効なリクエスト」エラーが発生するバックエンドの検証エラーを修正しました。 （TGT-52716）
* [!UICONTROL Form-Based Experience Composer] で、「[!UICONTROL Location]」ドロップダウン内の特殊文字を含む mbox にカーソルを合わせると、エディターが空白になり、「Element で「querySelector」を実行できませんでした」トリガーされる問題を修正しました。 エラーが表示されます。（TGT-52717）
* 新しい「PARTIALLY_IMPORTED」インジケーターにより、フィードステータスの精度が向上しました。 以前は、ファイル内のすべての行が読み込まれていない場合でも、フィードは「成功」とマークされていましたが、これは誤解を招くものでした。 （TGT-52892）
* AP V2 への移行後に、`/admin/rest/ui/v1/campaigns` への特定の API 呼び出しでクライアントサイドエラー（HTTP 4xx）が返されるエラーを修正しました。 （TGT-52721）

## [!DNL Target Standard/Premium] 25.6.2（2025年6月12日（PT））

このリリースには、次の修正および更新が含まれています。

* 更新された [ UI と ](/help/main/c-intro/updated-ui-faq.md) （VEC）に関するよくある質問に対処するため、[!DNL Target] 新しい FAQ 記事 [!UICONTROL Visual Experience Composer] を追加しました。
* [!UICONTROL URL - does not contain] の「[!UICONTROL Page Delivery]」ルールが機能せず、ブロックする必要があった場合でもコンテンツを表示できる問題を修正しました。 （TGT-52754）
* 「ページ URL の重複は許可され [!UICONTROL Page Delivery] せん。 （TGT-52765）
* エクスペリエンスフラグメントを含む URL[!UICONTROL Page Delivery] オーディエンスが#で誤って追加されて作成される問題を修正しました。 （TGT-52786）
* [!UICONTROL Goals and Settings] ページでアクティビティをコピーし、設定を編集すると、[!DNL Target] UI が応答しなくなる問題を修正しました。 （TGT-52797）
* 更新された [!UICONTROL Visual Experience Composer] （VEC）で、[!UICONTROL A/B Test] アクティビティ内の追加のページを同じ URL に誤ってリダイレクトしていた問題を修正しました。 （TGT-51838）
* アクティビティを編集する際に、[!UICONTROL Goals and Settings] ページの指標に対する変更が保存されない問題を修正しました。 （TGT-52799）
* Web エディターの読み込み中に新しいエクスペリエンスを追加すると、新しいエクスペリエンスで以前のエクスペリエンスのコンテンツが重複する問題を修正しました。 （TGT-51397）
* 従来の Target UI で以前に使用できた機能である、`<head>` タグ外でカスタムコードを使用する機能を復元しました。 （TGT-52304 および TGT-52300）
* アクティビティの作成時にデフォルトワークスペースを選択する際の、不要な検証を削除しました。 必須プロパティの検証は、デフォルトのワークスペースには適用されませんが、デフォルト以外のワークスペースには適用されます。 （TGT-52449）
* 更新された [!UICONTROL Visual Experience Composer] （VEC）で、`triggerView()` 呼び出しが検出されない問題を修正しました。 （TGT-52575）
* 更新された [!UICONTROL Visual Experience Composer] （VEC）で、ユーザーが [!UICONTROL Single Page Application] （SPA）ビューに変更を追加できなかった問題を修正しました。 （TGT-52556）
* 更新された [!DNL Target] UI で、顧客がオファーの詳細を表示できない問題を修正しました。 （TGT-52607）
* [!UICONTROL Offers Library] ージのオファーに対して行った更新が、更新された [!UICONTROL Visual Experience Composer] （VEC）に反映されない問題を修正しました。 （TGT-52637）
* アクティビティの作成時にオファーのセクションが正しく表示されない問題を修正しました。 （TGT-52773）
* `optionLocalIds` で参照されているすべての `optionGroups` がオプション配列に存在することを確認するための検証を追加しました。 無効な参照は、アクティビティの作成中に自動的に削除されます。 （TGT-52687）
* 新しいオファーを追加した後、レポートのグループと除外が保持されない問題を修正しました。 （TGT-52728）
* [!UICONTROL Activity QA] ボタンのないアクティビティで空のオプションセレクターが表示される問題を修正しました。 （TGT-52733）
* QA リンクでコンテンツを適切にレンダリングできない問題を修正しました。 （TGT-52718）
* 要素をエクスペリエンスフラグメントに置き換えても、QA 環境に変更が正しく反映されない問題を修正しました。 （TGT-52762）
* ユーザーがエクスペリエンスフラグメントを追加しようとすると、「無効な入力」エラーが発生する、更新された [!UICONTROL Visual Experience Composer] （VEC）の問題を修正しました。 （TGT-52701）
* 更新された [!UICONTROL Visual Experience Composer] （VEC）でオーディエンスターゲティングを編集すると、「オーディエンスを編集」モーダルが空に表示される問題を修正しました。 （TGT-52749）
* 選択したワークスペースでエンティティにアクセスできない場合に、ユーザーに通知するメッセージを追加しました。 （TGT-52767）
* UI で、条件に環境 ID を手動で割り当てることができない問題を修正しました。 代わりに、[!UICONTROL Product Catalog Search] ホストグループの ID がデフォルトで使用されます。 この修正により、条件の変更がデフォルトだけでなく、すべての環境に適用されるようになりました。 （TGT-52817）
* レコメンデーションを使用する [!UICONTROL Download Recommendations data] （XT）アクティビティで「[!UICONTROL Experience Targeting]」オプションが見つからない問題を修正しました。 （TGT-52730 および TGT-52756）

## [!DNL Target Standard/Premium] 25.6.1（2025年6月6日（PT））

このリリースには、次の修正および更新が含まれています。

* QA リンクで、関連するアクティビティに対して正しいエクスペリエンスが提供されなかった問題を修正しました。 （TGT-52163 および TGT-52790）
* QA リンクで、関連するオーディエンス ID が欠落していた問題を修正しました。 （TGT-52722）
* 設定されたページ配信 URL 条件が正確に満たされた場合にのみエクスペリエンスが配信される問題を修正しました。 （TGT-52696）
* お客様が [!DNL Recommendations] デザインテンプレートを作成できない問題を修正しました。 テンプレートを作成しようとすると、「スクリプト内でエンティティ変数が少なくとも 1 つ使用されている必要があります」というエラーがトリガーされました。 （TGT-52395）
* Velocity 配列を使用して [!DNL Recommendations] デザインを保存できない問題を修正しました。 「スクリプト内で使用されるエンティティ変数が 1 つ以上あるはずです」というエラーメッセージが誤ってトリガーされていました。 （TGT-52734）
* 内部 web ページのページを読み込めない場合に、[!UICONTROL Visual Experience Composer] （VEC）で変更にアクセスできない問題を修正しました。 （TGT-52488 &amp;TGT-52470）
* VEC の小さい画面サイズで [!UICONTROL Modifications] パネルが表示されない問題を修正しました。 （TGT-52470）
* 更新された VEC で、[!UICONTROL Browse] モードから [!UICONTROL Design] モードに切り替えるとコンソールエラーが発生し、それ以上のインタラクションが妨げられる問題を修正しました。 （TGT-52532）
* VEC で、特定の要素をクリックすると意図せずサイズが拡大される問題を修正しました。 （TGT-52497）
* VEC で特定のページ要素の読み込みまたは認識に失敗し、ボタンやバナーの選択などのインタラクションが発生したり、アクティビティの正確なイベント追跡が中断されたりする問題を修正しました。 （TGT-52663）
* [!UICONTROL Automated Personalization] （AP）アクティビティで、お客様がオファーを削除できない問題を修正しました。 （TGT-52690）
* 複数ページアクティビティでアクティビティの選定動作に一貫性がなかった問題を修正しました。 （TGT-52694）
* アクティビティの [!UICONTROL Overview] ページに [!UICONTROL Activity Location] の無効な URL が表示される問題を修正しました。 （TGT-52695）
* 更新された [!DNL Target] UI で、アクティビティの場所に重複するエントリが表示される問題を修正しました。 （TGT-52693）
* `getAudiencesV3` エラーをトリガーして、顧客がアクティビティを編集またはコピーできなかった問題を修正しました。 （TGT-52709）
* [!UICONTROL Experience Fragments] またはHTML オファーをアクティビティに追加する際に、「無効なペイロードです」エラーが発生する問題を修正しました。 （TGT-52779 および TGT-52773）
* 更新された [!DNL Target] UI で、無効な入力エラーが原因で E[!UICONTROL xperience Fragments] が正しく表示されなかった問題を修正しました。 （TGT-52701）
* 無効なユーザーエラーが原因で、お客様が [!UICONTROL Form-based Experience Composer] でアクティビティを編集できない問題を修正しました。 （TGT-52470）
* 以前の翻訳で基本多言語平面外の文字が使用されていた韓国語のローカライゼーションの問題を修正しました。 更新された翻訳では、意図した意味を正確に伝える適切な文字を使用しています。 （TGT-52508 および TGT-52509）
* 韓国語ローカライゼーションの問題を修正しました。アクティビティの開始日と終了日を選択する際に、「日付」の翻訳が一貫していませんでした。 （TGT-52510）

## [!DNL Target] UI バージョンの切り替えの廃止（2025 年 5 月 23 日（PT）） {#toggle}

>[!IMPORTANT]
>
>[!DNL Target] チームは、UI バージョンの切り替えの廃止のタイムラインを調整しました。 詳しくは、[ 更新： [!DNL Target] UI バージョンの切り替えの廃止（2025 年 6 月 17 日（PT）） ](#revised) を参照してください。

新しい [!DNL Target] ユーザーインターフェイスのロールアウトは、**2025 年 5 月 27 日（PT）** までに完了します。 その時点で、すべてのお客様が最新の UI バージョンにアクセスできます。

**2025 年 6 月 22 日** 以降、UI バージョンの切り替えが削除されます。 すべてのユーザーは新しいインターフェイスに永続的に移行しますが、以前のバージョンに戻すオプションはありません。

>[!NOTE]
>
>特殊なケースで、6 月 22 日以降に切り替えスイッチを保持する必要があるお客様は、Adobe カスタマーケアにお問い合わせください。

### UI バージョンの切り替えに関する重要な情報

切り替えボタンを使用して、更新された [!DNL Target] UI とレガシーバージョンを切り替えることができる一時機能を提供しています。 このオプションは、UI ロールアウトの最終フェーズでのみ使用できます。

![Target UI のバージョン切り替え ](/help/main/r-release-notes/assets/toggle.png)

ロールアウトが完了すると、切り替えが削除され、すべてのユーザーは更新済み UI に永続的に移行します **2025 年 6 月 22 日（PT）**。 この機能は間もなく廃止される予定なので、Adobeでは、事前に計画することをお勧めします。

### UI の切り替え動作の制限

* **新しいアクティビティの表示**：レガシー UI に切り替えた場合、更新された UI で作成されたアクティビティは表示されません。
* **既存のアクティビティの編集**：更新された UI の使用中に既存のアクティビティ（元々はレガシー UI で作成したもの）に加えられた変更が、web サイトに公開されます。 ただし、これらの更新は、戻してもレガシー UI には表示されません。レガシー UI から最後に作成された更新のみが表示されます。
* **アクティビティ詳細の一貫性**：使用する UI に関係なく、最新の変更がライブ web サイトに反映されます。 ただし、レガシー UI に表示されるのは、そのバージョン内で行われた最新の変更のみです。 更新された UI で編集されたアクティビティが、レガシー UI で表示されるものとは異なる表示になる場合は、混乱を招く可能性があります。

### 更新された UI に関する詳細情報

* [[!DNL Target Standard/Premium] 25.2.1 （2025 年 2 月 17 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2):[!DNL Target]、[!UICONTROL Activities] および [!UICONTROL Recommendations] （VEC）の [!UICONTROL Visual Experience Composer] の主な UI の変更点の概要を説明します。

* [[!DNL Target Standard/Premium] 25.1.1 （2025 年 1 月 9 日（PT））リリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1):[!DNL Target] の [!UICONTROL Offers Library] での主な UI の変更点の概要を説明します。

* [ [!DNL Target] UI について ](/help/main/c-intro/understand-the-target-ui.md):[!DNL Target] に慣れるのに役立つ概要と、より詳細な情報と手順を説明するリンクを提供します。

* [[!UICONTROL Visual Experience Composer] の変更点 ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015 年 2 月 17 日（PT））では、更新された [!UICONTROL Visual Experience Composer] （VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新バージョンの違いについて説明します。

* [[!UICONTROL Visual Experience Composer] options](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新された VEC UI とそのオプションについて説明します。

* [[!DNL Target] UI 更新 FAQ](/help/main/c-intro/updated-ui-faq.md)：この FAQ は、ナビゲーションの変更、機能の場所、一時的な UI バージョンの切り替えスイッチの廃止など、新しい [!DNL Target] UI と [!UICONTROL Visual Experience Composer] （VEC）に関するよくある質問に対応しています。 マーケター、開発者、管理者を問わず、この FAQ はスムーズに移行し、更新された UI を最大限に活用するのに役立ちます。

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
