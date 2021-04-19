---
keywords: 実装；javascriptライブラリ；js;atjs;on-device decisioning;on device decisioning;at.js;on-device;on-device;on-device
description: at.jsライブラリを使用してオンデバイス判定を実行する方法を学びます。
title: オンデバイス判定はat.js JavaScriptライブラリとどのように連携しますか。
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
translation-type: tm+mt
source-git-commit: dba3044c94502ea9e25b21a3034dc581de10f431
workflow-type: tm+mt
source-wordcount: '3506'
ht-degree: 7%

---

# at.jsのオンデバイス判定

>[!NOTE]
>
>オンデバイス判定は、今後の[at.js 2.5.0リリース](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)で利用可能になります。 近日発表予定。

バージョン2.5.0以降、at.jsオファーのOn-Device Decisioningを使用しています。 オンデバイス判定機能を使用すると、[A/Bテスト](/help/c-activities/t-test-ab/test-ab.md)と[エクスペリエンスターゲット設定](/help/c-activities/t-experience-target/experience-target.md)(XT)アクティビティをブラウザーにキャッシュして、[!DNL Adobe Target] Edge Networkに対するネットワーク要求をブロックせずにメモリ内判定を実行できます。

[!DNL Target] また、実験環境や機械学習主導（ML方式）のパーソナライゼーションアクティビティから、ライブサーバーコールを介して最も関連性の高い最新のエクスペリエンスを提供する柔軟性もオファーに提供します。つまり、パフォーマンスが最も重要な場合は、オンデバイスの判定を使用することを選択できます。 ただし、最も関連性の高い最新のML駆動のエクスペリエンスが必要な場合は、代わりにサーバーコールを実行できます。

## on-device decisioningの利点

オンデバイス判定の利点は次のとおりです。

* **迅速な意思決定と経験の提供。** グループ化と判定は、ネットワーク要求のブロックを避けるために、メモリ内およびブラウザー上で実行されます。
* **アプリケーションのパフォーマンスを強化します。** エンドユーザーの操作性を損なうことなく、テストを実行し、顧客とユーザーにパーソナライズを提供します。
* **Googleサイトの品質スコアの改善。** 判定がメモリ内で行われるので、オンラインビジネスのGoogleサイトの品質スコアを向上させ、消費者がより検出しやすくします。
* **リアルタイム分析から学習します。** Analytics forターゲット [](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)レポートを使用して、アクティビティのパフォーマンスからのインサイトをリアルタイムで取得します。A4Tを使用すると、重要な時点で戦略をピボットできます。

## サポートされる機能

Adobe TargetJS SDKを使用すると、お客様は柔軟にデータのパフォーマンスと鮮度を選択して判断できます。 つまり、機械学習を通じて最も関連性が高く魅力的なパーソナライズされたコンテンツを配信することが最も重要な場合は、ライブサーバーコールを行う必要があります。 ただし、パフォーマンスがより重要な場合は、デバイス上およびメモリ内の判断を行う必要があります。 オンデバイス判定が機能するようにするには、次に示すサポートされる機能のリストを参照してください。

* アクティビティのタイプ
* オーディエンスのターゲット設定
* 配分方法

詳しくは、[オンデバイス判定でサポートされている機能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)を参照してください。

## オンデバイス判定の仕組み

オンデバイス判定が有効なat.jsをデプロイして初期化すると、A/BおよびXTアクティビティ、オーディエンス、アセットのオンデバイス判定を含む[ルールアーティファクト](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)が、訪問者に最も近いAkamai CDNからダウンロードされ、訪問者のブラウザーにローカルにキャッシュされます。 エクスペリエンスを取得するためにat.jsからリクエストが行われると、キャッシュされたルールアーティファクトでエンコードされたメタデータに基づいて、どのエクスペリエンスを返すかに関する決定がメモリ内で行われます。

## 判定方法

オンデバイス判定では、[!DNL Target]に「[!UICONTROL 判定方法]」という新しい設定が導入されます。 [!UICONTROL 判定方法]の設定は、at.jsがエクスペリエンスを提供する方法を指示します。 [!UICONTROL 判定] 方式には次の3つの値があります。

