---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: eaba6fe562644874fc800612894218094ca37f1b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 44%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025年4月8日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Target 権限の更新（2025 年 4 月 22 日（PT））

この今後の更新により、[!DNL Target] インスタンス設定の組織管理が強化され、様々なテストやパーソナライゼーションチームにわたるアクティビティの配信に影響を与える可能性のある、誤った更新を防ぐことができます。

2025 年 4 月 22 日（PT）より、[!UICONTROL Product] と [!UICONTROL Solutions] の管理者のみが、ワークスペースでの役割に関係なく、[!UICONTROL Administration] セクションの設定を更新でき [!DNL Target] ようになります。 この権限を持たないユーザーは、[!UICONTROL Administration] のセクションに読み取り専用でアクセスできます。

詳しくは、[Target の管理 ](/help/main/administrating-target/start-target.md) を参照してください。

## [!DNL Target Standard/Premium] 25.4.3 （2025 年 4 月 10 日（PT））

このリリースには、次の修正および更新が含まれています。

* [!UICONTROL Form-Based Experience Composer] の [!UICONTROL Activity QA] リンクが [!DNL Adobe Experience Cloud] ホームページに誤ってリダイレクトされる問題を修正しました。 （TGT-52055）
* アクティビティで重複オプションを解決する際にユーザーをガイドするエラーメッセージを追加しました。 （TGT-51927）

## [!DNL Target Standard/Premium] 25.4.2 （2025 年 4 月 8 日（PT））

このリリースには、次の修正および更新が含まれています。

* 保存して再度開いた後に、[!UICONTROL A/B Test] アクティビティに追加された追加のページが保持されない問題を修正しました。 （TGT-51994）
* 顧客がインラインスタイルセクションのスタイルを削除できない問題を修正しました。 （TGT-52070）
* 従来の UI と同様に、[!UICONTROL Activity QA] 定ダイアログボックスでの [ オーディエンス定義カード ](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) へのアクセス権が復元されました。 （TGT-52056）
* 更新された UI では、変更を加えずにページやオーディエンスを保存することができませんでした。 顧客がアクティビティに新しいページやオーディエンスを追加しても、変更を加えない場合、保存時に変更さ [!DNL Target] ていないオーディエンスは破棄されます。 この動作をユーザーに通知するために、関連する場所に通知が追加されました。 （TGT-52104）

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
