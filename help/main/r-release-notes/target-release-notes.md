---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2812132c2720f54fa7bee2b0a5e16623362fdc33
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 34%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025 年 7 月 10 日**

>[!NOTE]
>
>* リリース日、機能などの情報は、予告なく変更されることがあります。
>
>* 最新のリリースに関する情報を確認するには、[Target リリースノート ](release-notes.md) を参照してください。
>
>* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target Standard/Premium] 25.7.3（2025年7月24日（PT））

最近の問題（主に複雑な顧客のカスタマイズに関連）が特定されたので、このリリースには次の修正と更新が含まれています。

**アクティビティ**

+++詳細を見る
* ビルダークラスの `buildViews` メソッドが、割り当てられた最も高い `viewMaxLocalId` ではなく、ビューの合計数に誤って `viewLocalId` を設定する問題を修正しました。 （TGT-53207）

+++

**フォームベースの Experience Composer**

+++詳細を見る
* [!UICONTROL Form-Based Experience Composer] で、**[!UICONTROL Manage Content]** （AP）アクティビティを作成または編集する際に、コンテン ![ アイコン（](/help/main/assets/icons/Experience.svg) コンテンツを管理アイコン [!UICONTROL Automated Personalization]）をクリックした後にエディターがクラッシュする問題を修正しました。 （TGT-53047）

+++

**Recommendations**

+++詳細を見る
* リストの下部までスクロール [!UICONTROL Catalog Search] ると、従来の UI と一貫した動作が復元され、追加の結果を読み込めない問題を修正しました。 （TGT-53088）
* 更新された [!UICONTROL Number of Products] UI の [!UICONTROL Collections] ページに [!DNL Target] 列が表示されない問題を修正しました。 列が正しく表示され、期待される機能が復元されるようになりました。 （TGT-53168）
* ルールに従って [!UICONTROL Collection] ルールが適切にフィルタリングされない問題を修正しました。 （TGT-53254）
* [!UICONTROL Criteria Details] ダイアログボックスからの項目の削除がブロックされる問題を修正しました。 （TGT-53245）
* 名前のない製品を開いたり操作したりできない問題を修正しました。 この問題は、名前のない結果を返した環境を選択すると、製品の詳細にアクセスできなくなる場合に発生しました。 （TGT-53007）
* 特定の製品を選択すると [!UICONTROL Catalog Search] ページがクラッシュして空白の画面が表示される問題を修正しました。 （TGT-53087）

+++

**Visual Experience Composer（VEC）**

+++詳細を見る

* VEC で、ビューに変更を適用すると重複が発生し、「無効なユーザー入力」エラーがトリガーされる問題を修正しました。 （TGT-52886）
* VEC で画像オファーを設定する際の、[!UICONTROL Undo] および [!UICONTROL Insert Before] オプションの [!UICONTROL Insert After] 機能の問題を修正しました。

  以前は、特にレガシー [!UICONTROL Insert Before] UI で作成されたアクティビティで、画像オファーに対する [!UICONTROL Insert After] や [!DNL Target] のアクションの取り消しによって、動作に一貫性がなかったり、変更を適切に元に戻せませんでした。 この問題は解決され、これらの変更に対して取り消しアクションが確実に機能するようになりました。 （TGT-52809）

+++

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [ リリースノート：Adobe Target Platform Experience Web SDK] （https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n） | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
