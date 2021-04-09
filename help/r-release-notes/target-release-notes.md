---
keywords: リリースノート；リリース；更新；今後のリリース；拡張；新機能；修正；更新；プレリリース
description: SDK、API、JavaScriptライブラリを含む、今後のAdobe Targetリリースに含まれる新機能、機能強化および修正について説明します。
title: 今後のリリースで追加される新機能
feature: リリースノート
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: a45cfbd52df935fa3138eda6cc7f1028c13ff81d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 23%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021年4月10日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングに応じて、これらのページの情報は同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリをサポートし [!DNL Adobe Target] なくなりました。2021年3月31日以降、mbox.jsから行われたすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにデフォルトコンテンツが提供されるようになりました。
>
>サイトに発生する可能性のある問題を回避するには、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行します。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

## Target Standard／Premium 21.4.1（2021 年 4 月 19 日）

このリリースには、次の新機能が含まれています。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

| 機能 | 詳細 |
| --- | --- |
| at.jsのオンデバイス判定のサポート | オンデバイス判定機能を使用すると、マーケターと開発者は、ユーザーのブラウザー上で実験とパーソナライズをほぼゼロの待ち時間で行うことができます。 |

このリリースには、次の機能強化、修正および変更が含まれています。

* オーディエンスを[!UICONTROL すべての訪問者]に変更した後、アクティビティが同期できない問題を修正しました。 （TGT-40259）
* 「[!UICONTROL オファーを許可しない]」オプションが有効になっている場合でも、[!UICONTROL Automated Personalization]アクティビティの異なる場所で使用すると重複が複製されない問題を修正しました。 （TGT-39567）
* [!UICONTROL 管理]/[!UICONTROL Scene7構成]ページが正しく読み込まれない問題を修正しました。 （TGT-39918）
* プロパティが正しくないワークスペースにマップされる問題を修正しました。 （TGT-39869）
* [!DNL Target Recommendations] は、エンティティのフィルタリングルールに新しいリストベースの演算子をサポートしています。（TGT-39234）

   新しく追加された演算子は次のとおりです。

   * リストに含まれる
   * リストに含まれない
   * リストに
   * リストに
   * リストにすべての項目が含まれる
   * リストに

* レコメンデーションの除外の作成中に環境を変更した後にリクエストが失敗した場合、無限に読み込まれる問題を修正しました。 （TGT-39948）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
