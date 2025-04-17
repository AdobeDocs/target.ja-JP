---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: cd25bda52b7a1b916a73ca5e531a7134ba8cef4e
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 43%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025年4月17日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target Standard/Premium] 25.4.4 （2025 年 4 月 17 日（PT））

このリリースには、次の修正および更新が含まれています。

* アクティビティで重複オプションを解決する際にユーザーをガイドするエラーメッセージを追加しました。 （TGT-51927）
* リダイレクトオファーを使用してページまたはエクスペリエンスを削除する際に、`ClickTrack` セレクターが削除されない問題を修正しました。 （TGT-51952）
* 空の `ClickTrack` セレクターを許可することで発生する問題を修正しました。 [!DNL Target] では、セレクターフィールドを空白にすることはできないという要件が追加されました。 （TGT-52107）
* 重複した名前の指標が正しく許可されない問題を修正しました。 指標に一意の名前が必要になりました。 （TGT-52201）
* [!UICONTROL Automated Personalization] （AP）アクティビティでオファーレベルのターゲティングを編集する際に、オーディエンス定義が表示されない問題を修正しました。 （TGT-52148）
* [!UICONTROL Editor] 権限を持つお客様がアクティビティを保存できない問題を修正しました。 （TGT-52227）
* オプション `OptionLocalIDs` 変更されていないときに、が正しく増分されなくなりました。 （TGT-52139）
* アクティビティを作成しようとすると「無効な `optionLocalIds`」メッセージが表示される問題を修正しました。 （TGT-52154）
* アクティビティに対して定義され `OptionLocalIDs` アクティビティと、エクスペリエンスの定義に使用されるアクティビティとの間の不一致が修正されました。 （TGT-52215）
* A/B アクティビティを作成しようとすると検証エラーが発生する問題を修正しました。 （TGT-51923）

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
