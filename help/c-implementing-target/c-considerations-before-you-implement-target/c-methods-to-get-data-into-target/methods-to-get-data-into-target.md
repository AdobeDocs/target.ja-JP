---
keywords: 実装; 実装方法; 設定; セットアップ; ページパラメーター; Tomcat; URL エンコード; ページ内プロファイル属性; mbox パラメーター; ページ内プロファイル属性; スクリプトプロファイル属性; プロファイル一括更新 API; 単一ファイル更新 API; 顧客属性; データプロバイダー
description: データを [!DNL Target] に取り込みます(ページパラメーター、プロファイル属性、スクリプトプロファイル属性、データプロバイダー、単一および一括プロファイル更新API、顧客属性)。
title: ターゲットにデータを取り込む方法
feature: 実装
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 62%

---

# メソッドの概要

[!DNL Adobe Target]にデータを取り込むために使用できる様々な方法に関する情報です。

次の方法を使用できます。

| メソッド | 詳細 |
| --- | --- |
| [ページパラメーター](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>（「mboxパラメーター」とも呼ばれる） | ページパラメーターは、ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。<br>ページパラメーターは、将来的なターゲティングでの使用のために訪問者のプロファイルと共に保存する必要のないページデータをターゲットに送信する場合に役立ちます。これらの値は、ページまたはユーザーが特定のページでおこなったアクションの記述に使用されます。 |
| [ページ内プロファイル属性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>(「in-mboxプロファイル属性」とも呼ばれる) | ページ内パラメーターは、ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されます。<br>ページ内プロファイル属性を利用すると、ユーザー固有のデータを Target のプロファイルに保管し、以降のターゲティングやセグメント化に利用できます。 |
| [スクリプトプロファイル属性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | スクリプトプロファイル属性は、Target ソリューションで定義された名前と値のペアです。値は、サーバー呼び出しごとに、Target サーバーで JavaScript スニペットが実行されることで決まります。<br>訪問者がオーディエンスやアクティビティメンバーシップの条件を満たしているかが評価される前に、ユーザーは、mbox 呼び出しごとに実行する簡単なコードスニペットを記述します。 |
| [データプロバイダー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | データプロバイダーを使用すると、サードパーティからターゲットにデータを簡単に渡すことができます。 |
| [プロファイル一括更新 API](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/bulk-profile-update-api.md) | API を介して、多数の訪問者のプロファイル更新を含む .csv ファイルを Target に送信します。各訪問者プロファイルでは、1 回の呼び出しで複数のページ内プロファイル属性を更新できます。 |
| [単一プロファイル更新 API](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/single-profile-update-api.md) | 一括プロファイル更新APIとほとんど同じですが、API呼び出しの行で、.csvファイルではなく1つの訪問者プロファイルが一度に更新されます。 |
| [顧客属性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/customer-attributes.md) | 顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。アップロードが完了したら、Adobe AnalyticsとAdobe Targetのデータを使用します。 |












