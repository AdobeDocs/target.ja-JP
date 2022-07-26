---
keywords: ターゲット設定；成功；コンバージョン指標；ページスコア指標；ページビュー指標；売上高指標；サイト滞在時間指標；予測値；詳細設定；詳細設定；依存関係；アクティビティでカウントを増分；ユーザーを保持；再入場を許可；カウントを増分、ユーザーをリリース
description: 成功指標についてのAdobe [!DNL Target] これは、アクティビティの成功を判断するのに役立ちます。 成功指標には、コンバージョン、売上高、ページビュー数、カスタムスコア、サイト滞在時間が含まれます。
title: 成功指標とは
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: b0bf54d47ac44afc3597f308ea38fd479c54026d
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 41%

---

# 成功指標

In [!DNL Adobe Target] 成功指標は、アクティビティの成功の測定に使用されるパラメーターです。 成功指標には、 [!DNL Target] アクティビティ。

例えば、新しいオファーが訪問者あたりの売上高を増加させたり、買い物かごに品目を追加したりするかどうかを判断できます。成功指標は、登録、注文または購入ファネルの問題を見つけるのに役立ちますが、単に訪問者やお客様のエンゲージメントにも役立ちます。

## 概要

In [!DNL Target]の場合、成功指標は、レポートおよび追跡の両方に最適なオプションを用いて事前設定されます。

デフォルトでは、コンバージョンイベントは「[!UICONTROL カウントを増分、アクティビティでユーザーを保持].&quot; コンバージョンは 1 回のみカウントされ、繰り返しコンバージョンはカウントされず、訪問者には常にアクティビティのコンテンツが表示されます。

売上高指標が「[!UICONTROL カウントを増分、アクティビティでユーザーを保持]」同じ訪問者が最初に行った注文の詳細のみをログに記録します。 それ以降のすべての注文は、コンバージョン数を増やしますが、RPV/AOV/Sales に売上高を追加することはなく、 [!UICONTROL 注文の詳細] レポート。

>[!NOTE]
>
>を使用するアクティビティの場合 [レポートソースとしての Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) の場合、目標指標は常に「[!UICONTROL カウントを増分、アクティビティでユーザーを保持]&quot;および&quot;[!UICONTROL すべてのインプレッション]」設定を使用します。 これは *not* 設定可能。

以下の成功指標を使用できます。

| 成功指標 | 測定アプローチ | 定義 |
|--- |--- |--- |
| コンバージョン | コンバージョンベース | コンバージョンとは、訪問者が、定義したサイトに対して、次のようなアクションを実行するときです。 <ul><li>ボタンをクリックしました</li><li>ページが表示された</li><li>調査を完了しました</li><li>購入済み</li></ul>コンバージョンは、訪問者ごとに 1 回、または訪問者がコンバージョンを完了するたびに 1 回とカウントできます。 |
| 売上高 | コンバージョンベース | 訪問者によって生成された売上高。次のいずれかの売上高指標から選択できます。<ul><li>訪問者あたりの売上高（RPV）</li><li>平均注文額（AOV）</li><li>合計販売額</li><li>注文</li></ul> |
| ページビュー | エンゲージメントベース | 一意の訪問ごとに 1 回のコンバージョンとしてカウントします。 |
| カスタムスコア | エンゲージメントベース | サイトで訪問したページに割り当てられた値に基づく、訪問者がアクティビティの最初の表示を最初に見た時点からの集計スコア。 [!DNL Target] リクエスト。 |
| サイト滞在時間 | エンゲージメントベース | 訪問者がアクティビティの最初の表示を見た時点からの訪問滞在時間（秒） [!DNL Target] リクエストを送信します。 |

エンゲージメントベースの指標の場合は（コンバージョンベースおよび売上高ベースの指標とは異なり）、訪問者はそのセッションのカウントをインクリメントするために、訪問ごとにアクティビティを再評価する必要があります。関連付けられた指標は、再評価の後にインクリメントが開始され、各訪問者のセッションの終わりでインクリメントが停止します。30 分間無操作状態が続くと、そのセッションは終了します。したがって、テスト中にすぐに結果が表示されることはありません。ただし、そのセッションからの結果は、セッションが終了してから数分以内にすべて利用できます。

## カスタム成功指標

カスタムの成功指標も作成できます。

成功指標を選択し、目的を達成するために訪問者がとるアクションを選択します。例えば、 [!UICONTROL コンバージョン] 指標を使用する場合は、訪問者ごとに 1 回カウントされるように設定してから、訪問者が特定のページ（または一連のページ）を表示したときに成功を収めるかどうかを設定し、特定のページを表示します [!DNL Target] 特定のリンクをクリックします。

有効にした場合、 [!UICONTROL 1 つのコンバージョンの推定値] フィールド ( [!UICONTROL ページスコア] 指標 ) は、他の指標ではなく、目標に関する値を提供します。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。すべての売上高指標 ([!UICONTROL 訪問者あたりの売上高], [!UICONTROL 平均注文額], [!UICONTROL 合計販売額]、および [!UICONTROL 注文]) の場合、推定は [!UICONTROL 訪問者あたりの売上高]. データタイプは通貨です。詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。

