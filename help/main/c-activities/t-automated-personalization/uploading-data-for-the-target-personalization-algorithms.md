---
keywords: Automated Personalization;ap；データのアップロード；オフラインデータ；パーソナライゼーションアルゴリズム；自動ターゲット；自動ターゲット；ベストプラクティス
description: '[!DNL Adobe Target] [!UICONTROL Automated Personalization] （AP）および[!UICONTROL 自動ターゲット &#x200B;] アクティビティでパーソナライゼーションモデルを構築する際にオフラインデータをアップロードする方法について説明します。'
title: Personalization アルゴリズムのデータをアップロードするにはどうすればよいですか？
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
TQID: 'https://experienceleague.adobe.com/B1vwWrii4DfQzXftwcmgzbhBkDAZFo5mDRn3a7dULj0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 18%
---
# [!DNL Target] パーソナライゼーションアルゴリズムのデータのアップロード

[!DNL Adobe Target] [!UICONTROL Automated Personalization] （AP）および[!UICONTROL 自動ターゲット &#x200B;] アクティビティでパーソナライゼーションモデルを構築する場合、CRM情報や顧客解約傾向スコアなどのオフラインデータは、非常に価値があります。

[!UICONTROL Automated Personalization] （AP）および[!UICONTROL 自動ターゲット &#x200B;] パーソナライゼーションアルゴリズムでデータを入力するには、いくつかの方法があります。 [Targetにデータを取り込む方法](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}、[!DNL Experience Cloud]の共有オーディエンス （[!UICONTROL Adobe Analytics]、[!DNL Audience Manager]）およびアクティビティ内レポートオーディエンスの方法に加えて、[!DNL Target] アルゴリズムでも使用されています。

[!UICONTROL Automated Personalization]および[!UICONTROL 自動ターゲット &#x200B;]のパーソナライゼーションアルゴリズムによって自動的に収集および使用されるデータについて詳しくは、[Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md)を参照してください。

## ベストプラクティス {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

次のリストは、[!DNL Target]個のパーソナライゼーションアルゴリズムのデータをアップロードするためのベストプラクティスを示しています。

* [!DNL Target]個のパーソナライゼーションアルゴリズムで利用できる高品質なデータが多ければ多いほど、[!UICONTROL Automated Personalization]および[!UICONTROL 自動ターゲット &#x200B;] アクティビティで生成されるモデルの品質が向上します。
* 同じ目的を果たす複数のプロファイルスクリプトまたは属性の使用を制限します。
* セッション IDなどの一意のIDは、必要に応じて渡さないでください。
* 重複したデータを送信しないように、[!DNL Target]が自動的に収集するデータ （[TargetのPersonalization アルゴリズムのデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)）を確認します。 例えば、[!DNL Target]はIP アドレスを使用して、訪問者の郵便番号を決定します。 この情報を別個の変数として渡す必要はありません。
* 同じ属性または変数に複数の値を渡さないでください。 複数の変数が連結されている場合、[!DNL Target]個のパーソナライゼーションアルゴリズムは、各文字列を一意の値として扱い、パーソナライゼーション用の情報の値を減らします。
* 覚えやすくて意味のある命名規則を使用して、[Personalization インサイトレポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)をより理解しやすくします。
