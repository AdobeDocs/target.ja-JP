---
keywords: リリースノート；リリース；アップデート；今後のリリース；機能強化；新機能；修正；アップデート；プレリリース；早期アクセス
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c882a5eb6530f3b3fe44484ee580beadeddaae23
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 29%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2025 年 6 月 25 日（PT）**

>[!NOTE]
>
>* リリース日、機能などの情報は、予告なく変更されることがあります。
>
>* 最新のリリースに関する情報を確認するには、[Target リリースノート ](release-notes.md) を参照してください。
>
>* 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target Standard/Premium] 25.6.4（2025年6月26日（PT））

このリリースには、次の修正および更新が含まれています。

* レガシー VEC で使用可能な機能と連携するために、更新された [!UICONTROL Visual Experience Composer] （VEC） UI に [!UICONTROL Rearrange] オプションを追加しました。 （TGT-46957 および TGT-52876）
* [!UICONTROL A/B Test] アクティビティでバリアントエクスペリエンス（エクスペリエンス B など）に加えた変更が保持されない問題を修正しました。 エクスペリエンスを切り替えると、バリアントに対する変更が消えます。 この問題は、コントロールエクスペリエンスには影響しませんでした。 （TGT-52664）
* 特定の顧客がアクティビティを作成または保存できない一方で、他の顧客が問題なく同じアクションを実行できる問題を修正しました。 複数のアカウントで問題が矛盾していました。（TGT-52842）
* [!UICONTROL Automated Personalization] （AP）アクティビティのレポートデータを取得する際に発生していたヌルポインター例外を修正しました。 （TGT-52362）
* [!UICONTROL Automated Personalization] （AP）アクティビティで、オファーレベルの詳細が.CSV ファイルに表示されない問題を修正しました。 （TGT-52675）
* 更新された VEC で変更を適用すると、期待される [!UICONTROL Experience Fragment] を含め、変更内容が最初は正しく表示されます。 ただし、エクスペリエンスを切り替えたり、追加の編集を行ったりすると、セレクターの問題が原因で一部の変更が適用されません。 （TGT-52679）
* 既存のアクティビティを複製して新しいアクティビティを作成した場合、複製されたアクティビティの QA リンクで、元のアクティビティのページ URL が誤って保持される問題を修正しました。 （TGT-52775）
* 更新された VEC で [!UICONTROL On-device Decisioning] が意図せず使用できない問題を修正しました。 （TGT-52371）
* 製品 [!DNL Recommendations] ーディエンスアクティビティを編集できない問題を修正しました。 Target UI を使用して VEC にアクセスしようとすると、[!UICONTROL Overview] ページにエラーが表示され、編集できませんでした。 （TGT-52823）
* エクスペリエンス名が 50 文字を超えた場合に、[!DNL Recommendations] アクティビティを保存できない問題を修正しました。 （TGT-52619）
* 新しい UI で条件を変更した後、顧客が Recommendations アクティビティを保存できない問題を修正しました。 この問題は権限に関連していると考えられ、類似の役割を持つすべてのユーザーに影響するわけではありません。 （TGT-52816）
* [!UICONTROL Editor] の役割を持つユーザーが [!DNL Recommendations] アクティビティを編集できない問題を修正しました。 デザインを変更し、アクティビティを保存しようとすると、ユーザーが関連するワークスペースで既にその役割を持っている場合でも、「[editor]」権限が必要であるという 403 Forbidden エラーが発生しました。 （TGT-52836）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [ リリースノート：Adobe Target Platform Experience Web SDK] （https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n） | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
