---
keywords: Recommendations
description: Analytics for [!DNL Target] (A4T)の導入に必要な要件と、この統合を実装する前に考慮する必要がある事項について説明します。
title: A4Tを実装する前に知っておくべきこと
feature: Analytics for Target（A4T）
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 31%

---

# at.jsを使用してAnalytics forターゲット(A4T)を実装する前に

[!DNL Adobe Analytics]を[!DNL Adobe Target]のレポートソースとして有効にする場合(A4T)、データ収集プロセスでいくつかの変更が行われます。

この統合を使用する前に、以下の節を確認し、レポートプロセスへの影響を検討してください。

>[!NOTE]
>
>この記事はat.js実装にのみ適用されます。

## 導入に必要な条件 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>A4Tの使用を開始する前に、アカウントが統合用にプロビジョニングされていることを要求する必要があります。 プロビジョニングをリクエストするには、[Marketing Cloud統合プロビジョニングフォーム](https://www.adobe.com/go/audiences)を使用します。

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
* [!DNL Analytics]を[!DNL Target]のレポートソースとして設定するプロセスには、いくつかの実装手順と、プロビジョニング手順が含まれます。 実装前に、以下の手順をすべて読んでおくことをお勧めします。これらの手順を完了したら、[!DNL Analytics]を有効にしたときにレポートソースとして使用する準備が整います。 プロビジョニングのプロセスには、最大で 5 営業日かかる場合があります。
* [!DNL Visitor ID service]は、[!DNL Adobe Experience Cloud]の間に共有[!DNL Visitor ID]を作成します。 [!DNL Target] mboxPC IDまたは[!DNL Audience Manager] UUIDは置き換えませんが、[!DNL Analytics]が新しい訪問者を識別する方法は置き換えられます。 正しく設定されている場合は、[!DNL Analytics]訪問者が返されるのも、古い[!DNL Analytics] IDを使って識別される必要があります。 同様に、[!DNL Target] mboxPCidは元のままなので、[!DNL Visitor ID service]にアップグレードしても[!DNL Target]訪問者プロファイルデータは失われません。
* [!DNL Visitor ID service]は、[!DNL Analytics]および[!DNL Target]ページコードの前に実行する必要があります。 `VisitorAPI.js`は、他のすべての[!DNL Experience Cloud]ソリューションのタグの上に記述します。

## 遅延 {#section_9489BE6FD21641A4844E591711E3F813}

この統合を有効にすると、[!DNL Analytics]に5 ～ 10分の待ち時間が追加で発生します。 この待ち時間の増加により、[!DNL Analytics]と[!DNL Target]のデータを同じヒットに保存して、アクティビティをページ別に、またはサイトセクション別に分類できます。

この増加は、ライブストリームやリアルタイムレポートを含むすべての[!DNL Analytics]サービスおよびツールに反映され、次のシナリオに適用されます。

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標の現在のデータ、ファイナライズされたデータおよびデータフィードでは、すべてのヒットが5 ～ 7分余分に遅延します。

この統合を完全に実装していない場合でも、[!DNL Experience Cloud]訪問者IDサービスを実装した後は、待ち時間が長くなる開始が発生します。

## 追加の ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4Tが正しく機能するためには、A4Tアクティビティがコンテンツを配信したり目標指標を記録するために使用するすべての[!DNL Target]呼び出しに、追加のIDを共有する、対応する[!DNL Analytics]ヒットが必要です。

[!DNL Analytics]と[!DNL Target]のデータを含むヒットには、追加のデータIDが含まれています。 このIDは[Adobe Experience Cloudデバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)では、`sdid`パラメーターとして確認できます。 例えば、`sdid=2F3C18E511F618CC-45F83E994AEE93A0` のようになります。この ID は、次の条件が満たされると常に生成されます。

* 訪問者 ID サービスが導入されている
* この統合をサポートするバージョンの [!DNL mbox.js] が導入されている

[トラブルシューティング](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)を行う場合は、[!DNL Analytics]ヒットに追加のIDが存在することを確認してください。

## クライアント側分析ログ {#client-side}

at.js、[!DNL Experience Cloud Visitor ID Service]およびappMeasurement.jsがページ上にある場合、正しい追加のIDがページに含まれていれば、[!DNL Analytics]および[!DNL Target]は、バックエンドでのレポートと分析の目的でイベントを正しくステッチします。 A4Tが正しく機能するために、追加の操作を管理および実行する必要はありません。

[!DNL Target]に関連する解析データをレポートのために[!DNL Analytics]に送信するタイミングと方法をより詳細に制御したい場合があります。 社内用の解析ツールを使用することもできます。 ただし、社内の解析製品を介して[!DNL Analytics]に解析データを送信し、組織の他のメンバーがビジュアルレポートソースとして引き続き[!DNL Analytics]を使用できるようにすることも必要です。 詳しくは、*Analytics for Target の実装*&#x200B;の[手順 7： サイトのすべてのページから at.js または mbox.js を参照](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)を参照してください。

## 共有オーディエンス

[Marketing Cloud統合プロビジョニングフォーム](https://www.adobe.com/go/audiences)に入力する際は、「[!UICONTROL プロビジョニングを要求する機能を指定してください]?」の下に表示される[!UICONTROL 共有オーディエンス]オプションに関する次の重要な情報に注意してください。

![要求フォーム](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

[!UICONTROL 共有オーディエンス]を要求するとき、[!UICONTROL ターゲット]と[!UICONTROL Adobe Audience Manager] (AAM)を有効にして情報を共有できます。この場合、オーディエンスです。

>[!IMPORTANT]
>
>[!UICONTROL ターゲット]とAAMとの統合には、追加のコストが伴います。 AAMでは、[!UICONTROL ターゲット]呼び出しごとに請求されます。
