---
keywords: Recommendations
description: Analytics を Target のレポートソースとして有効化する場合（A4T）のデータ収集プロセスでいくつかの変更点があります。
title: Adobe TargetのレポートソースとしてAdobe Analyticsを実装する前に(A4T)
feature: a4t implementation
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 57%

---


# 実装する前に{#before-you-implement}

Several changes occur in your data collection process when enabling [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

この統合を使用する前に、以降の節を確認して、レポートプロセスへの影響を検討してください。

## 導入に必要な条件 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>A4T を使用する際は、事前にアカウントで統合のプロビジョニングを依頼しておく必要があります。プロビジョニングの依頼には[このフォーム](https://www.adobe.com/go/audiences)を使用します。

この A4T 統合では、A4T でリダイレクトオファーを使用するかどうかに応じて、次のバージョン以降のライブラリを実装する必要があります。

### A4T でリダイレクトオファーを使用 *しない* 場合に必要な要件

この統合で、A4T でのリダイレクトオファーを使用しない場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.jsバージョン1.8.0
* [!DNL Adobe Target]（実装によって異なります）：at.js バージョン 0.9.1 または mbox.js バージョン 61
* Adobe Analytics：appMeasurement.js バージョン 1.7.0

### A4T でリダイレクトオファーを使用する場合に必要な要件

A4T でリダイレクトオファーを使用する場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.jsバージョン2.3.0
* [!DNL Adobe Target]: at.js バージョン 1.6.2

   **注意：** mbox.js ライブラリは A4T によるリダイレクトオファーをサポートしていません。実装では at.js を使用する必要があります。

* Adobe Analytics：appMeasurement.js バージョン 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## 導入の前に知っておくべきこと {#section_50D49CC52E11414089C89FB67F9B88F5}

* This integration is enabled on new activities when you select to use [!DNL Analytics] as the reporting source. この文書に書かれた実装の変更をおこなっても、既存のアクティビティは影響を受けません。
* The process of setting up [!DNL Analytics] as the reporting source for [!DNL Target] includes several implementation steps, followed by a provisioning step. 実装前に、以下の手順をすべて読んでおくことをお勧めします。After you complete these steps, you will be ready to use [!DNL Analytics] as your reporting source as soon as it is enabled for you. プロビジョニングのプロセスには、最大で 5 営業日かかる場合があります。
* では、 [!DNL Visitor ID service] 複数のコンポーネント間で共有 [!DNL Visitor ID] が作成され [!DNL Adobe Experience Cloud]ます。 Although it does not replace the [!DNL Target] mboxPC id or [!DNL Audience Manager] UUID, it does replace the way [!DNL Analytics] identifies new visitors. If set up properly, returning [!DNL Analytics] visitors should also be identified via their old [!DNL Analytics] ID to prevent visitor cliffing. Similarly, because the [!DNL Target] mboxPCid remains intact, no [!DNL Target] visitor profile data is lost when you upgrade to the [!DNL Visitor ID service].
* と [!DNL Visitor ID service] ページコードの前にを実行 [!DNL Analytics][!DNL Target] する必要があります。 Make sure that `VisitorAPI.js` appears above the tags for all other [!DNL Experience Cloud] solutions.

## 遅延 {#section_9489BE6FD21641A4844E591711E3F813}

After this integration is enabled, you will experience an additional 5-10 minutes of latency in [!DNL Analytics]. This latency increase allows data from [!DNL Analytics] and [!DNL Target] to be stored on the same hit, allowing you to break down activities by page and site section.

This increase is reflected in all [!DNL Analytics] services and tools, including the live-stream and real-time reporting, and applies in the following scenarios:

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標の現在のデータ、ファイナライズされたデータ、データフィードでは、すべてのヒットが追加で 5 ～ 7 分遅延します。

Be aware that the latency increase starts after you implement the [!DNL Experience Cloud] visitor ID service, even if you have not fully implemented this integration.

## 追加の ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

All [!DNL Target] calls used by an A4T activity to deliver content or record the goal metric must have a corresponding [!DNL Analytics] hit that shares the same supplemental ID for A4T to work properly.

Hits that contain data from [!DNL Analytics] and [!DNL Target] contain a supplemental data ID. You can see this ID in the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. 例えば、`sdid=2F3C18E511F618CC-45F83E994AEE93A0` のようになります。この ID は、次の条件が満たされると常に生成されます。

* 訪問者 ID サービスが導入されている
* この統合をサポートするバージョンの [!DNL mbox.js] が導入されている

When troubleshooting, be sure to confirm that the supplemental ID is present on [!DNL Analytics] hits.

## クライアント側分析ログ {#client-side}

デフォルトでは、at.js、[!DNL Experience Cloud Visitor ID Service] および appMeasurement.js がページ上にある場合、前述のように、ページから正しい追加の ID が含まれている限り、[!DNL Analytics] および [!DNL Target] は、レポートおよび分析目的で、バックエンドでイベントを正しくスティッチします。A4T が正しく機能するために、追加の操作を管理および実行する必要はありません。

ただし、[!DNL Target] に関連する分析データをレポート目的で [!DNL Analytics] にいつどのように送信するかをより制御するほうが良い場合があります。社内で活用するための社内分析ツールがあり、社内分析製品を使用して分析データを [!DNL Analytics] に送信したい場合、お客様の組織の他のメンバーが [!DNL Analytics] をビジュアルレポートソースとして引き続き使用できます。詳しくは、*Analytics for Target の実装*&#x200B;の[手順 7： サイトのすべてのページから at.js または mbox.js を参照](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)を参照してください。
