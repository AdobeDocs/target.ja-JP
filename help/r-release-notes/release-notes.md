---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
title: 現在のリリースに含まれる新機能
feature: リリースノート
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 42d9d7ed422bd5334a7f5e6467b0257f7ff4ab50
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 67%

---

# Target リリースノート（現行）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、Target API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js、その他のプラットフォームの変更点に関するリリースノートも含まれています。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトに起こりうる問題を回避するため、新しい [!DNL Adobe Experience Platform Web SDK] の最新バージョンまたは at.js JavaScript ライブラリの最新バージョンに移行してください。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## [!DNL Target Standard/Premium] 21.8.1（日付は未定）

>[!NOTE]
>
>[!DNL Target Standard/Premium] 21.8.1リリースが遅れました。 2021年8月4日にリリースされる代わりに、バージョン21.8.1は、今後数日以内にリリースされます。 詳細は、利用可能な場合に表示されます。

このメンテナンスリリースには、お客様向けの次の変更を含む、多くのバックエンドの機能強化が含まれています。

* [!UICONTROL フォームベースのExperience Composer]で作成された[!UICONTROL 自動パーソナライゼーション]アクティビティのレポートで、削除されたオファーがレポートで参照される問題を修正しました。 この問題が発生すると、「このレポートのデータを取得できません。 問題が解決しない場合は、AdobeのClientCareにお問い合わせください。」 （TGT-41028）

## [!DNL Target Delivery API] (2021 年 8 月 3 日（PT）)

このリリースで強化された機能は次のとおりです。

* mboxパラメーターの制限が100パラメーターに増えました。 以前の制限は50パラメーターでした。 （TNT-41717）
* `categoryId`の制限が256文字に増えました。 以前の上限は128文字でした。
* Delivery APIに次の[!DNL Adobe Audience Manager](AAM)の詳細が追加されました。

   * AAM UUID:ユーザーを一意に識別するために使用される内部AAM ID。
   * dataPartnerId:データパートナーのID。
   * dataPartnerUserId:データパートナーから提供されたユーザーID。

   以前は、Delivery APIには`dcsLocationHint`と`blob`のみが含まれていました。 （TNT-41644）

## at.js 2.6.0（2021 年 7 月 27 日（PT））

* at.js 設定 `secureOnly` が `true` に設定されている場合は常にセキュア属性を cookie に追加するようになりました。
* `triggerView()` を使用する際に応答トークンを使用できるようになりました。
* `CONTENT_RENDERING_NO_OFFERS` イベントに関連する問題を修正しました。これで、[!DNL Target] からコンテンツが返されない場合は常に、このイベントが正しくトリガーされます。
* `prefetch` リクエストを使用したときに、[!DNL Anlytics for Target]（A4T）のクリック指標の詳細が正しく返されます。
* UUID の生成では、`Math.random()` を使用しなくなり、`window.crypto` に基づくようになりました。
* `sessionId` cookie の有効期限は、すべてのネットワーク呼び出しで正しく延長されます。
* [!UICONTROL 単一ページアプリケーション]（SPA）ビューキャッシュの初期化が正しく処理され、`viewsEnable` 設定に従うようになりました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Platform Web SDKの各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、「[ドキュメントの変更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe 優先製品のアップデート | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
