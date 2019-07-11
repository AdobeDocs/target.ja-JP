---
description: これらのリリースノートでは、最新または今後の[!DNL Adobe Target]リリースを参照してください。
keywords: リリースノート
seo-description: これらのリリースノートでは、最新または今後の[!DNL Adobe Target]リリースを参照してください。
seo-title: Adobe Targetリリースノート（プレリリース版）
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: ce1758df44740213a2d9011ee43f84cb52f6a29d

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019 年 7 月 9 日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard／Premium 19.7.1（2019 年 7 月 23 日）{#tgt-19-7-1}

このリリースには、次の新機能および機能強化が含まれています。

| 機能／拡張機能 | 説明 |
| --- | --- |
| Visual Experience Composer（VEC） | When you click an image then click [!UICONTROL Replace With], two new options display:<ul><li>**HTML**:HTMLで画像を置換して、親要素を選択してHTMLオプションにアクセスすることなく要素をフルコントロールできます。</li><li>**エクスペリエンスフラグメント**:画像をAdobe Experience Manager（AEM） [エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md) に置き換えて、Targetアクティビティで作成した要素をすばやく挿入できます。</li></ul>（TGT-34097） |
| モバイルアプリケーション Visual Experience Composer | Mobile App VECに、クリック追跡用に設定した要素を表示する新しい変更パネルが表示されます。（TGT-31741） |
| ![A/Bテストおよびエクスペリエンスターゲット設定（XT）アクティビティ](/help/assets/premium.png)<br>のプレミアムバッジ | Recommendationsオファー（アルゴリズム）のステータスは、Recommendationsオファーを含むA/BテストおよびXTアクティビティの概要ページに表示されます。次のようなステータスがあります。結果準備完了、結果が準備されていない、フィード失敗。（TGT-33649） |
| Experience Cloud ID（ECID）ライブラリを使用したat. js2.0以降のクロスドメイントラッキングサポート | 以前は、クロスドメイントラッキングはat. js2ではサポートされていませんでした。*x*. このリリースでは、at. js2.0以上を使用するお客様は、ECIDライブラリを通じてクロスドメイントラッキングを利用できるようになりました。クロスドメイントラッキングを機能させるには、ページにEIDライブラリをat. js2.0以上と組み合わせてインストールする必要があります。It is highly recommended to use [Experience Cloud ID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html). |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
