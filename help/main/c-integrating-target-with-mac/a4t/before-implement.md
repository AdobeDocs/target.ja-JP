---
keywords: Recommendations
description: Analytics for Analytics の実装要件について説明します。 [!DNL Target] (A4T) と、この統合を実装する前に考慮すべき事項について説明します。
title: A4T を実装する前に知っておくべきこと
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 26%

---

# at.js を使用して Analytics for Target（A4T）を実装する前に

を有効にする際、データ収集プロセスでいくつかの変更がおこなわれます。 [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T)。

この統合を使用する前に、以下の節を確認し、レポートプロセスへの影響を検討してください。

>[!NOTE]
>
>この記事は、at.js の実装にのみ適用されます。

## 導入に必要な条件 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>A4T の使用を開始する前に、アカウントで統合のプロビジョニングを依頼する必要があります。 以下を使用： [Marketing Cloud統合プロビジョニングフォーム](https://www.adobe.com/go/audiences) プロビジョニングの依頼。

この A4T 統合では、A4T でリダイレクトオファーを使用するかどうかに応じて、次のバージョン以降のライブラリを実装する必要があります。

>[!NOTE]
>
>以下の要件で、 *最小* at.js のバージョンは、A4T の実装に必要です。 この [!DNL Target] チームが管理しているのは 2 つのバージョンのみ [!DNL at.js] — 現在のバージョンと 2 番目の最新バージョン。 必要に応じて [!DNL at.js] をアップグレードし、サポート対象のバージョンを使用するようにしてください。各バージョンについて詳しくは、 [at.js のバージョンの詳細](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)を参照してください。

### A4T でリダイレクトオファーを使用 *しない* 場合に必要な要件

この統合で、A4T でのリダイレクトオファーを使用しない場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js バージョン 1.8.0
* [!DNL Adobe Target]: at.js バージョン 0.9.1
* Adobe Analytics：appMeasurement.js バージョン 1.7.0

を使用した A4T の実装に関する情報 [!DNL Platform Web SDK]を参照してください。 [Adobe Experience Platform Web SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

### A4T でリダイレクトオファーを使用する場合に必要な要件

A4T でリダイレクトオファーを使用する場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js バージョン 2.3.0

   >[!NOTE]
   >
   >at.js 1.8.0+ および at.js 2.x+ は、Adobe Audience Manager（AAM）パラメーターを渡す際、2.5.0 よりも古いバージョンの訪問者 API では動作しなくなりました。

* [!DNL Adobe Target]: at.js バージョン 1.6.2

* Adobe Analytics：appMeasurement.js バージョン 2.1

ダウンロードおよびデプロイの手順については、 [Analytics for Target の実装](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

を使用した A4T の実装に関する情報 [!DNL Platform Web SDK]を参照してください。 [Adobe Experience Platform Web SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

## 導入の前に知っておくべきこと {#section_50D49CC52E11414089C89FB67F9B88F5}

* この統合は、「 [!DNL Analytics] を使用します。 この文書に書かれた実装の変更をおこなっても、既存のアクティビティは影響を受けません。
* 設定のプロセス [!DNL Analytics] レポートソースとして [!DNL Target] には、いくつかの実装手順と、その後のプロビジョニング手順が含まれます。 実装前に、以下の手順をすべて読んでおくことをお勧めします。これらの手順を完了すると、次の操作を実行する準備が整います。 [!DNL Analytics] を使用できます。 プロビジョニングのプロセスには、最大で 5 営業日かかる場合があります。
* この [!DNL Visitor ID service] 共有を作成 [!DNL Visitor ID] 横に [!DNL Adobe Experience Cloud]. ただし、 [!DNL Target] mboxPC id または [!DNL Audience Manager] UUID の場合、 [!DNL Analytics] は新しい訪問者を識別します。 を適切に設定した場合、 [!DNL Analytics] 訪問者は、以前の [!DNL Analytics] ID。 同様に、 [!DNL Target] mboxPCid は元の状態のまま残り、 [!DNL Target] 訪問者プロファイルデータは、 [!DNL Visitor ID service].
* この [!DNL Visitor ID service] は、 [!DNL Analytics] および [!DNL Target] ページコード。 必ず `VisitorAPI.js` は、他のすべてのタグの上に表示されます [!DNL Experience Cloud] ソリューション

## 遅延 {#section_9489BE6FD21641A4844E591711E3F813}

この統合を有効にすると、で 5～10 分の待ち時間が余分に発生します。 [!DNL Analytics]. この待ち時間の増加により、 [!DNL Analytics] および [!DNL Target] を同じヒットに保存し、アクティビティをページおよびサイトセクションで分類できます。

この増加は、 [!DNL Analytics] ライブストリームおよびリアルタイムレポートを含むサービスおよびツール。次のシナリオで適用されます。

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標、ファイナライズされたデータおよびデータフィードの現在のデータに関しては、すべてのヒットが 5 ～ 7 分延長されます。

待ち時間は、 [!DNL Experience Cloud] 訪問者 ID サービス（この統合を完全に実装していない場合でも）。

## 追加の ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

すべて [!DNL Target] コンテンツの配信や目標指標の記録をおこなうために A4T アクティビティで使用される呼び出しには、対応する [!DNL Analytics] A4T が正しく機能するために追加の ID を共有するヒット。

からのデータを含むヒット [!DNL Analytics] および [!DNL Target] には、追加のデータ ID が含まれています。 この ID は、 [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) を `sdid` パラメーター。 例えば、`sdid=2F3C18E511F618CC-45F83E994AEE93A0` のようになります。この ID は、次の条件が満たされると常に生成されます。

* 訪問者 ID サービスが導入されている

条件 [トラブルシューティング](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)を使用する場合は、必ず、追加の ID がに存在することを確認してください。 [!DNL Analytics] ヒット数。

## クライアント側分析ログ {#client-side}

at.js の場合、 [!DNL Experience Cloud Visitor ID Service]、および appMeasurement.js がページ上にある場合、 [!DNL Analytics]、および [!DNL Target] ページから正しい追加の ID が含まれている限り、バックエンドで reporting and analytics 目的でイベントを正しくステッチします。 A4T が正しく機能するために、追加の操作を管理および実行する必要はありません。

分析データの送信方法とタイミングをより詳細に制御する必要がある場合は、 [!DNL Target] から [!DNL Analytics] レポート目的で使用します。 社内で使用する社内分析ツールがある場合があります。 ただし、分析データをに送信する必要もあります。 [!DNL Analytics] 社内分析製品を使用して、組織の他のメンバーが引き続きを使用できるようにする [!DNL Analytics] ビジュアルレポートソースとして。 詳しくは、 [手順 7:サイトのすべてのページから at.js を参照します。](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) in *Analytics for Target の実装* を参照してください。

## 共有オーディエンス

を [Marketing Cloud統合プロビジョニングフォーム](https://www.adobe.com/go/audiences)に関しては、 [!UICONTROL 共有オーディエンス] &quot;の下にリストされたオプション[!UICONTROL プロビジョニングをリクエストする機能]?」

![リクエストフォーム](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

リクエスト時 [!UICONTROL 共有オーディエンス]、 [!UICONTROL ターゲット] および [!UICONTROL Adobe Audience Manager] (AAM) で情報を共有する場合。この場合、オーディエンス。

>[!IMPORTANT]
>
>この [!UICONTROL ターゲット] AAMには追加費用がかかります。 お客様には、 [!UICONTROL ターゲット] AAMでを呼び出します。
