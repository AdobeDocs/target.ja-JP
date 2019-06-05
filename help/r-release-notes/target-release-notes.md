---
description: これらのリリースノートでは、最新または今後の Target リリースの機能、機能強化、修正および既知の問題について説明します。
keywords: リリースノート
seo-description: これらのリリースノートには、最新または今後のAdobe Targetリリースの機能、機能強化、修正および既知の問題に関する情報が記載されています
seo-title: Target リリースノート（プレリリース）
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: bac43f0907b083f416aaf72fca0eb4c6d4b83a7e

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019 年 5 月 28 日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、変更されることがあります。現在のリリースに関する情報を表示するには [、Targetリリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。

## Target Standard/Premium19.6.1（2019年6月26日） {#tgt-19-6-1}

| 機能/拡張機能 | 説明 |
| --- | --- |
| Visual Experience Composer（VEC） | <ul><li>VECの [!DNL Styles > Background] メニューを使用して、選択した要素の背景画像と色を変更できるようになりました。（TGT-15001）</li><li>VECでページ要素をクリックすると、その要素タイプで使用できるオプションがメニューに表示されます。画像をクリックすると、次 [!DNL Replace With]の2つの新しいオプションが表示されます。 [!DNL HTML][エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md)を参照してください。<br> 画像をHTMLに置換すると、HTMLオプションにアクセスする親要素を選択しなくても要素をフルコントロールできます。エクスペリエンスフラグメントを使用すると、Adobe Experience Manager（AEM）で作成された要素をTargetのアクティビティにすばやく挿入できます。（TGT-34097）</li></ul> |
| シングルページアプリ（SPA） Visual Experience Composer（VEC） | <ul><li>新しいガイド付きワークフローは、単一ページアプリ用にアクティビティを実行して実行するために、ページ配信ルール設定をどのように設定すべきかを理解するのに役立ちます。（TGT-33718）</li><li>SPA VECを使用して変更を定義し、その変更を単一ページアプリの他のビューで使用するためにコピーできるようになりました。（TGT-33882）</li><li>SPA VEC内でのクリック追跡の設定プロセスを改善しました。<br>クリック追跡で使用する要素を選択する際、使用可能なすべてのエレメントの名前が右側の変更パネルに表示され、目的の要素をすばやく簡単に選択できます。<br>3つのガイドによるアクティビティワークフローの [!DNL Goals & Settings] ページには、クリック追跡用に選択した要素数を表す数値が表示されます。この番号にマウスポインターを置くと、選択したすべての要素の名前を表示できます。（TGT-33878） </li></ul> |
| Mobile Visual Experience Composer（VEC） | <ul><li>モバイルアプリの複数バージョンのアクティビティを作成できるようになりました。これにより、バージョンが非常によく似ており、アプリのUIを大幅に変更する必要がないので、時間と労力を節約できます。（TGT-34231）</li></ul> |
| ![Premium BadgeAutomated](/help/assets/premium.png)<br>Personalization（AP）および自動ターゲットアクティビティ:コントロールとしてのエクスペリエンス | <ul><li>AP または自動ターゲットアクエィビティを作成する際、コントロールとして使用するエクスペリエンスを選択できます。この機能を使用すると、アクティビティで設定されたトラフィック配分率に基づいて、コントロールトラフィック全体を特定のエクスペリエンスにルーティングすることができます。その後、コントロールエクスペリエンスに対するパーソナライズされた配信のパフォーマンスを評価できます。（TGT-32801 および TGT-26572）</li></ul> |

### 機能強化、修正、変更点

* Adobe コード内の   <BODY> タグが、ページ上の要素をクリックしたときにVECの下部に表示されるDOMパスに表示されるようになり、 <BODY> 。（TGT-33736）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Targetおよびその他のAdobe Experience Cloudソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Updateにサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
