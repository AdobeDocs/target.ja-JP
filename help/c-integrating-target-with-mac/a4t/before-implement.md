---
keywords: Recommendations
description: Analytics を Target のレポートソースとして有効化する場合（A4T）のデータ収集プロセスでいくつかの変更点があります。
title: Adobe TargetのレポートソースとしてAdobe Analyticsを実装する前に(A4T)
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 52%

---


# 実装する前に{#before-you-implement}

[!DNL Analytics]を[!DNL Target]のレポートソースとして有効にする場合(A4T)、データ収集プロセスでいくつかの変更が行われます。

この統合を使用する前に、以降の節を確認して、レポートプロセスへの影響を検討してください。

## 導入に必要な条件 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>A4T を使用する際は、事前にアカウントで統合のプロビジョニングを依頼しておく必要があります。プロビジョニングをリクエストするには、[Marketing Cloud統合プロビジョニングフォーム](https://www.adobe.com/go/audiences)を使用します。

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

ダウンロードと導入の手順は、[ターゲット導入のための解析](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)に記載されています。

## 導入の前に知っておくべきこと {#section_50D49CC52E11414089C89FB67F9B88F5}

* レポートソースとして[!DNL Analytics]を使用することを選択すると、新しいアクティビティでこの統合が有効になります。 この文書に書かれた実装の変更をおこなっても、既存のアクティビティは影響を受けません。
* [!DNL Analytics]を[!DNL Target]のレポートソースとして設定するプロセスには、いくつかの実装手順と、プロビジョニング手順が含まれます。 実装前に、以下の手順をすべて読んでおくことをお勧めします。これらの手順を完了すると、[!DNL Analytics]が有効になり次第、レポートソースとしてを使用する準備が整います。 プロビジョニングのプロセスには、最大で 5 営業日かかる場合があります。
* [!DNL Visitor ID service]は、[!DNL Adobe Experience Cloud]の間に共有[!DNL Visitor ID]を作成します。 [!DNL Target] mboxPC IDまたは[!DNL Audience Manager] UUIDは置き換えませんが、[!DNL Analytics]が新しい訪問者を識別する方法は置き換えられます。 正しく設定されている場合は、訪問者の情報が絶えないように、古い[!DNL Analytics] IDを使用して[!DNL Analytics]訪問者を返す必要もあります。 同様に、[!DNL Target] mboxPCidは元のままなので、[!DNL Visitor ID service]にアップグレードしても[!DNL Target]訪問者プロファイルデータは失われません。
* [!DNL Visitor ID service]は、[!DNL Analytics]および[!DNL Target]ページコードの前に実行する必要があります。 `VisitorAPI.js`は、他のすべての[!DNL Experience Cloud]ソリューションのタグの上に記述します。

## 遅延 {#section_9489BE6FD21641A4844E591711E3F813}

この統合を有効にすると、[!DNL Analytics]に5 ～ 10分の待ち時間が追加で発生します。 この待ち時間の増加により、[!DNL Analytics]と[!DNL Target]のデータを同じヒットに保存して、アクティビティをページ別に、またはサイトセクション別に分類できます。

この増加は、ライブストリームやリアルタイムレポートを含むすべての[!DNL Analytics]サービスおよびツールに反映され、次のシナリオに適用されます。

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標の現在のデータ、ファイナライズされたデータ、データフィードでは、すべてのヒットが追加で 5 ～ 7 分遅延します。

[!DNL Experience Cloud]訪問者IDサービスを実装した後は、この統合を完全に実装していなくても、待ち時間が長くなる開始があることに注意してください。

## 追加の ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4Tが正しく機能するためには、A4Tアクティビティがコンテンツを配信したり目標指標を記録するために使用するすべての[!DNL Target]呼び出しに、同じ追加のIDを共有する、対応する[!DNL Analytics]ヒットが必要です。

[!DNL Analytics]と[!DNL Target]のデータを含むヒットには、追加のデータIDが含まれています。 このIDは[Adobe Experience Cloudデバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)では、`sdid`パラメーターとして確認できます。 例えば、`sdid=2F3C18E511F618CC-45F83E994AEE93A0` のようになります。この ID は、次の条件が満たされると常に生成されます。

* 訪問者 ID サービスが導入されている
* この統合をサポートするバージョンの [!DNL mbox.js] が導入されている

[トラブルシューティング](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)を行う場合は、[!DNL Analytics]ヒットに追加のIDが存在することを確認してください。

## クライアント側分析ログ {#client-side}

デフォルトでは、at.js、[!DNL Experience Cloud Visitor ID Service] および appMeasurement.js がページ上にある場合、前述のように、ページから正しい追加の ID が含まれている限り、[!DNL Analytics] および [!DNL Target] は、レポートおよび分析目的で、バックエンドでイベントを正しくスティッチします。A4T が正しく機能するために、追加の操作を管理および実行する必要はありません。

ただし、[!DNL Target] に関連する分析データをレポート目的で [!DNL Analytics] にいつどのように送信するかをより制御するほうが良い場合があります。社内で活用するための社内分析ツールがあり、社内分析製品を使用して分析データを [!DNL Analytics] に送信したい場合、お客様の組織の他のメンバーが [!DNL Analytics] をビジュアルレポートソースとして引き続き使用できます。詳しくは、*Analytics for Target の実装*&#x200B;の[手順 7： サイトのすべてのページから at.js または mbox.js を参照](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)を参照してください。

## 共有オーディエンス

[Marketing Cloud統合プロビジョニングフォーム](https://www.adobe.com/go/audiences)に入力する際は、「[!UICONTROL プロビジョニングを要求する機能を指定してください]?」の下に表示される[!UICONTROL 共有オーディエンス]オプションに関する次の重要な情報に注意してください。

![要求フォーム](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

[!UICONTROL 共有オーディエンス]を要求するとき、[!UICONTROL ターゲット]と[!UICONTROL Adobe Audience Manager] (AAM)を有効にして情報を共有できます。この場合、オーディエンスです。

>[!IMPORTANT]
>
>[!UICONTROL ターゲット]とAAMとの統合には、追加費用がかかります。 AAMでは、[!UICONTROL ターゲット]呼び出しごとに請求されます。
