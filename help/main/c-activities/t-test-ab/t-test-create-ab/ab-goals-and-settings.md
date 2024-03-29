---
keywords: アクティビティ設定;A/B 目標と設定;レポート設定;目標指標;成功指標;従属成功指標;詳細設定;主な目標;追加の指標;目的;優先度;期間;レポートソリューション;目標;レポートのためのオーディエンス;指標を増分する前にどの成功指標に達するべきか;この目的指標にユーザーが達した後はどうなるか;メモ
description: の使用方法を学ぶ [!UICONTROL 目標と設定] ページ内 [!DNL Adobe Target] :A/B アクティビティの目標に関する情報を指定します。
title: で目標と設定を指定する方法 [!DNL Target] A/B アクティビティ？
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 53%

---

# 目標と設定

The [!UICONTROL 目標と設定] ページ内 [!DNL Adobe Target] は、アクティビティの目標に関する情報を指定する場所です。

利用できる設定は、Target を使用しているか、使用しているかによって異なります [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) を使用します。

## [!UICONTROL アクティビティの設定] {#section_DCBDC354261F420EBD4B43EA34947BAC}

The [!UICONTROL アクティビティの設定] のセクション [!UICONTROL 目標と設定] ページでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL 目的] | 目的を入力します（オプション）。目標には、ユーザーやチームメンバーがアクティビティを識別するのに役立つ任意の情報を指定できます。 |
| [!UICONTROL 優先度] | 設定に応じて、 [!DNL Target] の UI とオプション [!UICONTROL 優先度] 変化する。 従来の設定の [!UICONTROL 低], [!UICONTROL 中]または [!UICONTROL 高]または、0 ～ 999 の詳細な優先度を有効にすることもできます。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>このオプションが [!UICONTROL 管理] （デフォルト）次の優先度を指定します。 [!UICONTROL 低], [!UICONTROL 中]または [!UICONTROL 高].<P>有効にするには [きめ細かい優先度](/help/main/administrating-target/reporting.md)をクリックし、 [!UICONTROL 管理] > [!UICONTROL レポート]、次に [!UICONTROL 詳細な優先度の有効化] オプションを「オン」位置に設定します。 <P>このオプションを有効にした場合は、0 ～ 999 の値を指定します。 0 = [!UICONTROL 低] および 999 = [!UICONTROL 高]. <P>以前のバージョンので作成されたアクティビティの場合 [!DNL Target], [!UICONTROL 低] 優先度は 0 に変換され、 [!UICONTROL 中] は 5 に変換され、 [!UICONTROL 高] は 10 に変換されます。 これらの値は必要に応じて調整できます。<P>注意： 優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。 |
| 期間 | アクティビティは、承認されたときに開始させたり、特定の日時を設定したりできます。同様に、非アクティブ化されたときに終了させたり、日時を設定したりできます。タイムピッカーは 24 時間の時計を使用します。00:00 は真夜中です。タイムゾーンはブラウザーで設定されたタイムゾーンに設定されます。別のタイムゾーンを使用するには、ブラウザーのタイムゾーンを変更してからブラウザーを再起動します。 |

## [!UICONTROL レポート設定] {#section_13119392051044FBA6387D9B3B1C43CF}

The [!UICONTROL レポート設定] のセクション [!UICONTROL 目標と設定] ページでは、次のオプションを設定できます。

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL レポートソース] | データを収集する元にするかどうかを指定 [!DNL Adobe Target] またはから [!DNL Adobe Analytics]. 各レポートソリューションの差異およびそれぞれのメリットについて詳しくは、[Adobe Target のレポートソースとしての Adobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md)を参照してください。選択時 [!DNL Analytics] レポートソースとして [!DNL Target]を選択した場合、 [!DNL Analytics] 受信するレポートスイート [!DNL Target] アクティビティデータ。<P>レポートソースを指定するには、まず、次のいずれかを選択します。 [!DNL Analytics] アカウントに結び付けられた会社を選択し、アクティビティに適したレポートスイートを選択します。 接続するようにプロビジョニングされたレポートスイートのみ [!DNL Adobe Target] は選択可能です。 対象のレポートスイートが表示されない場合は、まず、ログアウトしてから、 [!DNL Adobe Experience Cloud] 再度お試しください。 それでもレポートスイートがリストに表示されない場合は、カスタマーケアにお問い合わせください。<P>アカウント設定でレポートソースが指定されている場合は、指定されたソースが使用され、この設定は表示されません。<P>注意：レポートの一貫性を確保するため、アクティビティが実行されるとレポートソースは変更できなくなります。 |
| [!UICONTROL 目標指標] | 目標達成の基準となる、訪問者の行動を選択します。例えば、 [!UICONTROL コンバージョン] 指標を設定し、成功の基準となるパラメーターを設定します。 指標の設定について詳しくは、[指標の設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)を参照してください。<P>注意：レポートソリューションが [!DNL Analytics]に設定されている場合、利用できる目標指標は [!UICONTROL コンバージョン]. [!DNL Analytics] 指標は目標として選択できません。成功指標を選択したら、セレクターが表示されます。このセレクターを使用して、成功指標の具体的な内容を選択します。<P>有効にした場合、 [!UICONTROL コンバージョンの推定値] フィールド ( [!UICONTROL ページスコア] 指標 ) は、他の指標ではなく、目標に関する値を提供します。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。すべての売上高指標（[!UICONTROL 訪問者あたり売上高]、[!UICONTROL 平均注文額]、[!UICONTROL 合計販売額]および[!UICONTROL 注文]）について、予測には[!UICONTROL 訪問者あたり売上高]が使用されます。データタイプは通貨です。<P>アクティビティの目標を達成した後も、訪問者がより優先度の高いアクティビティに該当しない限り、その訪問者には引き続きそのアクティビティのコンテンツが表示されます。 訪問者が再度目標を達成した場合は、追加のコンバージョンとしてカウントされます。これは、 [!DNL Target Classic]：訪問者がアクティビティを再度表示した場合、新規としてカウントされます。 |
| [!UICONTROL 追加の指標] | 追加の成功指標を作成します。この設定は、レポートソリューションが [!DNL Analytics]. この場合、 [!DNL Analytics] レポートスイートが適用されます。 |
| [!UICONTROL レポート対象のオーディエンス] | デフォルトでは、資格を満たすすべての訪問者の結果がレポートに表示されます。レポートのオーディエンスを追加して、特定のオーディエンスに関する情報のみを表示できます。 この設定は、 [!DNL Analytics] をレポートソリューションとして使用する。 に対して定義されたオーディエンス [!DNL Analytics] レポートスイートが適用されている状態。 |

