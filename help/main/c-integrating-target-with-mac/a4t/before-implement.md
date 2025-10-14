---
keywords: レコメンデーション
description: Analytics for  [!DNL Target] （A4T）の実装要件と、この統合を実装する前に考慮すべき事項について学びます。
title: A4T を実装する前に知っておくべきこと
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 656f728ba890f1f5afc0404e22f6acb1a2565fe6
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 87%

---

# at.js を使用して Analytics for Target（A4T）を実装する前に

[!DNL Adobe Target]（A4T）のレポートソースとして [!DNL Adobe Analytics] を有効にすると、データ収集プロセスでいくつかの変更が発生します。

この統合の使用を決定する前に、以降の節を確認し、レポートプロセスへの影響を検討してください。

>[!NOTE]
>
>この記事は、at.js 実装にのみ適用されます。 [!UICONTROL Analytics for Target] を使用した [!DNL Adobe Experience Platform Web SDK] （A4T）の実装については、[Experience Platform Web SDKのAdobe Analytics for Target （A4T）のログ &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/a4t/overview-a4t.html?lang=ja){target=_blank} を参照してください。

## 実装の必要システム構成 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>A4T の使用を開始する前に、事前にアカウントで統合のプロビジョニングを依頼しておく必要があります。[Marketing Cloud統合プロビジョニングフォーム &#x200B;](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} を使用して、プロビジョニングを依頼します。

この A4T 統合では、A4T でリダイレクトオファーを使用するかどうかに応じて、次のバージョン以降のライブラリを実装する必要があります。

>[!NOTE]
>
>次の要件は、A4T を実装するために必要な at.js の&#x200B;*最小*&#x200B;バージョンを表示します。[!DNL Target] チームがサポートを提供しているのは、[!DNL at.js] の最新バージョンとその 1 つ前のバージョンの 2 つのみです。必要に応じて [!DNL at.js] をアップグレードし、サポート対象のバージョンを使用するようにしてください。各バージョンについて詳しくは、 [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank}を参照してください。

### A4T でリダイレクトオファーを使用 *しない* 場合に必要な要件

この統合で、A4T でのリダイレクトオファーを使用しない場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* [!DNL Experience Cloud Visitor ID Service]：visitorAPI.js バージョン 1.8.0
* [!DNL Adobe Target]: at.js バージョン 0.9.1
* Adobe Analytics：appMeasurement.js バージョン 1.7.0

[!DNL Platform Web SDK] を使用した A4T の実装については、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} を参照してください。

### A4T でリダイレクトオファーを使用する場合に必要な要件

A4T でリダイレクトオファーを使用する場合は、次のバージョン以降のライブラリを実装する必要があります。リストされている順序は、操作の順序です。

* [!DNL Experience Cloud Visitor ID Service]：visitorAPI.js バージョン 2.3.0

  >[!NOTE]
  >
  >at.js 1.8.0+ および at.js 2.x+ は、Adobe Audience Manager（AAM）パラメーターを渡す際、2.5.0 よりも古いバージョンの訪問者 API では動作しなくなりました。

* [!DNL Adobe Target]: at.js バージョン 1.6.2

* Adobe Analytics：appMeasurement.js バージョン 2.1

ダウンロードおよびデプロイメントの手順については、[Analytics for Target 実装](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)に記載されています。

[!DNL Platform Web SDK] を使用した A4T の実装については、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} を参照してください。

## 実装の前に知っておくべきこと {#section_50D49CC52E11414089C89FB67F9B88F5}

