---
description: Analytics を Target のレポートソースとして有効化する場合（A4T）のデータ収集プロセスでいくつかの変更点があります。
keywords: Recommendations
seo-description: Analytics を Target のレポートソースとして有効化する場合（A4T）のデータ収集プロセスでいくつかの変更点があります。
seo-title: 実装する前にAdobe Target のレポートソースとしての Adobe Analytics（A4T）
solution: 'Target '
title: 実装する前に
topic: Premium
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# 実装する前に{#before-you-implement}

Analytics を Target のレポートソースとして有効化する場合（A4T）のデータ収集プロセスでいくつかの変更点があります。

この統合を使用する前に、以降の節を確認して、レポートプロセスへの影響を検討してください。

## 導入に必要な条件 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>A4T を使用する際は、事前にアカウントで統合のプロビジョニングを依頼しておく必要があります。プロビジョニングの依頼には[このフォーム](https://www.adobe.com/go/audiences)を使用します。

この A4T 統合では、A4T でリダイレクトオファーを使用するかどうかに応じて、次のバージョン以降のライブラリを実装する必要があります。

### A4T でリダイレクトオファーを使用 *しない* 場合に必要な要件

この統合で、A4T でのリダイレクトオファーを使用しない場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* Experience Cloud 訪問者 ID サービス：visitorAPI.js バージョン 1.8.0
* Adobe Target（実装によって異なります）：at.js バージョン 0.9.1 または mbox.js バージョン 61
* Adobe Analytics：appMeasurement.js バージョン 1.7.0

### A4T でリダイレクトオファーを使用する場合に必要な要件

A4T でリダイレクトオファーを使用する場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* Experience Cloud 訪問者 ID サービス：visitorAPI.js バージョン 2.3.0
* Adobe Target：at.js バージョン 1.6.2

   **注意：** mbox.js ライブラリは A4T によるリダイレクトオファーをサポートしていません。実装では at.js を使用する必要があります。

* Adobe Analytics：appMeasurement.js バージョン 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## 導入の前に知っておくべきこと {#section_50D49CC52E11414089C89FB67F9B88F5}

* Analytics をレポートソースとして使用することを選択すると、新しいアクティビティで統合が有効になります。この文書に書かれた実装の変更をおこなっても、既存のアクティビティは影響を受けません。
* Analytics を Target のレポートソースとして設定するには、いくつかの実装手順をおこなった後、プロビジョニングの手順を実行します。実装前に、以下の手順をすべて読んでおくことをお勧めします。以下に示すすべての手順を実行すると、オプションが有効化され次第、Analytics をレポートソースとして使用できるようになります。プロビジョニングのプロセスには、最大で 5 営業日かかる場合があります。
* Visitor ID サービスは Experience Cloud 全体で有効な 1 つの訪問者 ID を生成します。Target mboxPC ID または Audience Manager UUID は置き換えませんが、Analytics が新規訪問者と識別する方法を置き換えます。適切にセットアップすると、訪問者を複数回カウントすることを避けるために、Analytics の訪問者も、古い Analytics ID を使用して識別されます。同様に、Target mboxPCid は元の状態のままなので、Visitor ID サービスにアップグレードしても Target 訪問者プロファイルデータは失われません。
* Visitor ID サービスは、Analytics と Target のページコードの前に実行する必要があります。`VisitorAPI.js` は、必ず他のすべての Experience Cloud 製品のためのタグよりも前に参照してください。

## 遅延 {#section_9489BE6FD21641A4844E591711E3F813}

この統合を有効にすると、Adobe Analytics で 5～10 分の待ち時間が追加で発生します。この追加の待ち時間は、Analytics と Target からのデータを同じヒットに格納することによって、ページおよびサイトセクションによってテストを分類できるようにするためのものです。

この追加の待ち時間は、ライブストリームやリアルタイムレポートなどのすべての Adobe Analytics サービスおよびツールで発生します。追加の待ち時間が発生する対象となるヒットは次のとおりです。

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標の現在のデータ、ファイナライズされたデータ、データフィードでは、すべてのヒットが追加で 5 ～ 7 分遅延します。

この統合を完全に実装していなくても、Experience Cloud Visitor ID サービスを導入すると追加の待ち時間が発生することに注意してください。

## 追加の ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4T が正しく機能するためには、A4T アクティビティがコンテンツを配信したり目標指標を記録したりするために使用するすべての Target 呼び出しに、同じ追加の ID を共有する、対応する Analytics ヒットが必要です。

Analytics および Target からのデータを含むヒットには、追加のデータ ID が含まれています。You can see this ID in the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. 例えば、`sdid=2F3C18E511F618CC-45F83E994AEE93A0` のようになります。この ID は、次の条件が満たされると常に生成されます。

* 訪問者 ID サービスが導入されている
* この統合をサポートするバージョンの [!DNL mbox.js] が導入されている

トラブルシューティングをおこなう場合は、Analytics のヒットに追加の ID があることを確認してください。

## クライアント側分析ログ {#client-side}

デフォルトでは、at.js、[!DNL Experience Cloud Visitor ID Service] および appMeasurement.js がページ上にある場合、前述のように、ページから正しい追加の ID が含まれている限り、[!DNL Adobe Analytics] および [!DNL Target] は、レポートおよび分析目的で、バックエンドでイベントを正しくスティッチします。A4T が正しく機能するために、追加の操作を管理および実行する必要はありません。

ただし、[!DNL Target] に関連する分析データをレポート目的で [!DNL Analytics] にいつどのように送信するかをより制御するほうが良い場合があります。社内で活用するための社内分析ツールがあり、社内分析製品を使用して分析データを [!DNL Analytics] に送信したい場合、お客様の組織の他のメンバーが [!DNL Analytics] をビジュアルレポートソースとして引き続き使用できます。詳しくは、*Analytics for Target の実装*&#x200B;の[手順 7： サイトのすべてのページから at.js または mbox.js を参照](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)を参照してください。
