---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fda279c909e2bb35e919d1bb4f4b611401a367cf
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 17%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025 年 8 月 29 日**

>[!NOTE]
>
>* リリース日、機能などの情報は、予告なく変更されることがあります。この記事の情報は、特にリリース前に頻繁に更新されます。
>
>* 最新のリリースに関する情報を確認するには、[Target リリースノート ](release-notes.md) を参照してください。
>
>* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target Standard/Premium] 25.8.4 （2025 年 9 月 1 日（PT））

このリリースには、次の更新および修正が含まれています。

**[!UICONTROL Activities]**

+++詳細を表示
* **顧客は、[!UICONTROL Activity Overview]** からアクティビティまたはドキュメントの名前をコピーできませんでした。以前は、顧客は、更新されたアクティビティ作成プロセスの [!UICONTROL Activity Overview] から、アクティビティまたは関連するオファー/ドキュメントの名前を直接コピーできませんでした。 この制限は、特に画面が小さい場合、ユーザビリティに影響を与えました。 お客様は、回避策を使用せずに、アクティビティ名とドキュメント名の両方を簡単にコピーできるようになりました。 （TGT-51850）
* **アクティビティの作成時に、キュレートされた [!DNL Target] 顧客データを事前に取り込む**:[!DNL Target] 顧客からのレポート、コンテンツ、スクリーンショットを積極的に収集できるようにすることで、アクティビティ作成プロセスを改善しました。 この機能強化により、既存のユースケースで特定されたデータのギャップに対処し、アクティビティと実験の設定時により正確なインサイトを確保できるようになります。 （TGT-52415）
* **[!UICONTROL Reports] セクションの AP アクティビティでモデルに対応したデータが取得されませんでした**:[!UICONTROL Reports] セクションでAutomated Personalization（AP）アクティビティを表示しているお客様は、レポートグループおよびオファーレベルでモデルに対応した指標を表示できませんでした。 この問題は、モデル対応データがバックエンドから正しく取得されていないために発生しました。 機能が復元され、モデル対応データが期待どおりに表示されます。 （TGT-53600 および TGT-53601）

+++

**[!UICONTROL Recommendations]**

+++詳細を表示
* **[!UICONTROL View Collection] ダイアログに製品リストが表示されませんでした：** 以前は、顧客が「[!UICONTROL Recommendations]」タブでコレクションを表示する際に製品リストが表示されませんでした。 [!UICONTROL View Collection] ダイアログに関連する製品が正しく表示され、更新された Recommendations UI の透明性と操作性が向上しました。 （TGT-50531）
* **詳細検索で大文字と小文字を区別するフィルタリングが発生す [!UICONTROL Product Catalog Search] 問題を修正しました**:[!UICONTROL Product Catalog Search] ページの詳細検索フィルタリングでは、バックエンドとGraphQLの両方のサービスの動作に合わせて、大文字と小文字の区別が正しく無視されるようになりました。 この更新により、テキストの大文字と小文字を区別せずに、一貫した正確な提案結果が顧客に提供されます。 （TGT-53585）
* **更新された [!UICONTROL Product Catalog Search] UI の詳細検索では、候補が表示されませんでした**：更新された [!UICONTROL Product Catalog Search] UI の詳細検索機能を使用するお客様は、候補が表示されないので、正確な値を正しいスペルで入力する必要がありました。 このため、効率よく商品を見つけることが難しくなっていました。 詳細検索入力時に候補が期待どおりに表示されるようになりました。 （TGT-52008）

+++

**[!UICONTROL Reports]**

+++詳細を表示
* **無効なオーディエンス名のエラーが原因で、デスクトップオーディエンスのレポートの読み込みに失敗しました**：お客様が、アクティビティ作成プロセスで 1 つのオーディエンスのレポートを表示しようとしたときに、GraphQL エラーが発生しました。 システムが「無効なオーディエンス名：XXXXX」メッセージを返し、レポートデータにアクセスできませんでした。 デスクトップオーディエンスのレポートが正しく読み込まれるようになりました。 （TGT-53371）
* **レポートページでオーディエンスを切り替えると、Target UI でエラーが発生しました**：更新された Target UI の担当者 orts セクションで特定のオーディエンスを選択する際に、お客様がエラーが発生しました。 この問題は、バックエンドのGraphQL呼び出しでの無効なオーディエンス処理が原因で、予期しないエラーとデータの欠落が発生したことが原因でした。 この問題が解決され、データが利用できない場合でも、デスクトップオーディエンスがエラーなく読み込まれるようになりました。 （TGT-53370）
+++

**[!UICONTROL Visual Experience Composer]（VEC）**

+++詳細を表示
* **[!UICONTROL Enhanced Experience Composer] （EEC）を使用して「Accept Cookies」をクリックする際に、関数が見つからず失敗しました**:EEC を使用して Cookie を受け入れようとすると、コンソールエラーが発生することが報告されています：`handleclickAcceptAllButton is not defined`。 cookie 受け入れ機能が期待どおりに動作するようになり、更新された UI でアクティビティの作成時によりスムーズなエクスペリエンスが確保されます。 （TGT-52794）
* **新しい EEC UI で、以前はレガシー UI でサポートされていた特定のページを読み込めませんでした**：お客様は、サイトに iframe バスティングコードが存在するにもかかわらず、新しい EEC でレガシー UI でアクセスできる一部のページを読み込めないと報告しました。 更新されたアクティビティ作成プロセスでは、これらのページの読み込みをサポートするようになり、アクティビティ作成ワークフローの互換性が復元されます。 （TGT-53061）
* **エクスペリエンスを編集すると、VEC に空白の白画面が表示されていました**：更新された VEC でエクスペリエンスを編集しようとすると、特定のテナントの顧客から VEC 画面が空白になったとレポートされました。 この問題は、新しく作成されたアクティビティと古いアクティビティの両方に影響を与え、ワークフローの継続性を妨げました。 VEC が正しく読み込まれるようになり、お客様は中断することなくエクスペリエンスを編集できます。 （TGT-53547）
* **特定のアクティビティを読み込む際、VEC がクラッシュし、空白の画面が表示されました**：特定のテナントからの顧客から、VEC が特定のアクティビティを読み込めなかったことが報告されました。 エクスペリエンスエディターがクラッシュして空白の画面が表示される前に、「初期変更の適用」で動かなくなっていた。 コンソールエラーは、未定義のプロパティの読み取りに失敗したことを示しました。 エディターは、更新された VEC でエラーなく、影響を受けるアクティビティを読み込むようになりました。 （TGT-53548）

+++

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [ リリースノート：Adobe Target Platform Experience Web SDK] （https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n） | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
