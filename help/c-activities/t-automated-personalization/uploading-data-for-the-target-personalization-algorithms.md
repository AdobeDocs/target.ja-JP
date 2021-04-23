---
keywords: Automated Personalization；アップロードデータ；オフラインデータ；パーソナライゼーションアルゴリズム；自動ターゲット；自動ターゲット；ベストプラクティス
description: Adobe [!DNL Target] Automated Personalization(AP)アクティビティでパーソナライゼーションモデルを作成する場合、CRM情報など、オフラインデータをアップロードする方法を説明します。
title: パーソナライゼーションアルゴリズム用にデータをアップロードする方法を教えてください。
feature: 自動パーソナライゼーション
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 75%

---

# [!DNL Target]パーソナライゼーションアルゴリズム用のデータのアップロード

CRM情報や顧客チャーンの傾向スコアなどのオフラインデータは、[!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)アクティビティでパーソナライゼーションモデルを作成する際に非常に役立ちます。

[!UICONTROL Automated Personalization]（AP）および [!UICONTROL 自動ターゲット] のパーソナライゼーションアルゴリズムにデータを入力する方法はいくつかあります。[データを Target に送信する方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)で紹介している方法の他に、Experience Cloud 共有オーディエンス（Adobe Analytics、Audience Management）やアクティビティ内レポート用オーディエンスも使用されます。

自動的に収集され、Automated Personalization および自動ターゲットのパーソナライゼーションアルゴリズムで使用されるデータについて詳しくは、「[Automated Personalization のデータ収集](/help/c-activities/t-automated-personalization/ap-data.md)」を参照してください。

## ベストプラクティス {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

Target のパーソナライゼーションアルゴリズムのデータをアップロードするためのベストプラクティスを以下に示します。

* Target のパーソナライゼーションアルゴリズムで使用できる高品質データが増えれば増えるほど、AP および自動ターゲットアクティビティで結果として生成されるモデルの品質が向上します。
* 同じ目的を果たす複数のプロファイルスクリプトまたは属性の使用を制限します。
* セッション ID などの固有の ID は、必要ない限り渡しません。
* Target で自動的に収集されるデータ（[Target のパーソナライゼーションアルゴリズムのデータ収集](/help/c-activities/t-automated-personalization/ap-data.md)）を確認し、重複する情報を送信しないようにします。例えば、Target では IPアドレスを使用して訪問者の郵便番号を推定します。この情報を別個の変数として渡す必要はありません。
* 同じ属性／変数に複数の値を渡しません。複数の変数が連結されている場合、Target のパーソナライゼーションアルゴリズムでは各文字列を一意の値として扱い、パーソナライゼーションの情報の値を小さくします。
* 覚えやすく意味のある命名規則を使用して、[パーソナライゼーションインサイトレポート](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)をわかりやすくします。
