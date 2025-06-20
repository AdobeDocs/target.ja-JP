---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 71f88ad173599b3a582a1d2c261ba8a562cf734a
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 28%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025 年 6 月 20 日（PT）**

>[!NOTE]
>
>* リリース日、機能などの情報は、予告なく変更されることがあります。
>
>* 最新のリリースに関する情報を確認するには、[Target リリースノート ](release-notes.md) を参照してください。
>
>* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target Standard/Premium] 25.6.3（2025年6月20日（PT））

このリリースには、次の修正および更新が含まれています。

* レガシー VEC で使用可能な機能と連携するために、更新された [!UICONTROL Visual Experience Composer] （VEC） UI に [!UICONTROL Rearrange] オプションを追加しました。 （TGT-46957）
* あるワークスペースから別のワークスペースにアクティビティをコピーすると、「null であってはならない」や「エラーが発生しました」などのエラーがトリガーされる問題を修正しました。 （TGT-52474）
* 特定のアクティビティに対して [!UICONTROL Automated Segments] および [!UICONTROL Important Attributes] レポートが生成されない問題を修正しました。 （TGT-52904）
* 更新された VEC で、[!UICONTROL Automated Personalization] （AP）アクティビティのデフォルトのコンテンツ処理がレガシー UI と一致しなかった問題を修正しました。 グループが明示的に追加されていない場合、システムは「デフォルトコンテンツ」という名前のデフォルト `optionGroup` を `optionGroupLocalId = 0` で自動的に追加するようになりました。 このグループにはデフォルトのオプション（例：`optionLocalId: 0`）が含まれています。 デフォルトコンテンツが削除されると、対応するオプショングループも削除されます。 （TGT-52651）
* [!UICONTROL Multivariate Test] （MVT）アクティビティで、以前に削除したエクスペリエンスの `experienceLocalId` を再利用することが誤って禁止されていた問題を修正しました。 （TGT-52672）
* スラッシュ（/）などの無効な文字が原因で、アクティビティの場所の URL にクエリパラメーターを表示できなかった問題を修正しました。 （TNT52845）
* バックエンド API を介した [!DNL A/B Test] アクティビティの更新の検証エラーメッセージを改善しました。 重複した場所名が存在する場合、`locations.selectors` に「重複した名前は許可されません」とメッセージが明確に表示されるようになりました。 （TGT-52589）
* リクエストペイロードで認識されないプロパティが原因で、ライブ [!UICONTROL Recommendations] アクティビティを更新する際に発生していたエラーを修正しました。 「無効な JSON」が正しく処理されるようになりました。 認識できないプロパティ名」エラーが発生しました。 （TGT-52723）
* [!DNL Recommendations] デザインを作成できない問題を修正しました。 [!UICONTROL Create] をクリックすると、「スクリプト内でエンティティ変数が少なくとも 1 つ使用されている必要があります」というメッセージがトリガーされます。 （TGT-52395 および TGT-52899）
* [!DNL Recommendations] デザインを変更せずに再保存するとブロックされる問題を修正しました。 （TGT-52879）
* [!UICONTROL Recommendations] アクティビティを保存する際に「400 無効なリクエスト」エラーが発生するバックエンドの検証エラーを修正しました。 （TGT-52716）
* [!UICONTROL Form-Based Experience Composer] で、「[!UICONTROL Location]」ドロップダウン内の特殊文字を含む mbox にカーソルを合わせると、エディターが空白になり、「Element で「querySelector」を実行できませんでした」トリガーされる問題を修正しました。 エラーが表示されます。（TGT-52717）
* 新しい「PARTIALLY_IMPORTED」インジケーターにより、フィードステータスの精度が向上しました。 以前は、ファイル内のすべての行が読み込まれていない場合でも、フィードは「成功」とマークされていましたが、これは誤解を招くものでした。 （TGT-52892）
* AP V2 への移行後に、`/admin/rest/ui/v1/campaigns` への特定の API 呼び出しでクライアントサイドエラー（HTTP 4xx）が返されるエラーを修正しました。 （TGT-52721）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [ リリースノート：Adobe Target Platform Experience Web SDK] （https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n） | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
