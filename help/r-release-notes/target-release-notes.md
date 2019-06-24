---
description: これらのリリースノートでは、最新または今後の Target リリースの機能、機能強化、修正および既知の問題について説明します。
keywords: リリースノート
seo-description: これらのリリースノートでは、最新または今後の Adobe Target リリースの機能、機能強化、修正および既知の問題について説明します。
seo-title: Adobe Targetリリースノート（プレリリース版）
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a30f868c49bca7a0c017d272b435a6a351c6e9a6

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日:2019年6月8日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.6.1 (June 25, 2019) {#tgt-19-6-1}

このリリースには、次の新機能および機能強化が含まれています。

| 機能／拡張機能 | 説明 |
| --- | --- |
| Visual Experience Composer（VEC） | **新しいVECメニューオプション**:VECでページ要素をクリックすると、その要素タイプで使用できるオプションがメニューに表示されます。<ul><li>[!UICONTROL スタイル/背景] オプションを使用して、選択した要素の背景画像と色を変更できるようになりました。（TGT-15001）</li></ul>**クリック追跡の改善**:VECおよびシングルページアプリケーション（SPA） VEC内でのクリック追跡の設定プロセスを改善しました。<ul><li>クリック追跡で使用する要素を選択する際、使用可能なすべてのエレメントの名前が右側の変更パネルに表示され、目的の要素をすばやく簡単に選択できます。</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. この番号にマウスポインターを置くと、選択したすべての要素の名前を表示できます。（TGT-33878）</li></ul> |
| シングルページアプリケーション Visual Experience Composer （SPA VEC） | **ガイド付きワークフロー**:新しいガイド付きワークフローは、単一ページアプリ用にアクティビティを実行して実行するために、ページ配信ルール設定をどのように設定すべきかを理解するのに役立ちます。(TGT-33718)<br>**Clone modifications**: You can now define a modification using the SPA VEC and then clone that modification for use in other views in your Single Page App. （TGT-33882） |
| Mobile Visual Experience Composer | **複数のアプリケーションバージョン**:モバイルアプリの複数バージョンのアクティビティを作成できるようになりました。これにより、バージョンが類似していて、アプリケーションのUIを大幅に変更する必要がなくなります。（TGT-34231） |
| ![Premiumバッジ](/help/assets/premium.png) 自動パーソナライゼーション（AP）および自動ターゲット | **コントロールとしての特定のエクスペリエンス**:APまたは自動ターゲットアクティビティの作成時に、コントロールとして使用するエクスペリエンスを選択できます。この機能により、アクティビティで設定されたトラフィック配分の割合に基づいて、特定のエクスペリエンスにコントロールトラフィック全体をルーティングできます。その後、その1つのエクスペリエンスへのトラフィックを制御するために、パーソナライズされたトラフィックのパフォーマンスレポートを評価できます。現在の制御オプション（ランダムに提供されるエクスペリエンス）は引き続き使用できます。(TGT-32801 &amp; TGT-26572)<br>**Personalization Insights reports**: The marketer-friendly naming for attributes when a visitor sees a specific piece of content in a specific location provides more meaningful information. （TGT-33326 および TGT-34957） |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
