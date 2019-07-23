---
description: 最新または今後の[!DNL Adobe Target]リリースを参照してください。
keywords: リリースノート
seo-description: 最新または今後の[!DNL Adobe Target]リリースを参照してください。
seo-title: Adobe Targetリリースノート（プレリリース版）
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019 年 7 月 24 日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard／Premium 19.7.1（2019 年 7 月 24 日）{#tgt-19-7-1}

このリリースには、次の新機能および機能強化が含まれています。

| 機能／拡張機能 | 説明 |
| --- | --- |
| モバイルアプリケーション Visual Experience Composer | Mobile App VECに、クリック追跡用に設定した要素を表示する新しい変更パネルが表示されます。(TGT-31741)<br> See [Set up click tracking in the Mobile App](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![A/Bテストおよびエクスペリエンスターゲット設定（XT）アクティビティ](/help/assets/premium.png)<br>のプレミアムバッジ | Recommendationsオファー（アルゴリズム）のステータスは、Recommendationsオファーを含むA/BテストおよびXTアクティビティの概要ページに表示されます。次のようなステータスがあります。結果準備完了、結果が準備されていない、フィード失敗。(TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| Experience Cloud ID（ECID）ライブラリを使用したat. js2.0以降のクロスドメイントラッキングサポート | 以前は、クロスドメイントラッキングはat. js2ではサポートされていませんでした。*x*. このリリースでは、at. js2.0以上を使用するお客様は、ECIDライブラリを通じてクロスドメイントラッキングを利用できるようになりました。クロスドメイントラッキングを機能させるには、ページにEIDライブラリをat. js2.0以上と組み合わせてインストールする必要があります。[Experience Cloud IDライブラリ4.3.0以降を使用する](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 必要があります。<br>at. js2. xの [クロスドメイントラッキングのサポート](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain)を参照してください。 |
| Experience Cloud ID（ECID）ライブラリ4.3を使用したAppleのTP2.1およびITP2.2のTargetサポート | 今日、Targetのお客様は、アドビのCNAME認定プログラムを利用してAppleのTP2.1およびITP2.2を軽減することができます。<br>このリリースでは、Targetは、EIDライブラリ4.3とシームレスに統合して、サーバー側のcookieを利用してITP2.1およびITP2.2を軽減します。TargetのJavaScriptライブラリと共に [EIDライブラリ4.3以上](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) をデプロイして将来のASTリリースを緩和することを強くお勧めします。EIDライブラリは、ブラウザーによって導入されるCookieポリシーの変更に堅牢なソリューションを提供する、ロールアウト機能の強化を継続します。<br>[Apple Intelligent Tracking Prevention（ITP）2. xを参照](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)してください。 |

**機能強化、修正、変更点**

* 重複値を追加するとRecommendationsアクティビティの除外値がクリアされない問題を修正しました。（TGT-34996）
* ターゲットページから、Recommendationsアクティビティのデザインを削除できるようになりました（3つのガイドによるワークフローの手順2）。デザインを削除するには、複数のデザインが選択されている必要があります。（TGT-35118）
* 一部の顧客がTarget UIで適切に読み込まれるか、編集可能になるためにカスタム条件カードが使用できない問題を修正しました。（TGT-35170）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
