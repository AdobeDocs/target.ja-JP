---
keywords: 自動パーソナライゼーション；アプリ
description: '[!UICONTROL Visual Experience Composer]を使用して[!UICONTROL Automated Personalization] （AP） アクティビティを作成する方法について説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティを作成するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
TQID: 'https://experienceleague.adobe.com/5eUFwob4BekIJP4SM2lrSDQam4h1AXIByJjM7-1RNL8'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: c86619f0c004279bf4d9b871c84bf2e37ba932b7
workflow-type: tm+mt
source-wordcount: '1963'
ht-degree: 20%
---
# [!UICONTROL Automated Personalization] アクティビティの作成 {#create-ap-activity}

>[!BEGINSHADEBOX]

**このページ：** **[!UICONTROL Visual Experience Composer]** （VEC）で&#x200B;**[!UICONTROL Automated Personalization]** （AP）アクティビティを作成する方法を説明します。 エクスペリエンスを構築し、ターゲティングとコントロールグループを設定し、目標と設定を設定します。

>[!ENDSHADEBOX]

[!DNL Target]の&#x200B;**[!UICONTROL Automated Personalization]** アクティビティワークフローは、他のアクティビティタイプのワークフローとは異なります。 これは、**[!UICONTROL Visual Experience Composer]**&#x200B;の3段階のガイド付きワークフローに従います。

