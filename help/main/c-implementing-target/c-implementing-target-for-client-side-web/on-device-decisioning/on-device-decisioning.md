---
keywords: 実装；javascript ライブラリ；js;atjs；オンデバイス判定；on device decisioning;at.js；オンデバイス；on-device
description: at.js ライブラリを使用してオンデバイス判定を実行する方法を説明します。
title: オンデバイス判定は at.js JavaScript ライブラリとどのように連携しますか。
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '3552'
ht-degree: 18%

---

# at.js のオンデバイス判定

バージョン 2.5.0 以降、at.js は On-Device Decisioning を提供します。 オンデバイス判定を使用して、 [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) および [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) (XT) ブラウザー上でのアクティビティ。 [!DNL Adobe Target] Edge ネットワーク。

[!DNL Target] また、は、実験や機械学習に基づく（ML 駆動の）パーソナライゼーションアクティビティから、ライブサーバー呼び出しを介して、最も関連性の高い最新のエクスペリエンスを提供する柔軟性も提供します。 つまり、パフォーマンスが最も重要な場合は、オンデバイス判定を使用するように選択できます。 ただし、最も関連性の高い最新の ML 駆動型エクスペリエンスが必要な場合は、代わりにサーバー呼び出しをおこなうことができます。

## オンデバイス判定のメリットは何ですか？

オンデバイス判定のメリットには、次のようなものがあります。

* **超高速な意思決定とエクスペリエンスを提供します。** グループ化と判定は、ネットワークリクエストのブロックを防ぐために、メモリ内およびブラウザーで実行されます。
* **アプリケーションのパフォーマンスを向上** エンドユーザーエクスペリエンスを損なうことなく、実験を実行し、パーソナライゼーションを顧客およびユーザーに提供します。
* **Googleサイトの品質スコアを改善します。** メモリ内で判定がおこなわれるので、オンラインビジネスのGoogleサイトの品質スコアを向上させ、消費者が見つけやすくします。
* **リアルタイム分析から学ぶ。** を通じて、アクティビティのパフォーマンスからリアルタイムでインサイトを得る [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) レポート。 A4T を使用すると、重要な時点で戦略をピボットできます。

## サポートされる機能

Adobe Target JS SDK を使用すると、お客様は、パフォーマンスと決定のためのデータの鮮度を柔軟に選択できます。 つまり、機械学習を通じて最も関連性が高く、パーソナライズされたコンテンツを配信することが最も重要な場合は、ライブサーバー呼び出しをおこなう必要があります。 しかし、パフォーマンスがより重要な場合は、デバイス上およびメモリ内での判断が必要です。 オンデバイス判定が機能するには、サポートされる機能のリストを参照してください。

* アクティビティのタイプ
* オーディエンスのターゲティング
* 配分方法

