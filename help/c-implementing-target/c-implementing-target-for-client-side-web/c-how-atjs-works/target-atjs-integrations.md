---
keywords: at.js integration;supported integrations;unsupported integrations;third party integrations
description: Target の一般的な統合と at.js のサポート状況について説明します。
title: at.js の統合
feature: client-side
topic: Standard
uuid: 19036a1d-941c-4d31-8c7b-f50c86996b1c
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 90%

---


# at.js の統合{#at-js-integrations}

[!DNL Target] の一般的な統合と at.js のサポート状況について説明します。

サポートされていない統合やここに記載されていない統合を切実に必要としている場合は、担当のアカウント担当者またはコンサルタントにお問い合わせください。

## サポートされる統合 {#section_3B44A970D3FB42D1973701452C868B55}

| 統合 | 詳細 |
|--- |--- |
| Analytics for Target（A4T） | 「[Adobe Target のレポートソースとしての Adobe Analytics（A4T）](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)」を参照してください。 |
| プロファイルおよびオーディエンス（P&amp;A） | 『 [コアサービスユーザガイド](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) 』の *オーディエンスを参照してください*。 |
| Experience Cloud ID サービス | [Adobe Experience Cloud ID サービスのドキュメント](https://docs.adobe.com/content/help/en/id-service/using/home.html)を参照してください。 |
| Adobe Launch | Launch は、アドビの次世代のタグ管理プラットフォームで、Adobe Target を実装するための推奨される方法です。Launch は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告のタグをデプロイおよび管理するためのシンプルな手段を提供します。「[Adobe Launch を使用した Target の実装](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25)」を参照してください。 |
| Dynamic Tag Management（DTM） | See the [Best Practices for Implementing Target Using Dynamic Tag Management guide](https://docs.adobe.com/content/help/en/dtm/implementing/overview.html).   重要： [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) は、Target および at.js ライブラリを実装するための、最新の推奨される方法です。Target を新たに実装する場合は、Launch を使用してください。以下のガイドは、DTM 実装を使用している既存のお客様向けのものです。DTM 統合を使用する際には、次の点を考慮してください。 <ul><li>ライブラリ管理：at.js を使用するには、「カスタム」ホスティングオプションを使用します。自動管理は現在サポートされていません。 </li></ul> |
| Adobe Experience Manager（AEM）クラウドサービス | AEM クラウドサービスを使用すると、AEM ワークフロー内で A/B テストおよびエクスペリエンスのターゲット設定アクティビティを作成できます。at.js は、FP-11577（またはそれ以降）が適用された Adobe Experience Manager 6.2 でサポートされます。詳しくは、[Adobe Target との統合](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html)を参照し、対象の AEM バージョンを選択してください。 |
| AEM エクスペリエンスフラグメント | AEM で作成したエクスペリエンスフラグメントを Target アクティビティで使用すると、AEM の使いやすさおよび機能性と、Target の強力な自動インテリジェンス（AI）機能および機械学習（ML）機能を組み合わせ、幅広くエクスペリエンスをテストしてパーソナライズできます。AEM では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。デバイスごとにページを作成する必要はありません。コンテンツを基に、各デバイスのエクスペリエンスが自動調整されます。「[AEM エクスペリエンスフラグメント](../../../c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8)」を参照してください。 |

## サポートされない統合 {#section_8EFCAED418DC42E0B07F95924819EAC2}

| 統合 | 詳細 |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | この統合では、[!DNL SiteCatalyst] UI でレポートを実行できるように、ページ呼び出しを使用してキャンペーンおよびレシピ ID を [!DNL SiteCatalyst] に送信しました。この機能は、A4T によって置き換えられます。 |
| [!DNL Legacy Target to SiteCatalyst Integration] | この統合では、eVar および prop に基づいて成功指標およびユーザープロファイルを構築できるように、`"SiteCatalyst: Event"` および `"SiteCatalyst: Purchase"` という mbox 呼び出しを作成しました。この機能は、A4T および P&amp;A によって置き換えられます。 |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | この統合では、フロントエンド API 呼び出しを作成して AAM セグメントを取得し、それらをページの各 mbox 呼び出しの mbox パラメーターとして送信しました。 |

## サードパーティ統合 {#section_EE599839CCAD49DD97640E5EDAD9082E}

| 統合 | 詳細 |
|--- |--- |
| 他のタグマネージャー | at.js は、アドビ以外のタグ管理プラットフォームで使用する必要がありますが、他のベンダーが開発したカスタム統合機能の使用には注意してください。そうした統合は、もう at.js には存在しない内部 mbox.js 関数に依存している可能性があります。 |
| サードパーティデータプロバイダー（Demandbase、BlueKai、weather API など） | Target のユーザープロファイリングを補完するために使用される多くのサードパーティデータプロバイダーは、at.js の[データプロバイダー](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)機能を使用して統合することができます。. |