* [!UICONTROL サーバー側のみ]
* [!UICONTROL デバイス上のみ]
* [!UICONTROL ハイブリッド]

### サーバー側のみ

[!UICONTROL サーバー側] のみが、at.js 2.5.0以降が実装されWebプロパティにデプロイされた場合に初期設定で設定されるデフォルトの判定方法です。

[!UICONTROL サーバー側のみ]をデフォルト設定として使用すると、[!DNL Target]エッジネットワーク上ですべての決定が行われ、ブロッキングサーバーコールが行われます。 このアプローチは遅延を増加させる可能性がありますが、[Recommendations](/help/c-recommendations/recommendations.md)、[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)、[自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)アクティビティを含むターゲットの機械学習機能を適用できるなど、大きなメリットもあります。

さらに、セッションやチャネルを超えて持続するターゲットのユーザープロファイルを使用してパーソナライズされたエクスペリエンスを強化することで、ビジネスに強力な成果をもたらすことができます。

最後に、[!UICONTROL サーバ側のみ]では、Audience ManagerやAdobe Analyticsのセグメントを通じてターゲットにできるオーディエンスを、Adobe Experience Cloudを使用して微調整できます。

次の図は、訪問者、ブラウザー、at.js 2.5.0以降、およびAdobe Targetエッジネットワーク間のやり取りを示しています。 このフロー図は、新しい訪問者と再訪問者をキャプチャします。

