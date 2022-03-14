---
description: モバイルアプリ訪問者にAdobeなエクスペリエンスを表示するための Mobile SDK の使用方法を説明します。
title: 方法 [!DNL Target] モバイルアプリで作業する場合
feature: Implement Mobile
role: Developer
exl-id: 1a5f34dc-932d-47c7-b730-6d1658343fb4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 84%

---

# 方法 [!DNL Target] は、モバイルアプリで機能します

Adobe Mobile SDK は、ユーザーに適切なエクスペリエンスを表示するため、Target サーバーに接続してコンテンツと他のデータポイントを取得します。

## ターゲットの場所と成功指標 {#section_A08AAB0ABA9C4568A5AFD4D27EF1CE74}

*ターゲットの場所* はmboxとも呼ばれます。アプリで識別した場所は、テストとパーソナライゼーション（例えば、ホーム画面のようこそメッセージ）のために有効になります。これらの場所は、テスト作成プロセスの間に識別されます。

*[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)*&#x200B;はユーザーが実行するアクションで、特定のアクティビティが成功したかどうか（サインアップ、購入、チケットの予約など）を識別します。

![](assets/mobile-target-location.png)

* **Target の場所：**&#x200B;登録ボタンの下に表示されるコンテンツ。

   このユーザーは、18 時まで送料無料の提供を受けています。この場所は、A/B テストとパーソナライゼーションを実行するために、複数の Target アクティビティで再利用することができます。

* **成功指標**：ユーザーが登録ボタンをタップするという、ユーザーによって実行されるアクション。

**SDK における Target の仕組み**

![](assets/how-target-mobile-works.png)
