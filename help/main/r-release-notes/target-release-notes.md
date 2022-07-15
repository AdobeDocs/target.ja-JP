---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースではどのような新機能や機能強化が追加されますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fa6324606b32f265084615fd1c13ce6c49921b48
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 100%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2022年6月30日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target Standard/Premium] 22.6.2（2022年6月30日（PT））

このリリースには、以下の機能、拡張機能および修正が含まれています。

| 機能 | 説明 |
| --- | ---  |
| 製品内通知 | 次の関連する製品内通知を取得します。<ul><li>**アクティビティ**：手動で、または開始日または終了日に達したことにより、アクティビティが承認または無効化されたときの、すべてのアクティビティタイプに関する通知。 通知には、アクティビティの名前と、アクティビティの概要ページへのリンクが含まれます。</li><li>**プロファイルスクリプト** プロファイルスクリプトが手動または Target によって有効化または無効化されたときの通知。</li><li>**Recommendationsフィード**：Recommendationsフィードが手動またはターゲットによってアクティブ化または非アクティブ化されたときの通知。また、Recommendations フィードに失敗した場合には通知も送信されます。</li></ul> デフォルトでは、製品管理者、発行者および承認者が通知を受信します。 通知は、Experience Cloud の環境設定内で設定できます。<br>詳しくは、[通知とお知らせ](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements)を参照してください。 |
| *Adobe Target 開発者ガイド* | *Adobe Target 開発者ガイド*&#x200B;は、すべての [!DNL Target] 開発者コンテンツを 1 つの便利なガイドにまとめたものです。ガイドには、[!DNL Target] と [!DNL Recommendations]、[!DNL Target] SDK、[!DNL Target] API の実装に関する情報が掲載されています。<br>詳しくは、[Adobe Target 開発者ガイド](https://developer.adobe.com/target/){target=_blank} を参照してください。 |

* [!UICONTROL 編集者]の役割を持つユーザーは、ライブアクティビティでオーディエンスを編集できなくなりました。 （TGT-43582）
* オーディエンス名の最初の文字として感嘆符（!）が使用されているオーディエンス（例：!London）を顧客が保存しようとすると、警告メッセージが表示されるようになりました。（TGT-43643）
* 一部のお客様のオーディエンス定義の詳細カードで、終了したアクティビティがまだライブであると示されていた問題を修正しました。 （TGT-43527）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
