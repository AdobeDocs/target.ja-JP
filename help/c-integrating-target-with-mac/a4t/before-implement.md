---
keywords: Recommendations
description: Analytics for [!DNL Target] (A4T)の実装要件と、この統合を実装する前に考慮すべき事項について説明します。
title: A4Tを実装する前に知っておくべきことは何ですか？
feature: Analytics for Target（A4T）
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 51e36576439ff365bbdac14da67cb971c36431d6
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 26%

---

# at.js を使用して Analytics for Target（A4T）を実装する前に

[!DNL Adobe Target]のレポートソースとして[!DNL Adobe Analytics]を有効にする場合(A4T)、データ収集プロセスでいくつかの変更がおこなわれました。

この統合を使用する前に、以下の節を確認し、レポートプロセスへの影響を検討してください。

>[!NOTE]
>
>この記事はat.js実装にのみ適用されます。

## 導入に必要な条件 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>A4Tの使用を開始する前に、アカウントで統合のプロビジョニングを依頼する必要があります。 プロビジョニングの依頼には、[Marketing Cloud統合プロビジョニングフォーム](https://www.adobe.com/go/audiences)を使用します。

この A4T 統合では、A4T でリダイレクトオファーを使用するかどうかに応じて、次のバージョン以降のライブラリを実装する必要があります。

### A4T でリダイレクトオファーを使用 *しない* 場合に必要な要件

この統合で、A4T でのリダイレクトオファーを使用しない場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.jsバージョン1.8.0
* [!DNL Adobe Target]: at.js バージョン 0.9.1
* Adobe Analytics：appMeasurement.js バージョン 1.7.0

### A4T でリダイレクトオファーを使用する場合に必要な要件

A4T でリダイレクトオファーを使用する場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.jsバージョン2.3.0

   >[!NOTE]
   >
   >at.js 1.8.0以降およびat.js 2.x以降は、Adobe Audience Manager(AAM)パラメーターを渡すために、2.5.0より前のバージョンの訪問者APIでは動作しなくなりました。

* [!DNL Adobe Target]: at.js バージョン 1.6.2

* Adobe Analytics：appMeasurement.js バージョン 2.1

ダウンロードおよび導入の手順は、[Analytics for Targetの実装](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)に記載されています。

## 導入の前に知っておくべきこと {#section_50D49CC52E11414089C89FB67F9B88F5}

* この統合は、新しいアクティビティで、レポートソースとして[!DNL Analytics]を使用するように選択すると有効になります。 この文書に書かれた実装の変更をおこなっても、既存のアクティビティは影響を受けません。
* [!DNL Analytics]を[!DNL Target]のレポートソースとして設定するプロセスには、いくつかの実装手順と、プロビジョニング手順が含まれます。 実装前に、以下の手順をすべて読んでおくことをお勧めします。これらの手順を完了したら、[!DNL Analytics]を有効にしたときにレポートソースとして使用する準備が整います。 プロビジョニングのプロセスには、最大で 5 営業日かかる場合があります。
* [!DNL Visitor ID service]は、[!DNL Adobe Experience Cloud]間の共有[!DNL Visitor ID]を作成します。 [!DNL Target] mboxPC idまたは[!DNL Audience Manager] UUIDは置き換えませんが、[!DNL Analytics]が新しい訪問者を識別する方法を置き換えます。 適切にセットアップした場合、[!DNL Analytics]の再訪問者も、古い[!DNL Analytics] IDを使用して識別される必要があります。 同様に、 [!DNL Target] mboxPCidは元の状態のままなので、 [!DNL Visitor ID service]にアップグレードしても、[!DNL Target]訪問者プロファイルデータは失われません。
* [!DNL Visitor ID service]は、[!DNL Analytics]と[!DNL Target]ページコードの前に実行する必要があります。 `VisitorAPI.js`は、必ず他のすべての[!DNL Experience Cloud]ソリューションのタグよりも前に置いてください。

## 遅延 {#section_9489BE6FD21641A4844E591711E3F813}

この統合を有効にすると、[!DNL Analytics]に5～10分の待ち時間が追加で発生します。 この追加の待ち時間は、[!DNL Analytics]と[!DNL Target]のデータを同じヒットに格納することで、ページおよびサイトセクションでアクティビティを分類できるようにするためのものです。

この増加は、ライブストリームおよびリアルタイムレポートを含む、すべての[!DNL Analytics]サービスおよびツールに反映され、次のシナリオに適用されます。

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標の現在のデータ、ファイナライズされたデータおよびデータフィードに関しては、すべてのヒットが5 ～ 7分間延長されます。

この統合を完全に実装していなくても、[!DNL Experience Cloud]訪問者IDサービスを導入すると追加の待ち時間が発生します。

## 追加の ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4Tが正しく機能するには、A4Tアクティビティがコンテンツを配信したり目標指標を記録したりするために使用するすべての[!DNL Target]呼び出しに、追加のIDを共有する、対応する[!DNL Analytics]ヒットが必要です。

[!DNL Analytics]および[!DNL Target]のデータを含むヒットには、追加のデータIDが含まれます。 このIDは、[Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)で`sdid`パラメーターとして確認できます。 例えば、`sdid=2F3C18E511F618CC-45F83E994AEE93A0` のようになります。この ID は、次の条件が満たされると常に生成されます。

* 訪問者 ID サービスが導入されている

[トラブルシューティング](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)を行う際は、[!DNL Analytics]ヒットに追加のIDが存在することを確認してください。

## クライアント側分析ログ {#client-side}

at.js、[!DNL Experience Cloud Visitor ID Service]およびappMeasurement.jsがページ上にある場合、正しい追加IDがページから含まれている限り、[!DNL Analytics]および[!DNL Target]は、バックエンドでのレポートおよび分析目的でイベントを正しくステッチします。 A4Tが正しく機能するために、追加の操作を管理および実行する必要はありません。

[!DNL Target]に関連する分析データをレポート目的で[!DNL Analytics]に送信するタイミングと方法をより詳細に制御する必要が生じる場合があります。 社内で使用する社内分析ツールがある場合があります。 ただし、社内分析製品を使用して[!DNL Analytics]に分析データを送信し、組織の他のメンバーが引き続き[!DNL Analytics]をビジュアルレポートソースとして使用できるようにする必要もあります。 [手順7を参照してください。詳しくは、*TargetのAnalyticsの実装*&#x200B;のすべてのサイトページ](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)でat.jsを参照してください。

## 共有オーディエンス

[Marketing Cloud統合プロビジョニングフォーム](https://www.adobe.com/go/audiences)に入力する際は、「[!UICONTROL プロビジョニングをリクエストする機能]?」の下に表示される[!UICONTROL 共有オーディエンス]オプションに関する次の重要な情報に注意してください。

![リクエストフォーム](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

[!UICONTROL 共有オーディエンス]をリクエストする場合、[!UICONTROL Target]および[!UICONTROL Adobe Audience Manager](AAM)で情報を共有できます。この場合、オーディエンスは共有されます。

>[!IMPORTANT]
>
>[!UICONTROL Target]とAAMとの統合には、追加のコストがかかります。 AAMでは、[!UICONTROL Target]呼び出しごとに請求されます。
