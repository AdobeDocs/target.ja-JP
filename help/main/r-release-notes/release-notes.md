---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースに含まれているもの
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 49517f858b39a70df7643125e703f31bf45b7336
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 84%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target Standard/Premium] 22.6.2（2022 年 6 月 25 日）

このリリースには、以下の機能強化および修正が含まれています。

* [!UICONTROL 編集者]の役割を持つユーザーは、ライブアクティビティでオーディエンスを編集できなくなりました。 （TGT-43582）
* 顧客が感嘆符 (! ) をオーディエンスの名前の最初の文字（例：!London）として使用します。 （TGT-43643）
* 一部のお客様のオーディエンス定義の詳細カードで、終了したアクティビティがまだライブであることが示されていた問題を修正しました。 （TGT-43527）

## [!DNL Target Standard/Premium] 22.6.1 (stagger リリース：（2022 年 6 月 7～9 日）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **6月7日**：アジア太平洋（APAC）地域
* **6月8日**：アメリカ地域
* **6月9日**：ヨーロッパ、中東、アフリカ（EMEA）地域

このリリースには、以下の機能強化および修正が含まれています。

* 新しい[!UICONTROL オーディエンス]ページが拡張され、過去にオーディエンスが保存されていた古いデータベースと、バックエンドから直接情報を取得する新しいアーキテクチャとの間の一貫性のない状態が回避されました。（TGT-43552）
* Target UI によって「空の」コンテナが作成されることにより、一部の顧客が結合オーディエンスを保存できなかった問題を修正しました。（TGT-43588）

## Target プラットフォームリリース（2022年5月25日（PT））

このリリースには、以下の機能強化および修正が含まれています。

* 追加済み [ユーザーエージェントクライアントのヒント](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank} のサポート。
* [!UICONTROL Experience Targeting]（XT）アクティビティの[!UICONTROL オファーの決定]をレンダリングする際に、断続的にタイムアウトが発生していた問題を修正しました。（TNT-44611）

## at.js バージョン 2.9.0（2022年5月27日（PT））

* 追加済み [ユーザーエージェントクライアントのヒント](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank} のサポート。
* 同じページ上の複数の mbox リクエストが異なるインプレッション ID を持っていたバグを修正しました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、[ドキュメントの変更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/main/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md)ページを参照してください。 |
