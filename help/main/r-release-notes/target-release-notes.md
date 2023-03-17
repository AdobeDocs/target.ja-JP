---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の  [!DNL Target]  リリースには、どのような新機能や機能強化が含まれますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 59%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2023年14月4日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard／Premium 22.15.1（2023年3月8日、9日（PT））

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


## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