1. [エクスペリエンスの構築](#build-experiences)
1. [ターゲティングの設定](#set-targeting)
1. [目標と設定の設定](#configure-goals-and-settings)

## 始める前に {#before-you-begin}

最適なパフォーマンスを得るには、**[!UICONTROL Automated Personalization]**&#x200B;および&#x200B;**[!UICONTROL 自動ターゲット]** アクティビティを次の制限内に収めてください。

* 4～6か所、1か所あたり4～6件のオファーを提供。
* 総エクスペリエンス数が5,000件未満であれば、優れた結果が得られます。 ハード制限は30,000で、「**[!UICONTROL 重複を許可しない]**」オプションが有効になっている場合も同じ制限が適用されます。

エクスペリエンスの総数は、場所とオファーのデカルトの組み合わせから増加します。 大規模な設定を行うと、**[!UICONTROL Visual Experience Composer]**&#x200B;での読み込みや編集が遅くなる可能性があります。

## ステップ 1：エクスペリエンスの構築 {#build-experiences}

**[!UICONTROL Automated Personalization]**&#x200B;がパーソナライズできるコンテンツバリエーションのプールを定義します。 顧客体験やオファーが豊かで明確であればあるほど、アルゴリズムが各訪問者に適切なコンテンツを提供できるようになります。

### アクティビティの作成 {#create-activity}

アクティビティを開始し、**[!UICONTROL Visual Experience Composer]** （VEC）でパーソナライズするページを開きます。

1. [!DNL Target] **[!UICONTROL アクティビティ]** リストから、**[!UICONTROL アクティビティの作成]** > **[!UICONTROL Automated Personalization]**&#x200B;をクリックします。

   ![](../assets/ap-activities-2.png)

1. Experience Composerを選択します。

   * **[!UICONTROL Visual Experience Composer]** （VEC）を使用するには、**[!UICONTROL Visual]**&#x200B;をクリックします。

   * **[!UICONTROL フォームベースのExperience Composer]**&#x200B;を使用するには、代わりに&#x200B;**[!UICONTROL Form]**&#x200B;を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

     >[!NOTE]
     >
     >VECおよび&#x200B;**[!UICONTROL フォームベースのExperience Composer]**&#x200B;に加えて、[!DNL Target]では&#x200B;**[!UICONTROL シングルページアプリケーション VEC]**&#x200B;を提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。 VECに関するトラブルシューティング情報については、[Visual Experience Composerのトラブルシューティング ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

     ![](../assets/ap-activities-3.png)

1. （条件付き） [ ワークスペースを選択](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 「**[!UICONTROL アクティビティ URLを入力]**」ボックスに、[ アクティビティ URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)を指定します。 アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。 必要に応じて、デフォルトから別のURLに変更できます。

   [!DNL Target]はURL プロトコル （[!DNL https]と[!DNL http]）を区別しません。 結果、[!DNL `http://www.adobe.com`]と[!DNL `https://www.adobe.com`]は両方とも一致します。

1. 次に、**[!UICONTROL 作成]**&#x200B;をクリックします。 指定されたURLを持つページがVECで開きます。

1. アクティビティに名前を付けるには、**[!UICONTROL 編集]** アイコン （![編集アイコン ](/help/main/assets/icons/Edit.svg)）をクリックし、アクティビティのわかりやすい名前を指定して、**[!UICONTROL 保存]**&#x200B;をクリックします。

   {{activity-name-rules}}

   ![](../assets/ap-activities-1.png)

### コンテンツのデザイン {#design-content}

アルゴリズムが組み合わせることができるコンテンツを設定し、望ましくないエクスペリエンスを除外します。

1. [Visual Experience Composer オプション ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)で説明されているように、ページ要素を変更します。

   * 複数の画像をすばやくプレビューするには、アセットマネージャーから一度に複数の画像を選択します。 次に、アクティビティ用に設定された各画像を含むページを表示できます。
   * オファーのテキストを変更するには、ページ上でテキスト要素を直接編集します。

   エレメントを編集すると、変更したことを示すバーがそのエレメントに表示されます。

1. 「**[!UICONTROL コンテンツを管理]**」アイコン（![ コンテンツを管理アイコン ](/help/main/assets/icons/Experience.svg)）をクリックして、使用可能な組み合わせを設定します。

   「**[!UICONTROL コンテンツを管理]**」ダイアログボックスが開き、2つのタブ（**[!UICONTROL エクスペリエンス]**&#x200B;と&#x200B;**[!UICONTROL オファー]**）が表示されます。

   ![](../assets/ap-activities-4.png)

1. 「**[!UICONTROL エクスペリエンス]**」タブで、コンテンツのリストと、各コンテンツが割り当てられている場所を確認します。

1. （オプション）アクティビティからエクスペリエンスを除外するには、除外する各エクスペリエンスのチェックボックスを選択し、**[!UICONTROL 除外]** アイコンをクリックします。

   詳細なオプションについては、[除外の管理](/help/main/c-activities/t-automated-personalization/managing-exclusions.md)を参照してください。

   ![](../assets/ap-activities-5.png)

1. （条件付き）「**[!UICONTROL オファー]**」タブをクリックして、アクティビティ内のオファーを管理します。

   * レポート用のオファーを整理するには、コンテンツの一部を選択してレポートグループに割り当てます。 詳しくは、[Automated Personalizationのオファーレポートグループ ](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)を参照してください。
   * オファーを表示するユーザーを制限するには、ターゲティングを使用して、特定の訪問者にそのオファーを表示させるようにします。

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the **[!UICONTROL Disallow Duplicates]** option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.
-->

1. アクティビティのコンテンツの設定が完了したら、**[!UICONTROL 完了]**&#x200B;をクリックします。

## 手順2：ターゲティングの設定 {#set-targeting}

アクティビティに参加する訪問者と、公開されるトラフィックの量を決定します。 これらをコントロール グループと組み合わせて、[!DNL Target]がパーソナライゼーションの成果を測定できるようにします。

1. **[!UICONTROL Visual Experience Composer]**&#x200B;の上部にある&#x200B;**[!UICONTROL ターゲティング]**&#x200B;をクリックして、3段階のガイド付きワークフローの次のステップに移動します。

   ![AP テストのターゲット設定ステップ ](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

1. （条件付き）「**[!UICONTROL すべての訪問者]**」コントロールをクリックして[ アクティビティ用に別のオーディエンス ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択し、その訪問者の割合を設定します。

   **[!UICONTROL すべての訪問者]** オーディエンスがデフォルトとして設定されます。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。 例えば、すべての訪問者の 50％に参加を制限したり、カリフォルニア州のオーディエンスの 45％に参加を制限したりできます。

1. 「**[!UICONTROL トラフィック配分]**」コントロールをクリックし、次のいずれかのオプションを選択します。

   ![ トラフィック配分の目標オプション ](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   +++トラフィック配分の目標オプション

   | オプション | 使用するタイミング |
   |--- |--- |
   | **[!UICONTROL パーソナライゼーションアルゴリズムを評価（50/50）]** | ここでの目的は、アルゴリズムをテストすることです。 訪問者は、コントロールとターゲットアルゴリズムの間で50対50で分けられます。 この分割により、上昇率の最も正確な推定値が得られ、アルゴリズムのパフォーマンスがパーソナライゼーションがない場合（ランダムに提供されたコントロールなど）よりも優れているかどうかをテストするための最も迅速かつ正確な方法です。 「ランダムエクスペリエンス」をコントロールとして使用する場合にお勧めします。 |
   | **[!UICONTROL Personalization トラフィックの最大化（90/10）]** | あなたの目標は、「常に」活動を作成することです。 訪問者の10%が制御を利用するため、アルゴリズムが継続的に学習するのに十分なデータを保持できます。 これは、正確な上昇率に気づいていない場合にパーソナライズされるトラフィック量を最大化するための、最も迅速で正確な方法です。 トレードオフは、正確なリフトが何であるかについての精度が低いことです。 目標に関係なく、このオプションは、特定のエクスペリエンスをコントロールとして使用する場合に推奨されるトラフィック分割です。 |
   | **[!UICONTROL カスタム配分]** | パーセンテージを手動で分割する場合。 |

   +++

1. （条件付き）「**[!UICONTROL コントロール]**」ドロップダウンリストから、[ コントロールとして使用する特定のエクスペリエンスを選択](/help/main/c-activities/t-automated-personalization/experience-as-control.md)するか、**[!UICONTROL ランダムなエクスペリエンス]**&#x200B;を選択します。

   コントロールエクスペリエンスは、自動テストによってどれだけの上昇率を実現するかを判断するための比較となります。 **[!UICONTROL Automated Personalization]**&#x200B;は、コントロール グループに対するパフォーマンスを常に測定します。 少なくとも訪問者の 10％はコントロールグループに配分することをお勧めします。

   >[!NOTE]
   >
   >**[!UICONTROL Automated Personalization]** アクティビティでは、各要求に対してエントリ条件（URL ターゲティング、テンプレートルール、オーディエンスターゲット）が評価されます。 以前のバージョンでは、エントリ条件はセッションごとに 1 度評価されていました。

## 手順3：目標と設定の設定 {#configure-goals-and-settings}

[!DNL Target]の成功例を説明してください。 選択した最適化の目標は、パーソナライゼーションアルゴリズムが対象とする指標です。そのため、このアクティビティにとって最も重要な結果を選択してください。

1. 「**[!UICONTROL 次へ]**」をクリックして、**[!UICONTROL 目標と設定]** ページを表示します。

1. 次の設定でアクティビティを設定し、**[!UICONTROL 保存して閉じる]**&#x200B;をクリックします。

   | 設定 | 説明 |
   |--- |--- |
   | **[!UICONTROL Name]** | アクティビティの名前を設定します。 チームメンバーが&#x200B;**[!UICONTROL アクティビティ]** リストでアクティビティを認識できるほど、わかりやすい名前をアクティビティに付けます。 「[手順1：エクスペリエンスを構築](#build-experiences)」で説明されているアクティビティ名のルールに従います。 |
   | **[!UICONTROL 目標]** | （オプション）テストの目的を入力します。 目的を設定しておくと、アクティビティの用途を覚えやすくなります。 |
   | **[!UICONTROL 優先順位]** | 複数のアクティビティが場所とオーディエンスを共有する場合に表示されるアクティビティを決定します。 [優先度の設定](#set-priority)を参照してください。 |
   | **[!UICONTROL 期間]** | アクティビティの開始日と終了日を設定します。 「**[!UICONTROL When Activated]**」を選択するか、特定の日時を指定できます。 |
   | **[!UICONTROL 最適化の目標]** | パーソナライゼーションアルゴリズムが訓練する指標。 [最適化目標の設定](#set-optimization-goal)を参照してください。 |
   | **[!UICONTROL コンバージョン指標]** | デフォルトでは、コンバージョン指標は最適化目標指標と同じです。 ただし、「**[!UICONTROL 最適化目標と同じ]**」オプションのチェックを外すことで、別のコンバージョン指標を定義できます。 |
   | **[!UICONTROL 追加指標]** | 使用する追加のレポート指標を追加します。 コンバージョンまたは売上高指標を追加できます。<P>**注**: **[!UICONTROL エンゲージメント]**&#x200B;指標は、追加指標としてサポートされていません。 [!DNL Target] UIで&#x200B;**[!UICONTROL エンゲージメント]**&#x200B;指標を選択できる場合がありますが、データはレポートに正確に表示されません。 |
   | **[!UICONTROL レポート用オーディエンス]** | オーディエンスを追加して、レポートでオーディエンスによるフィルタリングを可能にします。 デフォルトでは、レポートにすべての認定訪問者の結果が表示されます。 オーディエンスを追加して結果をフィルタリングすると、訪問者をさらに絞り込むことができます。<P>**メモ**：他のアクティビティの種類とは異なり、**[!UICONTROL Automated Personalization]**&#x200B;では&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;をレポートソース（A4T）として使用できません。 |
   | **[!UICONTROL メモ]** | 自身や他のチームメンバーにとって役立つアクティビティ情報を入力します。 **[!UICONTROL メモ]** ペインはサイズ変更可能です。 |

   指標に名前を付けたり名前を変更したりする場合、次の文字は使用できません：`/`、`?`、`#`、`:`、`=`、`+`、`-`、および`@`。

### 優先度の設定 {#set-priority}

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。

設定に応じて、**[!UICONTROL 優先度]**&#x200B;の[!DNL Target] UIとオプションは異なります。

* **従来の優先度（デフォルト）:**&#x200B;きめ細かい優先度が有効になっていない場合は、**[!UICONTROL 低]**、**[!UICONTROL Medium]**、**[!UICONTROL 高]**&#x200B;の優先度を指定します。
* **きめ細かい優先度：** 0 ～ 999の値を指定します。0 = Lowおよび999 = Highです。 このオプションを有効にするには、**[!UICONTROL 管理]** > **[!UICONTROL レポート]**&#x200B;をクリックし、**[!UICONTROL きめ細かい優先度を有効にする]** オプションを「オン」の位置に切り替えます。

以前のバージョンの[!DNL Target Standard/Premium]で作成されたアクティビティの場合、**[!UICONTROL 低]**&#x200B;の優先度は0に変換され、**[!UICONTROL Medium]**&#x200B;の優先度は5に変換され、**[!UICONTROL 高]**&#x200B;の優先度は10に変換されます。 これらの値は必要に応じて調整できます。

>[!NOTE]
>
>きめ細かい優先度を使用した後に無効にする前に、すべての優先度を0、5、および10に戻す必要があります。

### 最適化目標の設定 {#set-optimization-goal}

最適化の目標は、次の2つのパラメーターで構成されます。

* このアクティビティで測定するもの
* 目標が達成されたことを示すアクティビティ参加者のアクション

**[!UICONTROL プライマリ目標]**&#x200B;の右側にある3つのドットを選択して、最適化目標に名前を付けることができます。 **[!UICONTROL Automated Personalization]**&#x200B;のアクティビティは、**[!UICONTROL コンバージョン]**&#x200B;または&#x200B;**[!UICONTROL 収益]**&#x200B;を測定できます。 コンバージョンは、ページを表示するか、mboxを表示することで達成できます。 クリックを追跡することもできます。

また、主な目標は、モデリングシステムがエクスペリエンスの成功を計算するために使用するモデリング指標になります。

モデリングの目標に達した後も、訪問者をアクティビティ内にとどめて、追跡の対象とすることができます。 例えば、多くの場合、**[!UICONTROL Automated Personalization]** アクティビティを使用してクリック率を向上させ、これがモデリング目標として設定されます。 しかし、クリック率の向上が最終的なコンバージョンにつながるかどうかを確認することは重要であり、最終的なコンバージョンを追跡することが不可欠です。

#### ある指標を別の指標に依存させる {#add-dependency}

複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。 成功指標の依存関係を設定する前に、両方（または複数）の成功指標を定義する必要があります。 「**[!UICONTROL 依存関係を追加]**」オプションを利用すると、ある成功指標に到達した場合、または到達しなかった場合に別の成功指標を増分するよう設定できます。

依存関係を追加する手順は次のとおりです。

1. 追加の指標を追加したら、**[!UICONTROL 追加の目標]**&#x200B;の右側にある3点メニューの下の&#x200B;**[!UICONTROL 詳細設定]**&#x200B;をクリックします。

1. 「**[!UICONTROL レポート設定]**」セクションの下部にある「**[!UICONTROL 依存関係を追加]**」オプションをクリックします。

1. 目的の指標を左側のパネルから右側のパネルにドラッグ＆ドロップしてから、「**[!UICONTROL 到達]**」をクリックし、「**[!UICONTROL 到達]**」と「**[!UICONTROL 未到達]**」を切り替えて設定します。

追加した依存関係は後で編集または削除できます。

## エクスペリエンスのプレビュー {#preview-experiences}

アクティビティを開始する前に、サイトでのエクスペリエンスの外観を確認します。

1. **[!UICONTROL 保存して閉じる]**&#x200B;をクリックすると、アクティビティの&#x200B;**[!UICONTROL 概要]** ページが表示されます。 「**エクスペリエンスをプレビュー**」をクリックします。

1. 表示されるポップアップで、サイト上のAP エクスペリエンスへのリンクを表示および共有します。 これらのリンクは、**[!UICONTROL Target]** **[!UICONTROL Visual Experience Composer]** （VEC）以外のエクスペリエンスの「真のプレビュー」を提供します。

   >[!NOTE]
   >
   >プレビューを共有するには、メッセージに表示されたリンクを共有する必要があります。 リンクをクリックした後、ブラウザーから直接URLをコピーしても機能しません。 リンクをコピーすると、メッセージ内のリンクからページにアクセスする場合にのみ、ページを正しく表示するパラメーターがURLに含まれます。

詳しくは、「[Automated Personalizationレポート](/help/main/c-reports/personalization-reports/reports-ap.md)」を参照してください。
