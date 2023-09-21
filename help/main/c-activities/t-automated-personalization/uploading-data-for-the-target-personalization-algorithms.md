---
keywords: Automated Personalization;ap；データのアップロード；オフラインデータ；パーソナライゼーションアルゴリズム；自動ターゲット；自動ターゲット；ベストプラクティス
description: でパーソナライゼーションモデルを構築する際に、オフラインデータをアップロードする方法を説明します。 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) および [!UICONTROL 自動ターゲット] アクティビティ。
title: パーソナライゼーションアルゴリズムのデータをアップロードするにはどうすればよいですか？
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 26%

---

# のデータをアップロード [!DNL Target] パーソナライゼーションアルゴリズム

CRM 情報や顧客のチャーン傾向スコアなどのオフラインデータは、でパーソナライゼーションモデルを構築する際に非常に重要になる可能性があります。 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) および [!UICONTROL 自動ターゲット] アクティビティ。

[!UICONTROL Automated Personalization]（AP）および [!UICONTROL 自動ターゲット] のパーソナライゼーションアルゴリズムにデータを入力する方法はいくつかあります。のメソッドに加えて、 [データを Target に送信する方法](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}, [!DNL Experience Cloud] 共有オーディエンス ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) やアクティビティ内レポート用オーディエンスも [!DNL Target] アルゴリズム。

自動的に収集され、[!UICONTROL Automated Personalization] および[!UICONTROL 自動ターゲット]のパーソナライゼーションアルゴリズムで使用されるデータについて詳しくは、「[Automated Personalization のデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)」を参照してください。

## ベストプラクティス {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

次のリストは、のデータアップロードのベストプラクティスを示しています。 [!DNL Target] パーソナライゼーションアルゴリズム：

* より高品質なデータを [!DNL Target] パーソナライゼーションアルゴリズムを使用すると、結果として生成されるモデルの品質が向上します。 [!UICONTROL Automated Personalization] および [!UICONTROL 自動ターゲット] アクティビティ。
* 同じ目的を果たす複数のプロファイルスクリプトまたは属性の使用を制限します。
* 必要がない場合は、セッション ID などの一意の ID を渡さないでください。
* データの確認 [!DNL Target] を自動的に収集 ( [Target のパーソナライゼーションアルゴリズムのデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)) を使用して、重複する情報を送信しないようにします。 例： [!DNL Target] は IP アドレスを使用して訪問者の郵便番号を判断します。 この情報を別個の変数として渡す必要はありません。
* 同じ属性または変数に複数の値を渡さないでください。 複数の変数が連結されている場合、 [!DNL Target] パーソナライゼーションアルゴリズムは、各文字列を一意の値として扱い、パーソナライゼーションのための情報の価値を減らします。
* 覚えやすく意味のある命名規則を使用して、 [パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) 理解しやすくなる。