## 詳細設定 {#section_E2FE441AFB324E498793ABB025ED9974}

The [!UICONTROL 詳細設定] のセクション [!UICONTROL 目標と設定] ページでは、次のオプションを設定できます。

詳細設定を指定するには、 **[!UICONTROL その他]** アイコン（縦の省略記号）をクリックし、 **[!UICONTROL 詳細設定]**（次の図に示すように）

![詳細設定メニュー](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。「詳細設定」オプションは使用できません。

![詳細設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| 設定 | 説明 |
|--- |--- |
| [!UICONTROL この指標を増分する前に達成する必要がある成功指標はどれですか？] | このオプションを使用すると、以前に別の成功指標に到達したことがあるユーザーのみが成功指標に到達したとしてカウントされます。 例えば、訪問者がオファーをクリックした場合、または、コンバートする前に特定のページに到達した場合にのみ、アクティビティのコンバージョンが有効になる場合があります。 複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。成功指標の依存関係を設定する前に、両方（または複数）の成功指標を定義します。 「[!UICONTROL 依存関係を追加]」オプションを利用すると、ある成功指標に到達した場合、または到達しなかった場合に別の成功指標を増分するよう設定できます。依存関係を追加する手順は次のとおりです。<ul><li>指標を追加したら、「[!UICONTROL 詳細設定]」をクリックします。</li><li>「[!UICONTROL 依存関係を追加]」オプションをクリックします。</li><li>目的の指標を左側のパネルから右側のパネルにドラッグ＆ドロップしてから、「[!UICONTROL 到達]」をクリックし、「[!UICONTROL 到達]」と「[!UICONTROL 未到達]」を切り替えて設定します。</li><li>追加した依存関係は後で編集または削除できます。</li></ul> |
| [!UICONTROL ユーザーがこの目標指標に達した後、どうなりますか？] | ユーザーが目標指標に到達した後の動作には、3 つのオプションがあります。<ul><li>「[!UICONTROL カウントを増分、アクティビティでユーザーを保持]」を選択して、カウントの増分方法を指定します。</li><li>「[!UICONTROL カウントを増分、ユーザーをリリース、再入場を許可]」を選択して、ユーザーがアクティビティに再度入ったときに表示されるエクスペリエンスを指定します。</li><li>「[!UICONTROL カウントを増分、ユーザーをリリース、再入場を許可しない]」を選択して、アクティビティのコンテンツの代わりにユーザーに表示する内容を指定します。</li></ul> |
| [!UICONTROL カウントをどのように増分しますか？] | カウントの増加方法について、以下の 3 つのオプションがあります。<ul><li>[!UICONTROL 参加者ごとに 1 回]</li><li>[!UICONTROL すべてのインプレッション（ページの更新を除く）]</li><li>[!UICONTROL すべてのインプレッション]</li></ul> |

詳細設定について詳しくは、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」を参照してください。

## その他のメタデータ {#section_2E8917BEFB954480A4206B9E9E917F80}

The [!UICONTROL その他のメタデータ] のセクション [!UICONTROL 目標と設定] ページでは、自分や他のチームメンバーが手元に置くのに役立つ、アクティビティに関する情報を指定できます。 メモウィンドウはサイズ変更可能です。|

## トレーニングビデオ

以下のビデオは、この記事で説明した概念についてさらに詳しく説明しています。

### アクティビティの設定(3:02) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

(https://video.tv.adobe.com/v/17381?captions=jpn

### A/B テストの作成(8:36) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、アクティビティを作成する際に 3 ステップのガイドによるワークフロー内でどのようにアクティビティ設定がなされるのか示します。目標と設定の説明は、5:30 から始まります。

* Adobe Target での A/B アクティビティの作成
* 手動分割または自動トラフィック配分によるトラフィックの配分

>[!VIDEO](https://video.tv.adobe.com/v/17391)