* [!DNL Analytics] をレポートソースとして使用することを選択すると、新しいアクティビティで統合が有効になります。この文書に書かれた実装の変更をおこなっても、既存のアクティビティは影響を受けません。
* [!DNL Analytics] を [!DNL Target] のレポートソースとして設定するプロセスには、いくつかの実装ステップと、それに続くプロビジョニングのステップが含まれます。実装前に、以下の手順をすべて読んでおくことをお勧めします。これらの手順を完了すると、[!DNL Analytics] が有効になったときにレポートソースとして使用できるようになります。プロビジョニングのプロセスには、最大で 5 営業日かかる場合があります。
* [!DNL Visitor ID service] は、[!DNL Adobe Experience Cloud] をまたいで共有 [!DNL Visitor ID] を作成します。[!DNL Target] mboxPC ID や [!DNL Audience Manager] UUID は置き換えませんが、[!DNL Analytics] が新しい訪問者を識別する方法を置き換えます。適切に設定されている場合、[!DNL Analytics] の再訪問者も古い [!DNL Analytics] ID で識別される必要があります。同様に、[!DNL Target] mboxPCid は元の状態のままなので、[!DNL Visitor ID service] にアップグレードしても [!DNL Target] 訪問者プロファイルデータは失われません。
* [!DNL Visitor ID service] は、[!DNL Analytics] および [!DNL Target] ページコードの前に実行する必要があります。他のすべての [!DNL Experience Cloud] ソリューションのタグの上に `VisitorAPI.js` が表示されていることを確認してください。

## 遅延 {#section_9489BE6FD21641A4844E591711E3F813}

この統合を有効にすると、[!DNL Analytics] で 5～10 分の待ち時間が追加で発生します。この追加の待ち時間により、[!DNL Analytics] と [!DNL Target] のデータを同じヒットに格納できるため、ページおよびサイトセクションによってアクティビティを分類できるようになりました。

この追加の待ち時間は、ライブストリームやリアルタイムレポートなど、すべての [!DNL Analytics] サービスおよびツールに反映され、以下のシナリオで適用されます。

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標の現在のデータ、ファイナライズされたデータ、データフィードでは、すべてのヒットが追加で 5～7 分遅延します。

この統合を完全に実装していなくても、[!DNL Experience Cloud] 訪問者 ID サービスを実装すると追加の待ち時間が発生します。

## 追加の ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

コンテンツを配信したり目標指標を記録したりするために A4T アクティビティで使用されるすべての [!DNL Target] 呼び出しには、A4T が正しく機能するための補足 ID を共有する、対応する [!DNL Analytics] ヒットが必要です。

[!DNL Analytics] および [!DNL Target] からのデータを含むヒットには、追加のデータ ID が含まれています。この ID は、[Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja) で `sdid` パラメーターとして確認できます。例えば、`sdid=2F3C18E511F618CC-45F83E994AEE93A0` のようになります。この ID は、次の条件が満たされると常に生成されます。

* 訪問者 ID サービスが導入されている

[トラブルシューティング](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)を行う場合は、[!DNL Analytics] のヒットに追加の ID が存在することを確認してください。

## クライアントサイド分析ログ {#client-side}

at.js、[!DNL Experience Cloud Visitor ID Service] および appMeasurement.js がページ上にある場合、ページから正しい追加の ID が含まれている限り、[!DNL Analytics] および [!DNL Target] は、レポートおよび分析目的で、バックエンドでイベントを正しくスティッチします。A4T が正しく機能するための、追加の操作を管理および実行する必要はありません。

レポートの目的で、[!DNL Target] に関連する分析データをいつどのように [!DNL Analytics] に送信するかを、より詳細に制御したい場合があります。内部目的で使用する社内分析ツールがある場合があります。ただし、組織の他のメンバーがビジュアルレポートソースとして [!DNL Analytics] を引き続き使用できるように、社内の分析製品経由で [!DNL Analytics] に分析データを送信したい場合もあります。詳しくは、*Analytics for Target 実装*&#x200B;の[ステップ 7：サイトのすべてのページから at.js を参照](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)を参照してください。

## 共有オーディエンス

[Marketing Cloud統合プロビジョニングフォーム &#x200B;](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} に入力する場合、「[!UICONTROL Shared Audiences]?」の下にリストされている [!UICONTROL For which capabilities are you requesting provisioning] オプションに関する以下の重要事項にご注意ください。

![リクエストフォーム](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

[!UICONTROL Shared Audiences] をリクエストするとき、[!UICONTROL Target] と [!UICONTROL Adobe Audience Manager] （AAM）を有効にして情報を共有します。この場合はオーディエンスです。

>[!IMPORTANT]
>
>[!UICONTROL Target] とAAMの統合には追加の費用がかかります。 AAMの [!UICONTROL Target] 呼び出し毎に請求されます。
