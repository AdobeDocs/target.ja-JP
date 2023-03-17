---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 207095a1db483abcc59f7806a67e559ee8694397
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 69%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target]Standard／Premium 22.15.1（2023年3月8日、9日）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **3月8日**：アメリカ地域
* **3月9日**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **3月9日**：アジア太平洋（APAC）地域

>[!NOTE]
>
>以降に修正された問題により、「 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット]「 」（3 月 8 日と 9 日にリリースされた機能）は一時的に削除されました。 さらに内部テストがおこなわれた後、この機能は今後数週間以内に再びリリースされます。

このリリースには、以下の修正が含まれています。

* を使用したカスタム Web コンポーネントのオーサリングの更新 [!UICONTROL Visual Experience Composer] (VEC):

   * オーサリングプロセスを改善し、VEC でのシャドウ DOM 要素の選択を修正し、 [!DNL Target] シャドウルートを作成する際の実装タイプ。 これで、VEC でのシャドウ DOM 要素の選択が、どの Web サイトでも機能するようになりました。
   * VEC で#Shadow DOM を使用してHTML要素を読み込めなかった問題を修正しました。 （TGT-35801）
   * ShadowDOM を使用するSPA Web サイトでの VEC の問題を修正しました。 （TGT-43169）
   * 最適化目標の問題を修正しました。ShadowDOM の CSS セレクターを正しく識別しなかった「要素をクリックしました」。

>[!NOTE]
>
>VEC で作成した変更を確実に配信するには、 [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js)) のバージョンが 2.8 より大きい場合にのみ有効です。

**既知の問題**:を使用する際のシャドウルート要素のクリック追跡 [!DNL Adobe Experience Platform Web SDK] が正しく機能していません。 （TNT-47012）

## at.js バージョン 2.10.2（2023年3月7日（PT））

* `trackEvent` 関数が常にエラーを返す問題を修正しました。

すべての at.js リリースについて詳しくは、[at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}を参照してください。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに記載されていない、このガイドの更新点に関する詳細情報を表示します。<br>詳しくは、[ドキュメントの変更](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認できます。<br>詳しくは、「[以前のリリースのリリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、[Experience Cloud リリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md)ページを参照してください。 |
