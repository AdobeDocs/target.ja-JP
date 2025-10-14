---
keywords: Automated Personalization;AP；データのアップロード；オフラインデータ；パーソナライゼーションアルゴリズム；自動ターゲット；自動ターゲット；ベストプラクティス
description: ' [!DNL Adobe Target] [!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] アクティビティでパーソナライゼーションモデルを作成する際にオフラインデータをアップロードする方法を説明します。'
title: Personalization アルゴリズムのデータをアップロードするにはどうすればよいですか？
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 13%

---

# [!DNL Target] パーソナライゼーションアルゴリズム用のデータのアップロード

CRM 情報や顧客のチャーン傾向スコアなどのオフラインデータは、[!DNL Adobe Target] [!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] アクティビティでパーソナライゼーションモデルを構築する際に非常に役立つ可能性があります。

[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] のパーソナライゼーションアルゴリズムでデータを入力する方法はいくつかあります。 [&#x200B; データを Target に送信する方法 &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank} の方法に加えて、共有オーディエンス（[!DNL Experience Cloud]、[!UICONTROL Adobe Analytics]）およびアクティビティ内レポートオーディエンスの [!DNL Audience Manager] も、[!DNL Target] アルゴリズムで使用されます。

[!UICONTROL Automated Personalization] および [!UICONTROL Auto-Target] パーソナライゼーションアルゴリズムによって自動的に収集および使用されるデータについて詳しくは、[Automated Personalizationのデータ収集 &#x200B;](/help/main/c-activities/t-automated-personalization/ap-data.md) を参照してください。

## ベストプラクティス {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

パーソナライゼーションアルゴリズム用のデータをアップロードする際のベストプラクティスを次 [!DNL Target] 示します。

* パーソナライゼーションアルゴリズムに使用できる高品質のデータが多いほど、[!DNL Target] ークフローと [!UICONTROL Automated Personalization] アクティビティにおける結果モデルの品質が高く [!UICONTROL Auto-Target] ります。
* 同じ目的を果たす複数のプロファイルスクリプトまたは属性の使用を制限します。
* 不要な場合は、セッション ID などの一意の ID を渡さないでください。
* 重複し [!DNL Target] 情報を送信しないように、自動的に収集するデータ（[Target のPersonalization アルゴリズムのデータ収集 &#x200B;](/help/main/c-activities/t-automated-personalization/ap-data.md)）を確認します。 例えば、[!DNL Target] では IP アドレスを使用して訪問者の郵便番号を判断します。 この情報を別個の変数として渡す必要はありません。
* 同じ属性または変数内に複数の値を渡さないでください。 複数の変数が連結されている場合、パーソナライゼーションアルゴリズム [!DNL Target] 各文字列を一意の値として扱い、パーソナライゼーションの情報の値を減らします。
* [Personalization Insights レポートを理解しやすくするために、覚えやすく意味のある命名規則 &#x200B;](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) 使用します。