アクティビティに対して選択した成功指標は、そのアクティビティのレポートを表示するときに、レポート設定で利用できます。

一部の指標 ( 例： [!UICONTROL カスタムスコア] および [!UICONTROL 訪問者あたりの売上高]の場合は、注文の合計数や注文 ID などの情報を渡すカスタマイズされた実装が必要です。

## 詳細設定 {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

詳細設定を使用して、成功の測定方法を管理します。依存関係の追加、アクティビティでユーザーを保持するか削除するかの選択、参加者ごとに 1 回指標をカウントするか、すべてのインプレッションで指標をカウントするかの選択などのオプションがあります。

次の手順で [!UICONTROL 詳細設定] オプションを選択し、 **[!UICONTROL 縦楕円]** > **[!UICONTROL 詳細設定]**.

![詳細設定メニュー](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>[!DNL Adobe Analytics] をレポートソースとして使用する場合、設定は [!DNL Analytics] サーバーによって管理されます。この [!UICONTROL 詳細設定] オプションは使用できません。 詳しくは、 [Adobe TargetのレポートソースとしてのAdobe Analytics(A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### 依存関係を追加

詳細設定を使用すると、訪問者が別の指標を先に達成した場合に 1 つの指標のみを増分する、従属成功指標を作成できます。

![依存関係を追加](/help/main/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

例えば、テストコンバージョンが、訪問者がオファーをクリックした場合、または、コンバートする前に特定のページに到達する場合にのみ有効になることがあります。

依存関係機能は *not* は、次の場合にサポートされます。

* [!UICONTROL Recommendations アクティビティ。]それ以外のすべてのアクティビティタイプには対応しています。
* 次を使用する場合、 [レポートソースとしての Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。
* 「ページが表示されました」指標タイプ。
* Visual Experience Composer(VEC) アクティビティの「要素をクリックしました」指標タイプ。

従属成功指標は次の場合にはコンバートされません。

* 循環依存（指標 1 が指標 2 に依存し、指標 2 が指標 1 に依存する）を作成した場合、どちらの指標もコンバートできません。
* 自動パーソナライゼーションアクティビティではユーザーが作業をおこなう必要はなく、コンバージョン指標に到達するとアクティビティが再開されます。そのため、そのコンバージョン指標に依存する指標はコンバートされません。

### ユーザーがこの目標指標に達した後、どうなりますか？

ユーザーが目標指標に到達した後の動作について指定するには、詳細設定を使用します。次の表に、使用可能なオプションを示します。

| ユーザーがこの目標指標に達した後 | オプション |
|--- |--- |
| [!UICONTROL カウントを増分、アクティビティでユーザーを保持] | カウントの増分方法を指定します。<ul><li>参加者ごとに 1 回（デフォルト）</li><li>すべてのインプレッション（ページの更新を除く）</li><li>すべてのインプレッション</li></ul> |
| [!UICONTROL カウントを増分、ユーザーをリリース、再入場を許可] | 訪問者がアクティビティに再度入ったときに表示されるエクスペリエンスを選択します。<ul><li>同じエクスペリエンス（デフォルト）</li><li>ランダムエクスペリエンス</li><li>未表示のエクスペリエンス</li></ul> |
| [!UICONTROL カウントを増分、ユーザーをリリース、再入場を許可しない] | アクティビティのコンテンツの代わりにユーザーに表示する内容を指定します。<ul><li>同じエクスペリエンス（トラッキングなし）（デフォルト）</li><li>デフォルト／他のアクティビティのコンテンツ</li></ul> |

>[!NOTE]
>
>指標を [!UICONTROL カウントを増分] オプション（前述）の場合、指標カウントは、訪問者レベルで参加者ごとに 1 回だけ正しく増分されます。 指標のカウントは、訪問レベルの新しいセッションのたびに、訪問ごとに 1 回増分されます。

### カウントをどのように増分しますか。

目的の動作を選択します。

* 参加者ごとに 1 回
* すべてのインプレッション（ページの更新を除く）
* すべてのインプレッション

## 既知の問題

* 詳細オプション「カウントの増分方法」を「すべてのインプレッション」または「すべてのインプレッション（更新を除く）」に設定した成功指標を使用することはできません。これは、1 つの成功指標に別の指標が依存することになるためです。

成功指標がインプレッションごとに増分するように設定されている場合、 [!DNL Target] は、訪問者がこの成功指標を訪問するたびに訪問者を再度カウントします。 [!DNL Target] 次に、成功指標「メンバーシップ」を 0 にリセットし、次のインプレッションで再度カウントできるようにします。 したがって、別の指標が最初にこの指標を表示する必要がある場合、 [!DNL Target] は、ユーザーが最初の指標を閲覧したことを認識しません。

## トレーニングビデオ： アクティビティ指標

このビデオでは、アクティビティの指標の使用方法を示します。

* 「目標」指標の理解
* コンバージョン、売上高、エンゲージメントの各指標の理解と作成
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380)
