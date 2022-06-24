---
keywords: 実装; 実装方法; 設定; セットアップ; ページパラメーター; Tomcat; URL エンコード; ページ内プロファイル属性; mbox パラメーター; ページ内プロファイル属性; スクリプトプロファイル属性; プロファイル一括更新 API; 単一ファイル更新 API; 顧客属性; データプロバイダー
description: データをに取り込む [!DNL Target] （ページパラメーター、プロファイル属性、スクリプトプロファイル属性、データプロバイダー、単一および一括プロファイル更新 API、顧客属性）。
title: データを Target に送信する方法を教えてください。
feature: Implementation
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 50%

---

# メソッドの概要

データをに取り込むための様々な方法に関する情報 [!DNL Adobe Target].

次のメソッドを使用できます。

| メソッド | 詳細 |
| --- | --- |
| [ページパラメーター](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/page-parameters/){target=_blank}<br>（「mbox パラメーター」とも呼ばれます） | ページパラメーターは、ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。<br>ページパラメーターは、今後のターゲティングで使用するために訪問者のプロファイルと共に保存する必要のないページデータを Target に送信する場合に役立ちます。 これらの値は、ページまたはユーザーが特定のページでおこなったアクションの記述に使用されます。 |
| [ページ内プロファイル属性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/in-page-profile-attributes/){target=_blank}<br>（「in-mbox プロファイル属性」とも呼ばれます） | ページ内パラメーターは、ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されます。<br>ページ内プロファイル属性を利用すると、ユーザー固有のデータを Target のプロファイルに保管し、以降のターゲティングやセグメント化に利用できます。 |
| [スクリプトプロファイル属性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/script-profile-attributes/){target=_blank} | スクリプトプロファイル属性は、Target ソリューションで定義された名前と値のペアです。値は、サーバー呼び出しごとに、Target サーバーで JavaScript スニペットが実行されることで決まります。<br>訪問者がオーディエンスやアクティビティメンバーシップの条件を満たしているかが評価される前に、ユーザーは、mbox 呼び出しごとに実行する簡単なコードスニペットを記述します。 |
| [データプロバイダー](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/data-providers/){target=_blank} | データプロバイダーを使用すると、サードパーティから Target に簡単にデータを渡すことができます。 |
| [プロファイル一括更新 API](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/bulk-profile-update-api/){target=_blank} | API を介して、多数の訪問者のプロファイル更新を含む .csv ファイルを Target に送信します。各訪問者プロファイルでは、1 回の呼び出しで複数のページ内プロファイル属性を更新できます。 |
| [単一プロファイル更新 API](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/single-profile-update-api/){target=_blank} | プロファイル一括更新 API とほとんど同じですが、API 呼び出しで、 .csv ファイルではなく、1 人の訪問者プロファイルが一度に更新されます。 |
| [顧客属性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/customer-attributes/){target=_blank} | 顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。アップロードが完了したら、データをAdobe AnalyticsとAdobe Targetで使用します。 |












