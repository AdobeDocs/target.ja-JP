---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8f7cdf94438763679273b3631e45b1b41899cda5
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 21%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025 年 8 月 18 日**

>[!NOTE]
>
>* リリース日、機能などの情報は、予告なく変更されることがあります。この記事の情報は、特にリリース前に頻繁に更新されます。
>
>* 最新のリリースに関する情報を確認するには、[Target リリースノート ](release-notes.md) を参照してください。
>
>* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target Standard/Premium] 25.8.3 （2025 年 8 月 21 日（PT））

このリリースには、次の更新および修正が含まれています。

**Recommendations**

+++詳細を表示
* **Recs UI で、カスタム条件の CSV ダウンロードが 404 エラーを返す問題を修正しました**：顧客がアクティビティ作成プロセスでカスタム条件の CSV をダウンロードできない問題を修正しました。 （TGT-51966）
* **[!UICONTROL Catalog Search]** での一貫性のない画像読み込みを修正：のサムネールと画像がアクティビティ作成プロセスで一貫して読み込まれない問題を修正しました [!UICONTROL  Catalog Search]。 「サムネール URL」列が表示されず、ナビゲーションまたは検索アクションの後に一部の製品画像が部分的に読み込まれたか、まったく読み込まれなかった場合に、画像が表示されませんでした。 （TGT-52778）
* **重複したエクスペリエンスのレコメンデーションを編集すると、元のエクスペリエンスに影響を与える問題を修正しました**：顧客が、重複したエクスペリエンスのレコメンデーションを変更すると元のエクスペリエンスが意図せず変更されたと報告しました。 具体的には、アクティビティ作成プロセスでエクスペリエンス B を複製し、そのデザインや条件を編集した後、別々のエンティティであるにもかかわらず、元のエクスペリエンス B に同じ変更が反映されました。 （TGT-53369）
* **重複したエクスペリエンスへの変更が、アクティビティの元のエクスペリエンスに意図せず影響を与える問題を修正しました。** アクティビティ内のエクスペリエンスを複製し、新しいオーディエンスを割り当てると、重複したエクスペリエンスのデザインまたは条件に加えられた変更が元のエクスペリエンスにも反映されるという問題を顧客が報告しました。 これは、元のバージョンに直接編集が加えられていない場合でも発生し、同じアクティビティ内で独立したバリエーションを作成する機能に影響を与えていました。 （TGT-53361）
* **フ [!UICONTROL Recommendation Catalog] ールドで完全な製品属性データが断続的に表示されない問題を修正しました**：更新された [!DNL Recommendations] UI で、フィードにデータが存在しているにもかかわらず、メッセージなどの特定の製品属性がカタログ検索結果に一貫して表示されない問題が発生しました。 この問題を解決するには、欠落している値を取得するために列表示を手動で再設定する必要がありました。 （TGT-52769）
+++

**[!UICONTROL Visual Experience Composer]（VEC）**

+++詳細を表示
* **アクティビティ作成プロセスで、AP アクティビティの [!UICONTROL Targeting] ステップへの進行がブロックされる問題を修正しました**：アクティビティ作成プロセスで、2 つの場所を追加しない限り、顧客が [!UICONTROL Targeting] （AP）アクティビティの [!UICONTROL Automated Personalization] ステップに進むことができない問題を修正しました。 この動作は、複数のオファーを含む 1 つの場所で十分だった以前のエクスペリエンスとは異なります。 要件が修正され、お客様は AP ワークフローの一部として引き続き単一場所の設定を使用できるようになりました。 （TGT-53426）

+++

**[!UICONTROL Workspaces]**

+++詳細を表示
* **1 つのワークスペースに制限されている顧客が他のワークスペースのアクティビティを表示できる問題を修正しました**:1 つのワークスペースに制限されたアクセス権を持つお客様が、アクティビティ作成プロセスで [!UICONTROL All Workspaces] を選択する際に、すべてのワークスペースにわたって予期せずアクティビティを表示できていました。 この表示によって、他のワークスペースのライブアクティビティに意図しない変更が加えられるリスクが生じ、web サイトのパフォーマンスに影響を与える可能性があります。 （TGT-53101）
* **顧客がアクセス権を持たずに [!UICONTROL Default Workspace] からアクティビティを表示できる問題を修正しました。** ステージングワークスペースへのアクセス権を持つ顧客が、アクティビティ作成プロセスを使用して [!UICONTROL Default Workspace] からアクティビティを表示できました。 これは、バックエンドの設定とアクセス権限が正しいにもかかわらず、発生していました。 （TGT-53297）

+++

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [ リリースノート：Adobe Target Platform Experience Web SDK] （https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n） | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
