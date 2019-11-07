---
keywords: リリースノート；リリース；更新；将来のリリース；拡張；新機能；修正点
description: DNL Adobe targetの最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。
title: Adobe targetプレリリースノート
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019年10月31日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Targetプラットフォーム（2019年10月31日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| Java SDK | Java SDKを使 [!DNL Target] 用すると、サーバー側 [!DNL Target] をデプロイできます。 このJava SDKを使用すると、、、などの他のソ [!DNL Target] リューシ [!DNL Adobe Experience Cloud] ョンとの統合を簡単に [!DNL Adobe Experience Cloud Identity Service]行うこ [!DNL Adobe Analytics]とができま [!DNL Adobe Audience Manager]す。<br>Java SDKは、アドビの配信APIを使用して統合する際に、ベストプラクティスを導入し、複雑 [!DNL Target] さを排除して、エンジニアリングチームがビジネスロジックに焦点を当てられるようにします。 最新バージョンで導入される主な機能は次のとおりです。<ul><li>キャッシュを使用してパフォーマンスを最適化できるプリフェッチと通知のサポート。</li><li>Webページとサーバー側の両方でのハイブリッド統合を使用する場合のパフ [!DNL Target] ォーマンスの最適化のサポートを追加しました。 at.js 2.2がエクスペリエンスを取得するための追加のサーバー呼び出しを行わないように、サーバー側で取得したエクスペリエンスによって設定されるという設定が導入されます。 `serverState` このアプローチは、ページ読み込みのパフォーマンスを最適化します。</li><li>Java SDKを使用したVECで作成されたアクティビティの取得のサポートが追加されました。これは、新しい配信APIで可能になりました。</li><li>開発者が [Target Java SDKに貢献できるように、オープンソースです](https://github.com/adobe/target-java-sdk)。</li></ul>詳しくは、リリースノート — [Target Java SDK（英語のみ）を参照してください](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)。<br>新しいTarget Java SDKを使用したサーバ側の最適化に関するアドビ [のテクニカルブログ（英語）で詳しく説明します](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。 |

## Target Standard／Premium 19.10.2（2019 年 10 月 31 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![プレミアムバッジ](/help/assets/premium.png) （複数値の属性で機能） | 複数の値を持つフィールドを使用する場合もあります。 次の例をご覧ください。<ul><li>ユーザに映画を提供する。 ある映画には複数の俳優がいる。</li><li>コンサートのチケットを売る。 特定のユーザーには、複数のお気に入りのバンドがあります。</li><li>あなたは服を売る。 1枚のシャツは複数のサイズで購入できます。</li></ul>これらのシナリオでのレコメンデーションを処理するには、複数値のデータをTarget Recommendationsに渡し、特別な複数値の演算子を使用します。 |

## Target Standard／Premium 20.1.1

Target Standard/Premium 20.1.1リリースは2020年1月に予定されています。 日付、機能、機能強化については、こちらからお知らせします。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
