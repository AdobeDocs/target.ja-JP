---
keywords: Automated Personalization;ap；データのアップロード；オフラインデータ；パーソナライゼーションアルゴリズム；自動ターゲット；自動ターゲット；ベストプラクティス
description: Adobeでパーソナライゼーションモデルを作成する際に、CRM 情報などのオフラインデータをアップロードする方法を説明します [!DNL Target] Automated Personalization(AP) アクティビティ
title: パーソナライゼーションアルゴリズムのデータをアップロードするにはどうすればよいですか？
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3ac61272ee1ccd72a8670966f181e7798cbe9f76
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 67%

---

# のデータをアップロード [!DNL Target] パーソナライゼーションアルゴリズム

CRM 情報や顧客のチャーン傾向スコアなどのオフラインデータは、でパーソナライゼーションモデルを構築する際に非常に重要になる可能性があります。 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) アクティビティ

[!UICONTROL Automated Personalization]（AP）および [!UICONTROL 自動ターゲット] のパーソナライゼーションアルゴリズムにデータを入力する方法はいくつかあります。のメソッドに加えて、 [データを Target に送信する方法](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}, Experience Cloud shared audiences (Adobe Analytics, Audience Management){target=_blank} また、アクティビティ内レポート用オーディエンスもアルゴリズムで使用されます。

自動的に収集され、Automated Personalization および自動ターゲットのパーソナライゼーションアルゴリズムで使用されるデータについて詳しくは、「[Automated Personalization のデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)」を参照してください。

## ベストプラクティス {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

Target のパーソナライゼーションアルゴリズムのデータをアップロードするためのベストプラクティスを以下に示します。

* Target のパーソナライゼーションアルゴリズムで使用できる高品質データが増えれば増えるほど、AP および自動ターゲットアクティビティで結果として生成されるモデルの品質が向上します。
* 同じ目的を果たす複数のプロファイルスクリプトまたは属性の使用を制限します。
* セッション ID などの固有の ID は、必要ない限り渡しません。
* Target で自動的に収集されるデータ（[Target のパーソナライゼーションアルゴリズムのデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)）を確認し、重複する情報を送信しないようにします。例えば、Target では IPアドレスを使用して訪問者の郵便番号を推定します。この情報を別個の変数として渡す必要はありません。
* 同じ属性／変数に複数の値を渡しません。複数の変数が連結されている場合、Target のパーソナライゼーションアルゴリズムでは各文字列を一意の値として扱い、パーソナライゼーションの情報の値を小さくします。
* 覚えやすく意味のある命名規則を使用して、[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)をわかりやすくします。
