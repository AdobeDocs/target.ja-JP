---
keywords: リリースノート；リリース；更新；今後のリリース；拡張；新機能；修正；更新；プレリリース
description: SDK、API、JavaScriptライブラリを含む、今後のAdobe Targetリリースに含まれる新機能、機能強化および修正について説明します。
title: 今後のリリースで追加される新機能
feature: リリースノート
translation-type: tm+mt
source-git-commit: 453106f7534f83c205722421bbf00044fde7da67
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 25%

---


# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。 リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 2 月 17 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングによっては、これらのページの情報が同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリ [!DNL Adobe Target] はサポートされなくなります。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>Adobeでは、サイトに発生する可能性のある問題を回避するため、すべてのお客様に対して、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

## Target Standard/Premium 21.2.1（2021年3月10日）

このメンテナンスリリースには、次の機能強化、修正および変更が含まれています。

括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

* 許容されるオファーサイズの拡大：

   | タイプ | 以前の制限 | 新しい制限 |
   | --- | --- | --- |
   | HTML | 256 KB | 1024 KB |
   | ターゲットUIからのビジュアルオファー | 64 KB | 各エクスペリエンスに1024 KB |
   | API経由 | 512 KB | 1024 KB |

* アクティビティの[!UICONTROL 目標と設定]ページで「依存関係を編集]」をクリックすると、現在の依存関係が表示されない問題を修正しました。 [!UICONTROL （TGT-39340）
* ワークスペースの[!UICONTROL オーディエンスライブラリ]を更新する際の問題を修正しました。 更新の前に、現在選択されているワークスペースのオーディエンスが表示されます。 更新後、[!UICONTROL デフォルトのワークスペース]とそのオーディエンスが表示されます。 現在のワークスペースとそのオーディエンスは、更新後も保持されるようになりました。 （TGT-38871）
* [!UICONTROL Recommendations]アクティビティをコピーし、後で条件のシーケンスを変更して元のアクティビティを編集する際に発生していた問題を修正しました。 元のアクティビティの条件のシーケンスの変更も、コピーされたアクティビティに誤って適用されていました。 （TGT-39155）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html)
