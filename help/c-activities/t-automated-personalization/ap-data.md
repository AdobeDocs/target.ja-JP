---
description: Target では、様々なデータを自動的に収集し、それを基に Automated Personalization（AP）と自動ターゲット（AT）アクティビティのパーソナライゼーションアルゴリズムを構築します。訪問者に AP または AT アクティビティが提供されると、情報のスナップショットが「トレーニングレコード」（パーソナライゼーションアルゴリズムによる学習の基になる訪問者データ）のセットに渡されます。
seo-description: Target では、様々なデータを自動的に収集し、それを基に Automated Personalization（AP）と自動ターゲット（AT）アクティビティのパーソナライゼーションアルゴリズムを構築します。訪問者に AP または AT アクティビティが提供されると、情報のスナップショットが「トレーニングレコード」（パーソナライゼーションアルゴリズムによる学習の基になる訪問者データ）のセットに渡されます。
seo-title: Target のパーソナライゼーションアルゴリズムのデータ収集
solution: 'Target '
title: Target のパーソナライゼーションアルゴリズムのデータ収集
title-outputclass: Premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: Premium
translation-type: tm+mt
source-git-commit: 2baa75b6020b2f9229db68667c2e19a698954231

---


# ![Premium](/help/assets/premium.png) Target パーソナライゼーションアルゴリズムのデータ収集{#data-collection-for-the-target-personalization-algorithms}

Target では、様々なデータを自動的に収集し、それを基に Automated Personalization（AP）と自動ターゲット（AT）アクティビティのパーソナライゼーションアルゴリズムを構築します。訪問者に AP または AT アクティビティが提供されると、情報のスナップショットが「トレーニングレコード」（パーソナライゼーションアルゴリズムによる学習の基になる訪問者データ）のセットに渡されます。

Target のパーソナライゼーションアルゴリズムについて詳しくは、[ランダムフォレストアルゴリズム](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA) を参照してください。

次の表に、マーケティング担当者が何もしなくてもデフォルトで Automated Personalization で収集されるデータと、これらの属性を [パーソナライゼーションインサイトレポート](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) で表示するときに使用する命名規則を示します。入力データセットはいつでも増やすことができます。追加データのアップロード方法について詳しくは、[Target のソナライゼーションアルゴリズムのデータのアップロード](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6) を参照してください。

| データタイプ | 説明 | データタイプの命名規則 | 属性の例 |
|--- |--- |--- |--- |
| URL パラメーター | Target では、URL を解析して URL パラメーターを抽出します。 | `Custom - URL Parameter - [URL Parameter]` | カスタムデータ |
| 参照 URL パラメーター | 一般に参照 URL とは、mbox 呼び出しが実行された特定のページを参照した URL のことを指します。<br>この変数は、サイトでのユーザーの行動と、サイトの技術的実装の影響を受ける場合があります。 | `Custom - [Referring URL Parameter] - [Parameter value]` | カスタムデータ |
| 環境とセッションのデータ | ユーザーがアクティビティにアクセスした方法と日時に関する情報。 | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | 訪問者プロファイル - 最新の訪問の開始 <br>訪問者プロファイル - 合計訪問回数<br>訪問者プロファイル - 訪問 1 回あたりの平均滞在時間 <br>ブラウザー - タイムゾーン<br>ブラウザー - 曜日<br>ブラウザー - 言語設定<br>ブラウザー - タイプ<br>オペレーティングシステム - バージョン |
| 地域 | 訪問者の所在地に関する情報。 | `Geo - [geo attribute]` | 市町村<br>国<br>地域／州<br>郵便番号<br>緯度<br>経度<br> ISP または携帯電話会社 |
| デバイスとモバイルデータ | デバイスとモバイル固有の情報。 | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | モバイルデバイスの OS<br>モバイルの画面のサイズ |

