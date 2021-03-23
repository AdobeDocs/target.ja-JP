---
keywords: リリースノート；新機能；リリース；更新；更新；リリース；機能強化；修正；バグ修正；更新
description: SDK、API、JavaScript ライブラリなど、Adobe Target の現在のリリースに含まれている新機能、機能強化および修正について説明します。
title: 現在のリリースに含まれる新機能
feature: リリースノート
translation-type: tm+mt
source-git-commit: 9155c487ed078f8af493755a2b4f067eafc8ae68
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 36%

---


# Target リリースノート（現行）

以下のリリースノートでは、各[!DNL Adobe Target Standard]および[!DNL Target Premium]リリースの機能、拡張機能および修正点に関する情報を提供しています。 また、ターゲットAPI、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも適宜含まれています。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリ [!DNL Adobe Target] はサポートされなくなります。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>サイトに問題が発生する可能性を回避するため、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンにこの日より前に移行してください。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## Recommendationsフィード処理サーバーのIPアドレスの変更（2021年3月16日）

[!DNL Target Recommendations]フィード処理サーバーのIPアドレスは、2021年3月16日に更新されました。 詳しくは、[Recommendationsフィード処理サーバーで使用されるIPアドレス](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md)を参照してください。

## Target Standard/Premium 21.2.1（2021年3月10日）

このメンテナンスリリースには、次の機能強化、修正および変更が含まれています。

括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

* 許可されるオファーサイズが増加しました。(TGT-38304)

   | タイプ | 以前の制限 | 新しい制限 |
   | --- | --- | --- |
   | HTML | 256 KB | 1024 KB |
   | ターゲットUIからのビジュアルオファー | 64 KB | 各エクスペリエンスに1024 KB |
   | API経由 | 512 KB | 1024 KB |

* [!UICONTROL 自動ターゲット] (AT)および [!UICONTROL Automated Personalization]   (AP)アクティビティ用のパーソナライゼーションインサイトレポートが毎日作成されるようになりました。過去15、30および60日間の[!UICONTROL 自動セグメント]または[!UICONTROL 重要な属性]を提供するレポートを選択できます。 45日と90日のオプションが削除され、その他のルックバックウィンドウの設定が毎日実行できるようになりました。 （TGT-39472）
* アクティビティの[!UICONTROL 目標と設定]ページで「依存関係を編集]」をクリックすると、現在の依存関係が表示されない問題を修正しました。 [!UICONTROL （TGT-39340）
* ワークスペースの[!UICONTROL オーディエンスライブラリ]を更新する際の問題を修正しました。 更新の前に、現在選択されているワークスペースのオーディエンスが表示されます。 更新後、[!UICONTROL デフォルトのワークスペース]とそのオーディエンスが表示されます。 現在のワークスペースとそのオーディエンスは、更新後も保持されるようになりました。 （TGT-38871）
* [!UICONTROL Recommendations]アクティビティをコピーし、後で条件のシーケンスを変更して元のアクティビティを編集する際に発生していた問題を修正しました。 元のアクティビティの条件のシーケンスの変更も、コピーされたアクティビティに誤って適用されていました。 （TGT-39155）
* [!UICONTROL Recommendations]の除外に正しくない数の製品が表示される問題を修正しました。 （TGT-39599）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | このガイドの更新に関する表示の詳細情報（リリースノートには含まれていません）。<br>詳しくは、「[ドキュメントの変更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、「 [Experience Cloudリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)」を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe優先度製品の更新 | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