詳しくは、 [オンデバイス判定でサポートされる機能](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

## オンデバイス判定の仕組み

オンデバイス判定を有効にして at.js をデプロイおよび初期化する場合、 [ルールアーティファクト](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/)A/B および XT のアクティビティ、オーディエンスおよびアセットに対するオンデバイス判定を含む {target=_blank} は、訪問者に最も近い Akamai CDN からダウンロードされ、訪問者のブラウザーにローカルにキャッシュされます。 エクスペリエンスを取得するリクエストが at.js からおこなわれると、キャッシュされたルールアーティファクトでエンコードされたメタデータに基づいて、返されるエクスペリエンスに関する決定がメモリ内でおこなわれます。

## 判定方法

オンデバイス判定を使用する場合、 [!DNL Target] という新しい設定を導入する [!UICONTROL 判定方法]. この [!UICONTROL 判定方法] の設定は、at.js がエクスペリエンスを提供する方法を示します。 [!UICONTROL 判定方法] には 3 つの値があります。

* [!UICONTROL サーバー側のみ]
* [!UICONTROL オンデバイスのみ]
* [!UICONTROL ハイブリッド]

### サーバー側のみ

at.js 2.5.0 以降が実装され web プロパティにデプロイされる場合に標準で設定されているデフォルトの判定方法は[!UICONTROL サーバー側のみ]です。

[!UICONTROL サーバー側のみ ]をデフォルト設定として使用すると、すべての決定は [!DNL Target] エッジネットワーク上で行われます。これにはブロッキングサーバーコールが必要になります。このアプローチでは、待ち時間が徐々に増えるおそれがありますが、[Recommendations](/help/main/c-recommendations/recommendations.md)、[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)（AP）および[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)の各アクティビティなど、Target の機械学習機能を適用する機能を提供するなど、大きなメリットもあります。

さらに、すべてのセッションやチャネルにわたって永続化された Target のユーザープロファイルを使用して、パーソナライズされたエクスペリエンスを強化することで、ビジネスに大きな成果をもたらすことができます。

最後に、[!UICONTROL サーバー側のみ ]では、Adobe Experience Cloud を使用して、Audience Manager セグメントや Adobe Analytics セグメントを介してターゲティングできるオーディエンスを微調整できます。

次の図は、訪問者、ブラウザー、at.js 2.5.0 以降およびAdobe Target Edge ネットワーク間のインタラクションを示しています。 このフロー図は、新規訪問者と再訪問者を取り込みます。

![サーバー側のみのフロー図](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

次のリストは、ダイアグラムの数値に対応しています。

| 手順 | 説明 |
| --- | --- |
| 1 | この [!DNL Experience Cloud Visitor ID] が [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>   at.js ライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して非同期で読み込むこともできます。 |
| 3 | at.js ライブラリでは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | ページ読み込みリクエストが実行され、（ECID、顧客 ID、カスタムパラメーター、ユーザープロファイルなど）設定済みのすべてのパラメーターが含まれます。 |
| 5 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。<br>プロファイルストアは、オーディエンスライブラリから正規のオーディエンスをリクエストします（例えば、から共有されたオーディエンス）。 [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]など )。<br>顧客属性がバッチ処理でプロファイルストアに送信されます。 |
| 6 | プロファイルストアは、アクティビティをフィルタリングするために、オーディエンスの選定とグループ化に使用されます。 |
| 7 | 結果のコンテンツは、エクスペリエンスがライブから判断された後に選択されます [!DNL Target] アクティビティ。 |
| 8 | at.js ライブラリでは、レンダリングが必要なエクスペリエンスに関連付けられている、ページ上の対応する要素を非表示にします。 |
| 9 | at.js ライブラリは、本文を表示し、訪問者が表示できるように、残りのページを読み込むことができます。 |
| 10 | at.js ライブラリは、DOM を操作して Target Edge ネットワークからエクスペリエンスをレンダリングします。 |
| 11 | エクスペリエンスが訪問者用にレンダリングされます。 |
| 12 | Web ページ全体が読み込まれます。 |
| 13 | [!DNL Analytics] データがデータ収集サーバーに送信されます。 |
| 14 | ターゲットデータは [!DNL Analytics] SDID を介してデータを処理し、 [!DNL Analytics] レポートストレージ。 [!DNL Analytics] for [!DNL Analytics]（A4T）レポートを使用して、[!DNL Target] データが [!UICONTROL Analytics および ]Target に表示できるようになります。 |

### オンデバイスのみ

[!UICONTROL オンデバイスのみ]は、オンデバイス判定を web ページ全体でのみ使用する場合に at.js 2.5.0 以降で設定する必要がある判定方法です。

オンデバイス判定では、オンデバイス判定の対象となるすべてのアクティビティを含んだ、キャッシュされたルールアーティファクトから決定が行われるので、エクスペリエンスとパーソナライゼーションアクティビティを超高速で配信できます。

どのアクティビティがオンデバイス判定の対象となるかについて詳しくは、 [オンデバイス判定でサポートされる機能](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

この判定方法は、[!DNL Target] からの決定を必要とするすべてのページでパフォーマンスが非常に重要な場合にのみ使用してください。さらに、この判定方法を選択した場合、オンデバイス判定の対象とならない [!DNL Target] アクティビティは配信も実行もされないことに注意してください。at.js ライブラリ 2.5.0 以降は、キャッシュされたルールアーティファクトのみを探して決定を下すように設定されています。

次の図は、訪問者、ブラウザー、at.js 2.5.0 以降および Akamai CDN 間のインタラクションを示しています。 Akamai CDN は、訪問者の最初の訪問に関するルールアーティファクトをキャッシュします。 新しい訪問者が最初にページを訪問する際には、JSON ルールアーティファクトを Akamai CDN からダウンロードして、訪問者のブラウザーにローカルにキャッシュする必要があります。 JSON ルールアーティファクトがダウンロードされた後、ネットワーク呼び出しをブロックせずに、即座に判定がおこなわれます。 次のフロー図は、新規訪問者を示しています。

![オンデバイスのみのフロー図](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

次のリストは、ダイアグラムの数値に対応しています。

>[!NOTE]
>
>[!DNL Adobe Target] 管理サーバーは、オンデバイス判定の対象となるすべてのアクティビティを検証し、JSON ルールアーティファクトを生成して、Akamai CDN に反映します。 アクティビティで、Akamai CDN に反映される新しい JSON ルールアーティファクトを出力するための更新が継続的に監視されます。

| 手順 | 説明 |
| --- | --- |
| 1 | この [!DNL Experience Cloud Visitor ID] が [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js ライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して非同期で読み込むこともできます。 |
| 3 | at.js ライブラリでは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | at.js ライブラリは、訪問者に最も近い Akamai CDN から JSON ルールアーティファクトを取得するリクエストを作成します。 |
| 5 | Akamai CDN が JSON ルールアーティファクトで応答します。 |
| 6 | JSON ルールアーティファクトは、訪問者のブラウザー上でローカルにキャッシュされます。 |
| 7 | at.js ライブラリは、JSON ルールアーティファクトを解釈し、エクスペリエンスを取得する決定を実行し、テストされた要素を非表示にします。 |
| 8 | at.js ライブラリは、本文を表示し、訪問者が表示できるように、残りのページを読み込むことができます。 |
| 9 | at.js ライブラリは DOM を操作して、キャッシュされた JSON ルールアーティファクトからエクスペリエンスをレンダリングします。 |
| 10 | エクスペリエンスが訪問者用にレンダリングされます。 |
| 11 | Web ページ全体が読み込まれます。 |
| 12 | [!DNL Analytics] データがデータ収集サーバーに送信されます。ターゲットデータは [!DNL Analytics] SDID を介してデータを処理し、 [!DNL Analytics] レポートストレージ。 [!DNL Analytics][!DNL Analytics]A4T レポートを使用して、 データが for の両方に表示できるようになります。[!DNL Target] |

次の図は、訪問者の後続のページヒットまたは再訪問に対する、訪問者、ブラウザー、at.js 2.5.0 以降、キャッシュされた JSON ルールアーティファクト間のインタラクションを示しています。 JSON ルールアーティファクトは既にキャッシュされ、ブラウザーで使用できるので、ネットワーク呼び出しをブロックすることなく、即座に決定がおこなわれます。 このフロー図は、後続のページナビゲーションまたは再訪問者をキャプチャします。

![後続のページナビゲーションと再訪問に関するオンデバイスのみのフロー図](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

次のリストは、ダイアグラムの数値に対応しています。

>[!NOTE]
>
>[!DNL Adobe Target] 管理サーバーは、オンデバイス判定の対象となるすべてのアクティビティを検証し、JSON ルールアーティファクトを生成して、Akamai CDN に反映します。 アクティビティで、Akamai CDN に反映される新しい JSON ルールアーティファクトを出力するための更新が継続的に監視されます。

| 手順 | 説明 |
| --- | --- |
| 1 | この [!DNL Experience Cloud Visitor ID] が [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js ライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して非同期で読み込むこともできます。 |
| 3 | at.js ライブラリでは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | at.js ライブラリは、JSON ルールアーティファクトを解釈し、メモリ内の決定を実行してエクスペリエンスを取得します。 |
| 5 | テストされた要素は非表示になります。 |
| 6 | at.js ライブラリは、本文を表示し、訪問者が表示できるように、残りのページを読み込むことができます。 |
| 7 | at.js ライブラリは DOM を操作して、キャッシュされた JSON ルールアーティファクトからエクスペリエンスをレンダリングします。 |
| 8 | エクスペリエンスが訪問者用にレンダリングされます。 |
| 9 | Web ページ全体が読み込まれます。 |
| 10 | [!DNL Analytics] データがデータ収集サーバーに送信されます。ターゲットデータは [!DNL Analytics] SDID を介してデータを処理し、 [!DNL Analytics] レポートストレージ。 [!DNL Analytics] for [!DNL Analytics]（A4T）レポートを使用して、[!DNL Target] データが [!UICONTROL Analytics および ]Target に表示できるようになります。 |

### ハイブリッド

[!UICONTROL ハイブリッド]は、オンデバイス判定アクティビティと、Adobe Target Edge ネットワークへのネットワーク呼び出しを必要とするアクティビティの両方を実行する必要がある場合に、at.js 2.5.0 以降で設定する必要がある判定方法です。

オンデバイス判定アクティビティとサーバー側アクティビティの両方を管理している場合は、ページに [!DNL Target] をデプロイしてプロビジョニングする方法を考える際に、少し複雑で面倒な場合があります。ハイブリッド判定方法では、サーバー側実行が必要なアクティビティについて Adobe Target Edge ネットワークに対してサーバーコールを行う必要がある場合と、オンデバイス判定のみを実行する必要がある場合を [!DNL Target] が把握しています。

JSON ルールアーティファクトには、mbox がサーバー側アクティビティを実行しているか、オンデバイス判定アクティビティを実行しているかを at.js に通知するメタデータが含まれています。この判定方法では、迅速に配信すべきアクティビティをオンデバイス判定を通じて行い、機械学習によるより強力なパーソナライゼーションを必要とするアクティビティについては、Adobe Target Edge ネットワークを介して行います。

次の図は、初めてページを訪問する新しい訪問者に対する、訪問者、ブラウザー、at.js 2.5.0 以降、Akamai CDN、Adobe Target Edge Network 間のインタラクションを示しています。 この図からわかるのは、JSON ルールアーティファクトが非同期でダウンロードされ、一方で、決定はAdobe Target Edge ネットワークを通じておこなわれるということです。

この方法では、多数のアクティビティを含む可能性があるアーティファクトのサイズが、判定の待ち時間に悪影響を与えないようにします。 JSON ルールアーティファクトを同期的にダウンロードし、その後に決定をおこなう場合も、遅延に悪影響を与え、一貫性が失われる可能性があります。 したがって、ハイブリッド判定方法は、新しい訪問者に対して常にサーバー側で判定を呼び出し、JSON ルールアーティファクトが並行してキャッシュされるので、お勧めのベストプラクティスです。 以降のページ訪問と再訪問では、JSON ルールアーティファクトを通じて、キャッシュとメモリ内から決定がおこなわれます。

![初回訪問者のハイブリッドフロー図](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

次のリストは、ダイアグラムの数値に対応しています。

>[!NOTE]
>
>[!DNL Adobe Target] 管理サーバーは、オンデバイス判定の対象となるすべてのアクティビティを検証し、JSON ルールアーティファクトを生成して、Akamai CDN に反映します。 アクティビティで、Akamai CDN に反映される新しい JSON ルールアーティファクトを出力するための更新が継続的に監視されます。

| 手順 | 説明 |
| --- | --- |
| 1 | この [!DNL Experience Cloud Visitor ID] が [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js ライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して非同期で読み込むこともできます。 |
| 3 | at.js ライブラリでは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | ページ読み込みリクエストは、Adobe Target Edge Network に対しておこなわれます。これには、（ECID、顧客 ID、カスタムパラメーター、ユーザープロファイルなど）設定済みのすべてのパラメーターが含まれます。 |
| 5 | 同時に、at.js は、訪問者に最も近い Akamai CDN から JSON ルールアーティファクトを取得するリクエストをおこないます。 |
| 6 | (Adobe Target Edge Network) プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。 プロファイルストアは、オーディエンスライブラリから正規のオーディエンスをリクエストします（例えば、から共有されたオーディエンス）。 [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]など )。 |
| 7 | Akamai CDN が JSON ルールアーティファクトで応答します。 |
| 8 | プロファイルストアは、アクティビティをフィルタリングするために、オーディエンスの選定とグループ化に使用されます。 |
| 9 | 結果のコンテンツは、エクスペリエンスがライブから判断された後に選択されます [!DNL Target] アクティビティ。 |
| 10 | at.js ライブラリでは、レンダリングが必要なエクスペリエンスに関連付けられている、ページ上の対応する要素を非表示にします。 |
| 11 | at.js ライブラリは、本文を表示し、訪問者が表示できるように、残りのページを読み込むことができます。 |
| 12 | at.js ライブラリは、DOM を操作して Target Edge ネットワークからエクスペリエンスをレンダリングします。 |
| 13 | エクスペリエンスが訪問者用にレンダリングされます。 |
| 14 | Web ページ全体が読み込まれます。 |
| 15 | [!DNL Analytics] データがデータ収集サーバーに送信されます。ターゲットデータは [!DNL Analytics] SDID を介してデータを処理し、 [!DNL Analytics] レポートストレージ。 [!DNL Analytics] for [!DNL Analytics]（A4T）レポートを使用して、[!DNL Target] データが [!UICONTROL Analytics および ]Target に表示できるようになります。 |

次の図は、後続のページナビゲーションまたは再訪問での、訪問者、ブラウザー、at.js 2.5.0 以降、キャッシュされた JSON ルールアーティファクト間のインタラクションを示しています。 この図では、後続のページナビゲーションまたは再訪問でデバイス上の決定がおこなわれる使用例にのみ焦点を当てます。 特定のページに対してどのアクティビティがライブになっているかに応じて、サーバー側の決定を実行するためにサーバー側の呼び出しがおこなわれる場合があることに注意してください。

![後続のページナビゲーションおよび繰り返し訪問に関するハイブリッドフロー図](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

次のリストは、ダイアグラムの数値に対応しています。

>[!NOTE]
>
>[!DNL Adobe Target] 管理サーバーは、オンデバイス判定の対象となるすべてのアクティビティを検証し、JSON ルールアーティファクトを生成して、Akamai CDN に反映します。 アクティビティで、Akamai CDN に反映される新しい JSON ルールアーティファクトを出力するための更新が継続的に監視されます。

| 手順 | 説明 |
| --- | --- |
| 1 | この [!DNL Experience Cloud Visitor ID] が [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js ライブラリは、ページに実装されているオプションの事前非表示スニペットを使用して非同期で読み込むこともできます。 |
| 3 | at.js ライブラリでは、ちらつきを防ぐために本文を非表示にします。 |
| 4 | エクスペリエンスを取得するリクエストが作成されます。 |
| 5 | at.js ライブラリによって、JSON ルールアーティファクトが既にキャッシュされていることが確認され、メモリ内で決定を実行してエクスペリエンスを取得します。 |
| 6 | テストされた要素は非表示になります。 |
| 7 | at.js ライブラリは、本文を表示し、訪問者が表示できるように、残りのページを読み込むことができます。 |
| 8 | at.js ライブラリは DOM を操作して、キャッシュされた JSON ルールアーティファクトからエクスペリエンスをレンダリングします。 |
| 9 | エクスペリエンスが訪問者用にレンダリングされます。 |
| 10 | Web ページ全体が読み込まれます。 |
| 11 | [!DNL Analytics] データがデータ収集サーバーに送信されます。ターゲットデータは [!DNL Analytics] SDID を介してデータを処理し、 [!DNL Analytics] レポートストレージ。 [!DNL Analytics] for [!DNL Analytics]（A4T）レポートを使用して、[!DNL Target] データが [!UICONTROL Analytics および ]Target に表示できるようになります。 |

## オンデバイス判定を有効にする方法を教えてください。

オンデバイス判定は、すべての [!DNL Target] at.js 2.5.0 以降を使用するお客様

オンデバイス判定を有効にするには：

>[!NOTE]
>
>次を持っている必要があります： [!UICONTROL 管理者] または [!UICONTROL 承認者] [ユーザーロール](/help/main/administrating-target/c-user-management/user-management.md) :「オンデバイス判定」切り替えを有効または無効にします。

1. クリック **[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!UICONTROL アカウントの詳細]**.
1. の下 **[!UICONTROL アカウントの詳細]**、 **[!UICONTROL オンデバイス判定]** 「オン」の位置に切り替えます。

   ![オンデバイス判定の切り替え](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   「[!UICONTROL 既存のすべてのオンデバイス判定対象アクティビティをアーティファクトに含めます]「 」オプションは、on-device decisioning を有効にすると表示されます。
1. （条件付き）オンデバイス判定の対象となるすべてのライブ Target アクティビティをアーティファクトに自動的に含める場合は、切り替えを「オン」の位置にスライドします。

   この切り替えをオフにした場合、オンデバイス判定アクティビティを生成されたルールアーティファクトに含めるには、そのアクティビティを再作成し、アクティブ化する必要があります。 つまり、 [!UICONTROL オンデバイス判定] 切り替えはルールアーティファクトに含まれません。

を有効にした後 [!UICONTROL オンデバイス判定] 切り替え [!DNL Target] 生成と伝播を開始 [ルールアーティファクト](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/){target=_blank} を設定します。

>[!IMPORTANT]
>
>オンデバイス判定を使用するようにAdobe Target SDK を初期化する前に、必ず切り替えを有効にしてください。 ルールアーティファクトは、まず、オンデバイス判定を機能させるために、生成し、Akamai CDN に反映する必要があります。 最初のルールアーティファクトが生成されて Akamai CDN に反映されるまで、伝播には 5～10 分かかる場合があります。

## オンデバイス判定を使用するように at.js 2.5.0 以降を設定する方法を教えてください。

1. クリック **[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!UICONTROL アカウントの詳細]**.
1. の下 **[!UICONTROL 実装方法]** > **[!UICONTROL 主な実装方法]**&#x200B;をクリックし、 **[!UICONTROL 編集]** を at.js バージョンの横に置きます（at.js 2.5.0 以降にする必要があります）。

   ![主な実装方法設定の編集](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >これらのデフォルト設定を変更する前に、現在の実装に影響を与えないよう、ClientCare にお問い合わせください。

1. 目的の判定方法を選択します。

   * [!UICONTROL サーバー側のみ]
   * [!UICONTROL オンデバイスのみ]
   * [!UICONTROL ハイブリッド]

   ![at.js 設定パネルを編集](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### グローバル設定

デフォルトの [!UICONTROL 判定方法] すべて [!DNL Target] 決定。 様々な判定方法は次のとおりです。 [!UICONTROL サーバー側のみ], [!UICONTROL オンデバイスのみ]、および [!UICONTROL ハイブリッド]. Target UI で選択された判定方法は、 `window.targetGlobalSettings` の下に `decisioningMethod` フィールドに入力します。 詳しくは、 `decisioningMethod` in [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

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

### カスタマイズ設定

次に `decisioningMethod` in `window.targetGlobalSettings`を返しますが、 `decisioningMethod` ユースケースに従ったAdobe Targetの各決定に対して、次の手順を実行できます： `decisioningMethod` at.js2.5.0 以降の [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/){target=_blank} 呼び出し。

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
>getOffers() 呼び出しで「オンデバイス」または「ハイブリッド」を判定メソッドとして使用するには、グローバル設定に `decisioningMethod` を「on-device」または「hybrid」として設定できます。 at.js ライブラリ 2.5.0 以降は、ページに読み込んだ直後に、JSON ルールアーティファクトをダウンロードしてキャッシュするかどうかを把握している必要があります。 グローバル設定の判定メソッドが「サーバー側」に設定され、「オンデバイス」または「ハイブリッド」の判定メソッドが getOffers() 呼び出しに渡された場合、at.js 2.5.0 以降では、JSON ルールアーティファクトがキャッシュされず、オンデバイスの判定が実行されます。

### アーティファクトキャッシュ TTL

[!DNL Target] は、オンデバイス判定の対象となるアクティビティを、メタデータ、ルール、条件で構成されるアーティファクトとして表します。 このアーティファクトは Akamai CDN 上にキャッシュされます。 ユーザーの初回訪問中に、ユーザーのブラウザーは、オンデバイス判定アクティビティを表すアーティファクトをダウンロードしてキャッシュします。

その後のサイト訪問時に、ブラウザーは、新しいバージョンのアーティファクトをダウンロードする必要があるかどうかを自動的に確認します。 このチェックは待ち時間を追加します。 アーティファクトキャッシュの TTL は、最後に正常にダウンロードされてからの更新済みアーティファクトをブラウザーで確認しない分数を定義します。 期間が長いほど、パフォーマンスが向上します。 時間枠が短いほど、データの鮮度が向上しますが、待ち時間が長くなります。

## アクティビティの実施要件がデバイス上での判定であることを確認するには、どうすればよいですか？

オンデバイス判定の対象となるアクティビティを作成すると、次のようなラベルが付きます。 [!UICONTROL オンデバイス判定の対象]( アクティビティの [!UICONTROL 概要] ページ。

![アクティビティの概要ページのオンデバイス判定対象ラベル。](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

このラベルは、アクティビティが常にオンデバイス判定経由で配信されるとは限りません。 at.js 2.5.0 以降がオンデバイス判定を使用するように設定されている場合にのみ、このアクティビティはデバイス上で実行されます。 at.js 2.5.0 以降がオンデバイスを使用するように設定されていない場合、このアクティビティは、at.js からおこなわれるサーバー呼び出しを介して引き続き配信されます。

で実施要件を満たすオンデバイス判定の対象となるすべてのアクティビティをフィルタリングできます [!UICONTROL アクティビティ] ページを [!UICONTROL オンデバイス判定の対象] フィルター。

![アクティビティページのオンデバイス判定対象フィルター。](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>オンデバイス判定の対象となるアクティビティを作成してアクティブ化すると、生成され Akamai CDN のプレゼンスポイントに反映されるルールアーティファクトに含められるまでに、5～10 分かかる場合があります。

## オンデバイス判定アクティビティが At.js 2.5.0 を介して確実に配信されるようにする手順の概要+?

1. Adobe Target UI にアクセスし、に移動します。 **[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!DNL Account Details]** 有効にする **[!UICONTROL オンデバイス判定]** 切り替え
1. を有効にします。 **&quot;[!UICONTROL 既存のすべてのオンデバイス判定対象アクティビティをアーティファクトに含めます]&quot;** 切り替え

   最初の JSON ルールアーティファクトの生成には、最大 10 分かかる場合があります。

1. の作成とアクティブ化 [オンデバイス判定でサポートされるアクティビティタイプ](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/)をクリックし、オンデバイス判定の対象であることを確認します。
1. を **[!UICONTROL 判定方法]** どちらか **[!UICONTROL &quot;ハイブリッド&quot;]** または **[!UICONTROL &quot;On-device only&quot;]** at.js 設定 UI を使用します。
1. ページに at.js 2.5.0 以降をダウンロードしてデプロイします。