![サーバー側のみのフロー図](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

次のリストは、図の数値に対応しています。

| 手順 | 説明 |
| --- | --- |
| 1 | [!DNL Experience Cloud Visitor ID]は[Adobe Experience CloudIDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)から取得されます。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>   at.jsライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して、非同期で読み込むこともできます。 |
| 3 | at.jsライブラリは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | ページ読み込みリクエストが実行され、(ECID、顧客ID、カスタムパラメーター、ユーザープロファイルなど)設定済みのすべてのパラメーターが含まれます。 |
| 5 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。<br>プロファイルストアは、オーディエンスライブラリから正規のオーディエンス(例えば、、から共有するオーディエンスなど) [!DNL Adobe Analytics]を要求 [!DNL Adobe Audience Manager]します。<br>顧客属性がバッチ処理でプロファイルストアに送信されます。 |
| 6 | プロファイルストアは、オーディエンスの資格やグループ化に使用してアクティビティをフィルタリングします。 |
| 7 | 結果のコンテンツは、ライブ[!DNL Target]アクティビティからエクスペリエンスを決定した後に選択されます。 |
| 8 | at.jsライブラリは、レンダリングする必要があるエクスペリエンスに関連付けられているページ上の対応する要素を非表示にします。 |
| 9 | at.jsライブラリには本文が表示され、訪問者から表示への移行のために残りのページを読み込むことができます。 |
| 10 | at.jsライブラリはDOMを操作して、ターゲットエッジネットワークからエクスペリエンスをレンダリングします。 |
| 11 | エクスペリエンスは、訪問者に対してレンダリングされます。 |
| 12 | Webページ全体が読み込まれます。 |
| 13 | [!DNL Analytics] データがデータ収集サーバーに送信されます。 |
| 14 | ターゲットデータは、SDIDを介して[!DNL Analytics]データと照合され、[!DNL Analytics]レポートストレージに処理されます。 [!DNL Analytics] for [!DNL Analytics]（A4T）レポートを使用して、[!DNL Target] データが [!UICONTROL Analytics および ]Target に表示できるようになります。 |

### デバイス上のみ

[!UICONTROL オンデバイス] は、オンデバイスの判定をWebページ全体でのみ使用する場合にat.js 2.5.0以降で設定する必要がある判定方法のみです。

オンデバイスの判定では、エクスペリエンスとパーソナライズアクティビティを超高速で配信できます。これは、オンデバイスの判定に適したすべてのアクティビティを含むキャッシュされたルールアーティファクトが決定に反映されるからです。

デバイス上での判定に適したアクティビティの詳細については、[デバイス上での判定でサポートされる機能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)を参照してください。

この判定方法は、[!DNL Target]からの決定を必要とするすべてのページでパフォーマンスが非常に重要な場合にのみ使用してください。 さらに、この判定方法を選択した場合、デバイス上の判定に該当しない[!DNL Target]アクティビティは配信も実行もされないことに注意してください。 at.jsライブラリ2.5.0以降は、決定を行うためにキャッシュされたルールアーティファクトのみを検索するように設定されています。

次の図に、訪問者、ブラウザー、at.js 2.5.0以上、Akamai CDN間のインタラクションを示します。 Akamai CDNは、訪問者の最初の訪問用にルールのアーティファクトをキャッシュします。 新しい訪問者の最初のページ訪問では、JSONルールのアーティファクトをAkamai CDNからダウンロードして、訪問者のブラウザーにローカルにキャッシュする必要があります。 JSONルールのアーティファクトがダウンロードされた後、ネットワーク呼び出しをブロックせずに、即座に決定が行われます。 次のフロー図は、新しい訪問者を示しています。

![デバイス上のみのフロー図](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

次のリストは、図の数値に対応しています。

>[!NOTE]
>
>[!DNL Adobe Target] 管理サーバーは、オンデバイスの判定に適したすべてのアクティビティを認定し、JSONルールアーティファクトを生成して、Akamai CDNに伝えます。新しいJSONルールのアーティファクトを出力し、Akamai CDNに伝達するための更新がアクティビティーで継続的に監視されます。

| 手順 | 説明 |
| --- | --- |
| 3 | [!DNL Experience Cloud Visitor ID]は[Adobe Experience CloudIDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html)から取得されます。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.jsライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して、非同期で読み込むこともできます。 |
| 3 | at.jsライブラリは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | at.jsライブラリは、訪問者に最も近いAkamai CDNからJSONルールのアーティファクトを取得するようリクエストします。 |
| 5 | Akamai CDNはJSONルールのアーティファクトで応答します。 |
| 6 | JSONルールのアーティファクトが訪問者のブラウザー上でローカルにキャッシュされます。 |
| 7 | at.jsライブラリは、JSONルールのアーティファクトを解釈し、エクスペリエンスを取得する決定を実行し、テスト対象の要素を非表示にします。 |
| 8 | at.jsライブラリには本文が表示され、訪問者から表示への移行のために残りのページを読み込むことができます。 |
| 9 | at.jsライブラリはDOMを操作して、キャッシュされたJSONルールのアーティファクトからエクスペリエンスをレンダリングします。 |
| 10 | エクスペリエンスは、訪問者に対してレンダリングされます。 |
| 11 | Webページ全体が読み込まれます。 |
| 12 | [!DNL Analytics] データがデータ収集サーバーに送信されます。ターゲットデータは、SDIDを介して[!DNL Analytics]データと照合され、[!DNL Analytics]レポートストレージに処理されます。 [!DNL Analytics][!DNL Analytics]A4T レポートを使用して、 データが と の両方に表示できるようになります。[!DNL Target] |

次の図は、訪問者、at.js 2.5.0以降、および訪問者の後続のページヒットまたは再訪問に対するキャッシュされたJSONルールアーティファクトの間のインタラクションを示しています。 JSONルールのアーティファクトは既にキャッシュされ、ブラウザーで使用できるので、ネットワーク呼び出しをブロックせずに、即座に決定されます。 次のフロー図は、後続のページナビゲーションまたは再訪問者をキャプチャします。

![後続のページナビゲーションと再訪問のためのデバイス上のみのフロー図](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

次のリストは、図の数値に対応しています。

>[!NOTE]
>
>[!DNL Adobe Target] 管理サーバーは、オンデバイスの判定に適したすべてのアクティビティを認定し、JSONルールアーティファクトを生成して、Akamai CDNに伝えます。新しいJSONルールのアーティファクトを出力し、Akamai CDNに伝達するための更新がアクティビティーで継続的に監視されます。

| 手順 | 説明 |
| --- | --- |
| 1 | [!DNL Experience Cloud Visitor ID]は[Adobe Experience CloudIDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html)から取得されます。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.jsライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して、非同期で読み込むこともできます。 |
| 3 | at.jsライブラリは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | at.jsライブラリは、JSONルールのアーティファクトを解釈し、メモリ内の決定を実行してエクスペリエンスを取得します。 |
| 5 | テストされた要素は非表示になります。 |
| 6 | at.jsライブラリには本文が表示され、訪問者から表示への移行のために残りのページを読み込むことができます。 |
| 7 | at.jsライブラリはDOMを操作して、キャッシュされたJSONルールのアーティファクトからエクスペリエンスをレンダリングします。 |
| 8 | エクスペリエンスは、訪問者に対してレンダリングされます。 |
| 9 | Webページ全体が読み込まれます。 |
| 10 | [!DNL Analytics] データがデータ収集サーバーに送信されます。ターゲットデータは、SDIDを介して[!DNL Analytics]データと照合され、[!DNL Analytics]レポートストレージに処理されます。 [!DNL Analytics] for [!DNL Analytics]（A4T）レポートを使用して、[!DNL Target] データが [!UICONTROL Analytics および ]Target に表示できるようになります。 |

### ハイブリッド

[!UICONTROL Adobe Targetエッジネットワークへのネットワーク呼び出しを必要とするオンデバイス判定とアクティビティの両方を実行する必要がある場合に、at.js 2.5.0以降で設定する必要がある判定方式を] Hybridis社が使用します。

オンデバイス判定アクティビティとサーバーサイドアクティビティの両方を管理している場合、[!DNL Target]をページにデプロイしてプロビジョニングする方法を考えると、少し複雑で面倒な場合があります。 ハイブリッドを判定方式として使用する場合、[!DNL Target]は、サーバ側での実行が必要なアクティビティに対して、いつサーバーがAdobe Targetエッジネットワークを呼び出す必要があるか、また、デバイス上での判断のみを実行する必要があるかを知っています。

JSONルールのアーティファクトには、mboxがサーバー側のアクティビティーを実行しているか、またはデバイス上の判定アクティビティが実行されているかをat.jsに通知するメタデータが含まれます。 迅速に配信するアクティビティは、オンデバイスの判定によって行われ、より強力なML駆動型パーソナライゼーションを必要とするアクティビティでは、これらのアクティビティはAdobe Targetエッジネットワークを介して行われます。

次の図に、訪問者、ブラウザー、at.js 2.5.0以降、Akamai CDN、Adobe Targetエッジネットワーク間での、初めてページを訪問する新しい訪問者のインタラクションを示します。 この図から取り除くと、JSONルールのアーティファクトは、Adobe Targetエッジネットワークを介して決定が行われる間は非同期でダウンロードされます。

この方法では、多数のアクティビティを含む可能性のあるアーティファクトのサイズが、決定の待ち時間に悪影響を与えないようにします。 JSONルールのアーティファクトを同期的にダウンロードして、その後決定する場合も、遅延に悪影響を与え、一貫性に欠ける場合があります。 したがって、ハイブリッド判定の方法は、新しい訪問者に対する決定に対するサーバー側の呼び出しを常に行い、JSONルールアーティファクトが並行してキャッシュされるようにするベストプラクティスの推奨です。 それ以降のページ訪問回数および再来訪では、JSONルールのアーティファクトを介してキャッシュとメモリ内から決定が行われます。

![初回訪問者のハイブリッドフロー図](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

次のリストは、図の数値に対応しています。

>[!NOTE]
>
>[!DNL Adobe Target] 管理サーバーは、オンデバイスの判定に適したすべてのアクティビティを認定し、JSONルールアーティファクトを生成して、Akamai CDNに伝えます。新しいJSONルールのアーティファクトを出力し、Akamai CDNに伝達するための更新がアクティビティーで継続的に監視されます。

| 手順 | 説明 |
| --- | --- |
| 3 | [!DNL Experience Cloud Visitor ID]は[Adobe Experience CloudIDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html)から取得されます。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.jsライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して、非同期で読み込むこともできます。 |
| 1 | at.jsライブラリは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | ページ型リクエストは、(ECID、顧客ID、カスタムパラメーター、ユーザープロファイルなどの設定済みのすべてのパラメーターを含む、Adobe Targetエッジネットワークに対して行われます。 |
| 5 | 同時に、at.jsは、訪問者に最も近いAkamai CDNからJSONルールのアーティファクトを取得するリクエストを行います。 |
| 6 | (Adobe Targetエッジネットワーク)プロファイルスクリプトを実行し、プロファイルストアにフィードします。 プロファイルストアは、オーディエンスライブラリ(例えば、[!DNL Adobe Analytics]、[!DNL Adobe Audience Manager]などから共有されたオーディエンス)から正規のオーディエンスを要求します。 |
| 7 | Akamai CDNはJSONルールのアーティファクトで応答します。 |
| 8 | プロファイルストアは、オーディエンスの資格やグループ化に使用してアクティビティをフィルタリングします。 |
| 9 | 結果のコンテンツは、ライブ[!DNL Target]アクティビティからエクスペリエンスを決定した後に選択されます。 |
| 10 | at.jsライブラリは、レンダリングする必要があるエクスペリエンスに関連付けられているページ上の対応する要素を非表示にします。 |
| 11 | at.jsライブラリには本文が表示され、訪問者から表示への移行のために残りのページを読み込むことができます。 |
| 12 | at.jsライブラリはDOMを操作して、ターゲットエッジネットワークからエクスペリエンスをレンダリングします。 |
| 13 | エクスペリエンスは、訪問者に対してレンダリングされます。 |
| 14 | Webページ全体が読み込まれます。 |
| 15 | [!DNL Analytics] データがデータ収集サーバーに送信されます。ターゲットデータは、SDIDを介して[!DNL Analytics]データと照合され、[!DNL Analytics]レポートストレージに処理されます。 [!DNL Analytics] for [!DNL Analytics]（A4T）レポートを使用して、[!DNL Target] データが [!UICONTROL Analytics および ]Target に表示できるようになります。 |

次の図は、訪問者、at.js 2.5.0以降、および後続のページナビゲーションまたは再来訪に使用するキャッシュされたJSONルールのアーティファクトの間でのインタラクションを示しています。 この図では、後続のページナビゲーションまたは再訪問に対してデバイス上の判断が行われる場合のみに焦点を当てます。 特定のページに対してライブなアクティビティが存在するかどうかに応じて、サーバ側の呼び出しを行って、サーバ側の判断を実行できます。

![後続のページナビゲーションと再訪問のハイブリッドフロー図](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

次のリストは、図の数値に対応しています。

>[!NOTE]
>
>[!DNL Adobe Target] 管理サーバーは、オンデバイスの判定に適したすべてのアクティビティを認定し、JSONルールアーティファクトを生成して、Akamai CDNに伝えます。新しいJSONルールのアーティファクトを出力し、Akamai CDNに伝達するための更新がアクティビティーで継続的に監視されます。

| 手順 | 説明 |
| --- | --- |
| 1 | [!DNL Experience Cloud Visitor ID]は[Adobe Experience CloudIDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html)から取得されます。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.jsライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して、非同期で読み込むこともできます。 |
| 1 | at.jsライブラリは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | エクスペリエンスを取得するリクエストが作成されます。 |
| 5 | at.jsライブラリは、JSONルールのアーティファクトが既にキャッシュされていることを確認し、メモリ内の決定を実行してエクスペリエンスを取得します。 |
| 6 | テストされた要素は非表示になります。 |
| 7 | at.jsライブラリには本文が表示され、訪問者から表示への移行のために残りのページを読み込むことができます。 |
| 8 | at.jsライブラリはDOMを操作して、キャッシュされたJSONルールのアーティファクトからエクスペリエンスをレンダリングします。 |
| 9 | エクスペリエンスは、訪問者に対してレンダリングされます。 |
| 10 | Webページ全体が読み込まれます。 |
| 11 | [!DNL Analytics] データがデータ収集サーバーに送信されます。ターゲットデータは、SDIDを介して[!DNL Analytics]データと照合され、[!DNL Analytics]レポートストレージに処理されます。 [!DNL Analytics] for [!DNL Analytics]（A4T）レポートを使用して、[!DNL Target] データが [!UICONTROL Analytics および ]Target に表示できるようになります。 |

## オンデバイスの判定を有効にする方法を教えてください。

オンデバイス判定は、At.js 2.5.0以降を使用するすべての[!DNL Target]ユーザーが利用できます。

オンデバイス判定を有効にするには：

>[!NOTE]
>
>オンデバイス判定の切り替えを有効または無効にするには、[!UICONTROL 管理者]または[!UICONTROL 承認者] [ユーザーの役割](/help/administrating-target/c-user-management/user-management.md)が必要です。

1. **[!UICONTROL 管理]**/**[!UICONTROL 導入]**/**[!UICONTROL アカウントの詳細]**&#x200B;をクリックします。
1. 「**[!UICONTROL アカウントの詳細]**」で、**[!UICONTROL デバイス上での判定]**&#x200B;を「オン」の位置に切り替えます。

   ![オンデバイス判定の切り替え](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   オンデバイスの判定を有効にすると、「[!UICONTROL 既存のすべてのオンデバイスの判定修飾アクティビティをアーティファクトに含める]」オプションが表示されます。
1. （条件付き）デバイス上の判定に適したすべてのライブターゲットアクティビティを自動的にアーティファクトに含める場合は、切り替えを「オン」の位置にスライドします。

   このトグルをオフにしたままにすると、生成されたルールのアーティファクトに含めるには、オンデバイス判定アクティビティを再作成してアクティブ化する必要があります。 つまり、[!UICONTROL デバイス上での判定]トグルをオンにする前のライブ状態のアクティビティは、ルールのアーティファクトに含まれません。

[!UICONTROL デバイス上での判定]の切り替えを有効にした後、[!DNL Target]がクライアントの[ルールアーティファクト](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)の生成と伝播を開始します。

>[!IMPORTANT]
>
>オンデバイス判定を使用するようにAdobe TargetSDKを初期化する前に、切り替えを有効にしてください。 ルールのアーティファクトは、まずAkamai CDNを生成して、オンデバイスの判定機能を動作させるために伝播する必要があります。 最初のルールアーティファクトが生成されAkamai CDNに反映されるまでに5 ～ 10分かかる場合があります。

## on-device decisioningを使用するためにat.js 2.5.0以降を設定する方法を教えてください。

1. **[!UICONTROL 管理]**/**[!UICONTROL 導入]**/**[!UICONTROL アカウントの詳細]**&#x200B;をクリックします。
1. **[!UICONTROL 実装メソッド]**/**[!UICONTROL 主な実装メソッド]**&#x200B;の下で、at.jsバージョンの横にある「**[!UICONTROL 編集]**」をクリックします（at.js 2.5.0以降にする必要があります）。

   ![主な実装方法の設定の編集](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >これらのデフォルト設定を変更する前に、現在の実装に影響を与えないように、ClientCareにお問い合わせください。

1. 目的の判定方法を選択します。

   * [!UICONTROL サーバー側のみ]
   * [!UICONTROL デバイス上のみ]
   * [!UICONTROL ハイブリッド]

   ![at.js設定パネルの編集](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### グローバル設定

すべての[!DNL Target]決定に対して、デフォルトの[!UICONTROL 決定方法]を設定できます。 様々な判定方法は、[!UICONTROL サーバー側のみ]、[!UICONTROL オンデバイスのみ]、[!UICONTROL ハイブリッド]です。 ターゲットUIで選択された判定方式は、`decisioningMethod`フィールドの`window.targetGlobalSettings`で設定されます。 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)の`decisioningMethod`についての詳細。

```javascript
<head> 
    <script type="text/javascript">

        window.targetGlobalSettings = { 
            clientCode: "yourClientCodeHere", 
            imsOrgId: "imsOrgId@AdobeOrg", 
            decisioningMethod: "on-device"

        }; 
    </script>

    <script type="text/javascript" src="at.js"></script> 
</head>
```

### カスタマイズされた設定

`decisioningMethod`を`window.targetGlobalSettings`に設定し、使用事例に従ってAdobe Targetの判断を上書きしたい場合は、At.js2.5.0+の[getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)呼び出しで`decisioningMethod`を指定して、この手順を実行できます。`decisioningMethod`

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
});
```

>[!NOTE]
>
>「on-device」または「hybrid」をgetOffers()呼び出しの判定メソッドとして使用するには、グローバル設定に`decisioningMethod`が「on-device」または「hybrid」として含まれていることを確認します。 at.jsライブラリ2.5.0以降は、JSONルールアーティファクトをページに読み込んだ後すぐにダウンロードしてキャッシュするかどうかを知っている必要があります。 グローバル設定の判定方法が「サーバー側」に設定され、「on-device」または「hybrid」判定メソッドがgetOffers()呼び出しに渡される場合、at.js 2.5.0+では、JSONルールアーティファクトがキャッシュされず、デバイス上の判断が実行されます。

### Artifact Cache TTL

[!DNL Target] は、メタデータ、ルールおよび条件で構成されるアーティファクトとしてon-device decisioningに該当するアクティビティを表します。このアーティファクトはAkamai CDN上にキャッシュされます。 ユーザーの初回訪問時に、ユーザーのブラウザーがオンデバイス判定アクティビティを表すアーティファクトをダウンロードしてキャッシュします。

サイトへの以降の訪問では、ブラウザーは、新しいバージョンのアーティファクトをダウンロードする必要があるかどうかを自動的に確認します。 このチェックは遅延を追加します。 アーティファクトキャッシュTTLは、前回正常にダウンロードされた後に、ブラウザーが更新されたアーティファクトをチェックしない時間（分）を定義します。 時間枠が長いほど、パフォーマンスが向上します。 時間枠が短いほどデータの鮮度は向上しますが、待ち時間が長くなるコストは高くなります。

## アクティビティがオンデバイス判定の資格を持っていることを知る方法を教えてください。

オンデバイス判定の資格を持つアクティビティを作成すると、[!UICONTROL On-Device Decisioning Eligible]というラベルがアクティビティの[!UICONTROL 概要]ページに表示されます。

![アクティビティの概要ページの「On-Device Decisioningの有効なラベル」。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

このラベルが、アクティビティが常にオンデバイスの判定を介して配信されることを意味するわけではありません。 at.js 2.5.0以降がオンデバイス判定を使用するように設定されている場合にのみ、このアクティビティはデバイス上で実行されます。 at.js 2.5.0以降がオンデバイスを使用するように設定されていない場合、このアクティビティは、at.jsから行われるサーバー呼び出しを介して配信されます。

[!UICONTROL On-Device Decisioning Eligibled]フィルターを使用して、[!UICONTROL アクティビティ]ページで有効なオンデバイス判定のすべてのアクティビティをフィルターできます。

![アクティビティページのOn-Device Decisioningの有効なフィルター。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>有効なオンデバイス判定の対象となるアクティビティを作成してアクティブ化した後、Akamai CDNのプレゼンスポイントに生成および反映されるルールアーティファクトに含まれるまで、5 ～ 10分かかる場合があります。

## オンデバイス判定のアクティビティがAt.js 2.5.0以降を介して提供されるようにする手順の概要を教えてください。

1. Adobe TargetUIにアクセスし、**[!UICONTROL 管理]**/**[!UICONTROL 実装]**/**[!DNL Account Details]**&#x200B;に移動して、**[!UICONTROL オンデバイス判定]**&#x200B;の切り替えを有効にします。
1. 「**」[!UICONTROL 既存のすべてのオンデバイス判定修飾アクティビティをアーティファクト]&quot;**&#x200B;に含める」トグルを有効にします。

   最初のJSONルールのアーティファクト生成には、最大10分かかります。

1. オンデバイス判定](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)でサポートされている[アクティビティタイプを作成してアクティブ化し、そのタイプがオンデバイス判定の適格であることを確認します。
1. at.js設定UIを使用して、**[!UICONTROL Decisioningメソッド]**&#x200B;を&#x200B;**[!UICONTROL &quot;ハイブリッド&quot;]**&#x200B;または&#x200B;**[!UICONTROL &quot;オンデバイスのみ&quot;]**&#x200B;に設定します。
1. At.js 2.5.0以降をページにダウンロードしてデプロイします。
