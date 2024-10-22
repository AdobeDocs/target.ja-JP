---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b1ead7317debadafcb42469894cdb7b6ba337110
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 28%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2024年10月22日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Adobe Experience Platform Web SDK] `__view__` 範囲の最適化（2024 年 10 月 22 日（PT））

2024 年 7 月 22 日（PT）から 2024 年 8 月 15 日（PT）の間に、[!DNL Target] チームは `__view__` の範囲を最適化し、アクティビティのインプレッション、訪問および訪問者レポートの精度を高めました。 この最適化は、自動レンダリングされた提案のレポートデータを自動的に取得することを目的としており、ほとんどのアカウントに対して透過的である必要があります。

新規の [!DNL Adobe Experience Platform Web SDK] ユーザーはすべて、この最適化を有効にします。 ただし、at.js から移行したお客様で、以下の実装手順に従っていないお客様は、最適化を無効にしています。 アドビでは、これらのお客様に、2025 年 2 月 3 日までに実装を確認することをお勧めします。 この日以降、すべてのお客様に対して最適化を有効にします。 以下に示すように、までに実装のレビューと調整を行わないと、レポートに影響を与える可能性があります。 実装が影響を受けるかどうかを確認する必要がある場合や、実装を調整するためにより多くの時間が必要な場合は、[!DNL Adobe Client Care] にお問い合わせください。

手動の提案レンダリングを行う場合にこの最適化を活用するには、エクスペリエンスを手動でレンダリングした後や、`applyPropositions` メソッド（または対応する [!DNL Launch] アクションをヘルパーとして）を使用してエクスペリエンスをレンダリングする際に、[[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} ールをレビューして通知を送信していることを確認します。

エクスペリエンスを手動でレンダリングする場合の最も一般的なシナリオは次のとおりです。

* JSON オファーの使用
* [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md) で作成されたアクティビティでのカスタム決定範囲の使用
* グローバル `__view__` スコープを使用する [!UICONTROL Form-Based Experience Composer] を使用して作成されたアクティビティを取得する場合、`renderDecisions: true` を使用しない

*データ収集* ガイドの [ パーソナライズされたコンテンツのレンダリング ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} に記載されているように通知が実装されていない場合、[!DNL Target] および [Analytics for Target レポート ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）でレポートデータが欠落している可能性があります。 特定のシナリオでは、レポートデータが取得されないので、誤ったトラフィック分割に気付く場合があります。 または、他のシナリオで、同じイベントを繰り返しレポートする場合もあります。

実装に応じて、[!DNL Analytics] および A4T レポートの影響を確認します。

[!DNL Platform Web SDK] では、エクスペリエンスとパーソナライゼーションのレンダリングに対して、次の 2 つの実装タイプをサポートしています。

* **パーソナライゼーションと測定のための 1 回の呼び出し**

  最初にお勧めしたのは、[!DNL Platform Web SDK] のシングルコールアプローチは廃止される予定で、スプリットコールアプローチに置き換わることです。 Adobeでは、すべての新しい実装に新しい分割呼び出しアプローチを使用することをお勧めし、既存のお客様も分割呼び出し方式に移行することをお勧めします。

  シングルコールアプローチを引き続き使用すると、[!DNL Analytics] レポートに次のような予期しない変更が表示される場合があります。

   * 潮が引込む。
   * A4T と [!UICONTROL Page View] のヒットが結び付けられていないので、[!DNL Analytics] eVar とイベントを使用して A4T レポートの特定の分類や相関関係を実行することが困難になります。

* **分割呼び出し（ページイベントの上下とも呼ばれます）。**

  この実装タイプは、[!DNL Adobe] が推奨する新しい [ 分割呼び出し実装アプローチ ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} です。 このアプローチでは、新しい最適化は [!DNL Analytics] や A4T レポートには影響しません。

ご不明な点については、[Adobeカスタマーケア ](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C) にお問い合わせください。 （KB-2179）

## [!DNL Target Standard/Premium] 24.10.2 （2024 年 10 月 21 日（Pt））

このリリースには、以下の修正が含まれています。

* [!UICONTROL Compose] および [!UICONTROL Browse] モードで [!UICONTROL Recommendations] アクティビティを読み込むことができない問題を修正しました。 （TGT-50709）
* 新しい [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] 拡張機能で ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 「キャンセル」をクリックした後に [!UICONTROL Visual Experience Composer] （VEC）から [!UICONTROL Activities Library] にリダイレクトされる問題を修正しました。 この修正を行う前は、お客様はアクティビティを新規作成する前に [!UICONTROL Activities Library] を更新する必要がありました。 （TGT-49980）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
