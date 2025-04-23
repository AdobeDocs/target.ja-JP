---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ad82d108adc6f5c76b2104f40fb0bb2c66e98a2b
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 33%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025年4月23日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target Standard/Premium] 25.4.5 （2025 年 4 月 24 日（PT））

このリリースには、次の修正および更新が含まれています。

* [!DNL Recommendations] アクティビティをアクティブ化した後、顧客の web サイトにレコメンデーションが表示されない問題を修正しました。 （TGT-52164）
* オプション `OptionLocalIDs` 変更されていないときに、が誤って増分されることはなくなりました。 （TGT-52187）
* ダウンロードしたレポートファイルで、レポート UI に存在するデータが正しく表示されるようになりました。 （TGT-52068）
* ページ配信ルールを追加した後、バッチ操作が失敗しなくなりました。 （TGT-52097）
* [!DNL Target] が web サイトの URL からすべてのクエリパラメーターをトリミングする問題を修正しました。 （TGT-52100）
* 従来の Target UI と更新された Target UI の両方で、お客様がアクティビティを作成できなかったコンソールエラーを解決しました。 （TGT-52181）
* 顧客が新しいページを追加できず、無効なユーザー入力エラーが発生する問題を修正しました。 （TGT-52258）
* ページを追加してから「[!UICONTROL Experiences]」タブに戻ると変更が消える問題を修正しました。 （TGT-52264）
* 顧客が [!UICONTROL Experience Targeting] （XT）アクティビティのオーディエンスを変更できなかった問題を修正しました。 （TGT-52191）
* サポートされていない UI ルールが原因で XT アクティビティを編集できないエラーを修正しました。 （TGT-52273）
* Web ページに正常に配信されているにもかかわらず、アクティビティの変更が [!DNL Target] UI に表示されない問題を修正しました。 （TGT-52192）
* 更新 [!UICONTROL Visual Experience Composer] （VEC）で、パンくずリストがエディターの下部に常に表示されず、要素を正確に選択するのが困難になる問題を修正しました。 （TGT-51169）
* [!UICONTROL Audience] ドロップダウンリストで、ページネーションが原因ですべてのオーディエンスを表示できなかった問題を修正しました。 （TGT-52204）
* [!UICONTROL Automated Personalization] （AP）アクティビティに新しいオファーを追加する際に、無効なユーザー入力メッセージが表示される問題を修正しました。 （TGT-52210）
* 顧客が A4T にアクセスできない場合でも、[!UICONTROL Analytics for Target] （A4T）が誤ってレポートソースとして選択される問題を修正しました。 （TGT-52226）
* [!UICONTROL View a Page] URL 指標を使用してアクティビティを保存できない問題を修正しました。 （TGT-52260）
* アクティビティ内でオファーを作成する際に、顧客がワークスペースを選択できなかった問題を修正しました。 （TGT-52289）
* 別のエクスペリエンスに切り替えると、あるエクスペリエンスからの変更が正しく表示されない問題を修正しました。 （TGT-52184）
* アクティビティを開いた後、[!DNL Target] UI にデフォルトオファーが正しく表示されない問題を修正しました。 （TGT-52198）

## Target 権限の更新（2025 年 4 月 22 日（PT））

この今後の更新により、[!DNL Target] インスタンス設定の組織管理が強化され、様々なテストやパーソナライゼーションチームにわたるアクティビティの配信に影響を与える可能性のある、誤った更新を防ぐことができます。

2025 年 4 月 22 日（PT）より、[!UICONTROL Product] と [!UICONTROL Solutions] の管理者のみが、ワークスペースでの役割に関係なく、[!UICONTROL Administration] セクションの設定を更新でき [!DNL Target] ようになります。 この権限を持たないユーザーは、[!UICONTROL Administration] のセクションに読み取り専用でアクセスできます。

詳しくは、[Target の管理 ](/help/main/administrating-target/start-target.md) を参照してください。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
