---
description: Automated Personalization アクティビティワークフローは、他のアクティビティのタイプで使用するワークフローとは異なります。
keywords: Automated Personalization;オーディエンス;アンサンブル;ランダムフォレスト;残差分散;誤差分散;生涯価値
seo-description: Automated Personalization アクティビティワークフローは、他のアクティビティのタイプで使用するワークフローとは異なります。
seo-title: Automated Personalization アクティビティの作成
solution: 'Target '
title: Automated Personalization アクティビティの作成
title-outputclass: Premium
topic: Advanced
uuid: 7d301dc3-6076-4e05-8abc-4978075a881e
badge: Premium
translation-type: tm+mt
source-git-commit: add895d353e7483dfcbe82f1bca55b277bc65f20

---


# ![Premium](/help/assets/premium.png) Automated Personalization アクティビティの作成{#create-an-automated-personalization-activity}

Automated Personalization アクティビティワークフローは、他のアクティビティのタイプで使用するワークフローとは異なります。

1. Target Standard アクティビティリストで、「**[!UICONTROL アクティビティを作成]**／**「[!UICONTROL Automated Personalization]**」の順にクリックします。

   ![アクティビティの作成:自動パーソナライゼーション](/help/c-activities/t-automated-personalization/assets/ap_create-new.png)

1. Visual Experience Composer（VEC）を使用するには、「**[!UICONTROL ビジュアル**]」（デフォルト）をクリックします。

   ![自動パーソナライゼーションアクティビティの作成ダイアログボックス](/help/c-activities/t-automated-personalization/assets/ap_url-new.png)

   フォームベースの Experience Composer を使用する場合、「[!UICONTROL フォーム]」を選択します。See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >VECおよびフォームベースのExperience Composerに加えて、Targetは単一ページアプリケーションVECおよびVEC forモバイルアプリを提供します。For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。
   >
   >The [!UICONTROL Choose Workplace] option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. このオプションが表示されない場合、組織にTarget Standardライセンスがあります。

1. (Conditional) If you are a Target Premium customer, [choose a workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. アクティビティ URL を確認または入力してから、「**[!UICONTROL 次へ]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://wwww.adobe.com`] の両方が一致します。

   指定された URL のページが Visual Experience Composer で開きます。

1. アクティビティに名前を付けるには、「名前」フィールドをクリックして、アクティビティ名を入力します。

   ![名前フィールド](/help/c-activities/t-automated-personalization/assets/ab_newname-new.png)

   次の文字はアクティビティ名として入力できません。

   | 文字 | 説明 |
   |--- |--- |
   | / | フォワードスラッシュ |
   | ? | 疑問符 |
   | # | 番号記号 |
   | : | コロン |
   | = | イコール |
   | + | プラス |
   | - | マイナス |
   | @ | アットマーク |

1. Modify page elements as explained in [Visual Experience Composer options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   アセットマネージャーから一度に複数の画像を選択できます。これにより、各画像がアクティビティ用に設定されたページをすばやく表示できます。また、オファー内のテキスト要素を容易に編集することもできます。要素を編集すると、その要素が変更されたことを示すバーが要素上に表示されます。

1. 「**[!UICONTROL コンテンツを管理]**」をクリックして、使用可能な組み合わせを設定します。

   ![コンテンツを管理オプション](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   ダイアログボックスが開き、画面上部に「エクスペリエンス」、「オファー」および「除外グループ」の 3 つのオプションが表示されます。

   ![コンテンツを管理ダイアログボックス](/help/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >AP アクティビティでは 30,000 個までエクスペリエンスを作成できますが、アクティビティが最高のパフォーマンスを発揮するのはエクスペリエンスが 5,000 個未満の場合です。

   [!UICONTROL エクスペリエンス]リストには、アクティビティ用に選択されたコンテンツの各部分と、それが割り当てられている場所が表示されます。

   エクスペリエンスを除外する際は、対象のエクスペリエンスにカーソルを合わせてから除外アイコンをクリックします。

   ![除外アイコンポイント](/help/c-activities/t-automated-personalization/assets/icon-exclude.png)

   関連するエクスペリエンスのチェックボックスを選択して、エクスペリエンスを除外/含めたり、ダイアログボックスの右上隅にある除外アイコンをクリックしたりできます。

   ![バッチ除外オプション](/help/c-activities/t-automated-personalization/assets/batch-exclude.png)

   You can filter this list view to see only excluded or only included activities by clicking the **Status** drop-down list.

1. （条件付き）「**[!UICONTROL オファー]**」をクリックして、コンテンツを選択してレポートグループに割り当てたり、ターゲット設定によって特定のオファーの閲覧を特定の訪問者のみに許可したりします。

   詳しくは、「[Automated Personalization のオファーレポートグループ](../../c-reports/offer-reporting-groups-in-automated-personalization.md#concept_194128C0B56B4B26AAB57DB49892960C)」を参照してください。

   場所を基準にしてオファーをフィルターするには、[!UICONTROL 場所]リストを使用します。レポートグループを基準にしてオファーをフィルターするには、[!UICONTROL レポートグループ]リストを使用します。また、[!UICONTROL レポートグループ]では、[!UICONTROL 割り当てられていないオファー]をフィルターして、現在どのレポートグループにも割り当てられていないオファーにレポートグループを割り当てることもできます。

   特定のエクスペリエンスをレポートグループに追加するには、目的のオファーにマウスポインターを置き、フォルダーアイコンをクリックします。

   ![フォルダアイコンのポイント](/help/c-activities/t-automated-personalization/assets/icon-folder.png)

   関連するエクスペリエンスのチェックボックスを選択して、レポートグループにエクスペリエンスを含めることができます。次に、ダイアログボックスの右上隅にあるレポートグループフォルダーアイコンボタンをクリックします。

   ![レポートグループオプション](/help/c-activities/t-automated-personalization/assets/report-group-options.png)

   レポートグループは、Target によるモデルの構築に影響することを念頭に置いてください。そのため、レポートグループは、アクティビティがライブの間にオファーを入れ替えたり新たに追加したりする予定がある場合のみ使用することをお勧めします。新しいオファーをライブのアクティビティに追加する場合は、それと似通ったオファーがあるグループに追加すると、グループ内の他の既存オファーで収集されているデータを、新しいオファーの学習に生かすことができます。すべてのオファーを 1 つのレポートグループに入れるのは避けてください。

   特定のオーディエンスに対するオファーのターゲット設定について詳しくは、「[AP オファーのターゲット設定](../../c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E)」を参照してください。

1. （条件付き）「**[!UICONTROL 除外グループ]**」をクリックして、アクティビティから除外する要素の組み合わせを選択します。

   ![「コンテンツを管理」ダイアログボックスの「排他グループ」タブ](/help/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   AP テストでは 30,000 個までエクスペリエンスを作成できますが、アルゴリズムが最高のパフォーマンスを発揮するのはエクスペリエンスが 10,000 個未満の場合です。

   アクティビティでまだ除外グループを使用していない場合は、「**除外グループを作成**」をクリックします。リストにフィルターを適用し、除外する組み合わせのみを表示できます。除外グループに名前を付け、「**保存**」をクリックします。

   既存の除外グループを編集するには、編集するグループにカーソルを合わせてから鉛筆アイコンをクリックします。

1. Click **[!UICONTROL Done]** when you have finished setting up the content of your activity.

1. **ターゲット設定** のステップは、Target の他のタイプのアクティビティと同様です。ここでは、オーディエンスを選択してから、「**[!UICONTROL カスタム配分]**」ドロップダウンリストをクリックして、コントロールエクスペリエンスを表示する訪問者の割合を指定し、「**次へ**」をクリックできます。

   [!UICONTROL カスタム配分]ドロップダウンリストで、以下のオプションを選択できます。

   ![トラフィック配分目標ドロップダウンリスト](/help/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **パーソナライゼーションアルゴリズムを評価 (50/50)：** 目標がアルゴリズムのテストの場合は、50:50 の比率でコントロールとターゲットアルゴリズムに訪問者を配分します。この配分により、上昇率を最も正確に推定できます。コントロールとして「ランダムエクスペリエンス」を使用することを推奨します。
   * **パーソナライゼーショントラフィックを最大化 (90/10)：**「常時稼働」のアクティビティを作成することが目標の場合は、10％の訪問者をコントロールに配分し、アルゴリズムによる学習の継続に必要なデータを確保します。この場合は、トラフィックの大部分をパーソナライズ対象に回す代わりに、推定上昇率の精度が落ちるというデメリットがあります。目標にかかわらず、これは特定のエクスペリエンスをコントロールとして使用する場合の推奨トラフィックです。
   * **配分をカスタマイズ**： 配分の割合を手動で調節します。

1. (Conditional) From the [!UICONTROL Control] drop-down list, [select a specific experience to be used as control](/help/c-activities/t-automated-personalization/experience-as-control.md) or select [!UICONTROL Random Experience.]

   コントロールエクスペリエンスは、自動テストによってどれだけの上昇率を実現するかを判断するための比較となります。

   Automated Personalization は、常にコントロールグループに基づいてパフォーマンスを測定します。少なくとも訪問者の 10％はコントロールグループに配分することをお勧めします。与えられたデータに対し、パーソナライゼーションアルゴリズムがパーソナライゼーションなしの場合（コントロールでエクスペリエンスがランダムに提供される場合）と比べ、優れたパフォーマンスを発揮するかどうかをテストすることが目標の場合は、コントロールとパーソナライゼーションアルゴリズムの配分を 50:50 に設定すると、最も早く、最も精度の高いテスト結果が得られます。パーソナライゼーション対象のトラフィック量を最大化したいと考えており、アクティビティの上昇率の正確性が多少低くても構わない場合は、コントロールとパーソナライゼーションアルゴリズムに 10:90 でトラフィックを配分すると、最も早く、最も精度の高いテスト結果が得られます。

   >[!NOTE]
   >
   >Automated Personalization アクティビティでは、エントリ基準（URL ターゲット設定、テンプレートルール、オーディエンスのターゲット）がリクエストごとに評価されます。以前のバージョンでは、エントリ条件はセッションごとに 1 度評価されていました。

1. Click **[!UICONTROL Next]** to display the **[!UICONTROL Goals &amp; Settings]** page.
1. 次の設定を使用してアクティビティを構成し、「**[!UICONTROL 保存して閉じる**]」をクリックします。

   | 設定 | 説明 |
   |--- |--- |
   | 名前 | アクティビティの名前を設定します。チームメンバーがアクティビティリストでアクティビティを認識できるように、十分にわかりやすい名前を付けます。上記の表を参照して、アクティビティ名で許可されていない文字を確認してください。 |
   | 目的 | （オプション）テストの目的を入力します。目的を設定しておくと、アクティビティの用途を覚えやすくなります。 |
   | 優先度 | 優先度の UI とオプションは、設定によって変わります。従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。<br>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<br>「セットアップ」でこのオプションが有効（デフォルト）になっていない場合は、「低」、「中」、「高」のいずれかの優先度を指定します。<br>優先度の詳細設定を有効にするには、「[!UICONTROL セットアップ]」をクリックしてから、「[!UICONTROL 詳細なプロパティを有効にする]」オプションを「オン」に設定します。<br>このオプションを有効にした場合は、0～999 の値を指定します。<ul><li>0 = 低</li><li>999 = 高</li></ul>Target Standard/Premium の以前のバージョンで作成されたアクティビティについては、低の優先度は 0 に、中は 5 に、高は 10 に変換されます。これらの値は必要に応じて調整できます。<br>**注意**： 優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。 |
   | 期間 | アクティビティの開始日と終了日を設定します。 |
   | 最適化目標 | 以下の 2 つのパラメーターを使用して最適化目標を指定します。<ul><li>このアクティビティで測定するもの</li><li>その目標が達成されたことを示すアクティビティ参加者によって取られるアクション。</li></ul>主な目標の右側にある 3 ドットメニューをクリックし、最適化目標に名前を付けることもできます。Automated Personalization のアクティビティは、コンバージョン、RPV および AOV を測定します。コンバージョンは、ページまたは mbox が表示されると達成されます。クリックを追跡することもできます。<br>また、主な目標はモデリング指標になり、モデリングシステムによってエクスペリエンスの成功を計算するために使用されます。<br>モデリングの目標に達した後も、訪問者をアクティビティ内にとどめて、追跡の対象とすることができます。例えば、Automated Personalization アクティビティは、多くの場合、クリック率の向上を目的に使用され、クリック率がモデリング目標として設定されます。しかし、クリック率の向上が最終的にどのようにコンバージョンにつながっているかを確認することが重要なので、最終的なコンバージョンまで追跡することが欠かせません。<br>複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。<br>成功指標の依存関係を設定する前に、両方（または複数）の成功指標を定義する必要があります。<br>「依存関係を追加」オプションを利用すると、ある成功指標に到達した場合、または到達しなかった場合に別の成功指標を増分するよう設定できます。<br>依存関係を追加する手順は次のとおりです。<ol><li>指標を追加したら、追加の目標の右側にある 3 ドットメニューで「[!UICONTROL 詳細設定]」をクリックします。</li><li>「[!UICONTROL レポート設定]」セクションの下部にある「[!UICONTROL 依存関係を追加]」オプションをクリックします。</li><li>目的の指標を左側のパネルから右側のパネルにドラッグ＆ドロップしてから、「[!UICONTROL 到達]」をクリックし、「[!UICONTROL 到達]」と「[!UICONTROL 未到達]」を切り替えて設定します。</li></ol>追加した依存関係は後で編集または削除できます。 |
   | コンバージョン指標 | デフォルトでは、コンバージョン指標は最適化目標指標と同じです。ただし、「[!UICONTROL 最適化目標と同じ]」オプションをオフにすれば、個別のコンバージョン指標を定義できます。 |
   | 追加の指標 | 使用する他のレポート指標を追加します。コンバージョンまたは売上高指標を追加できます。<br>**注意**： エンゲージメント指標は追加の指標として使用できません。UI ではエンゲージメント指標を選択できる場合がありますが、レポートにデータが正確に表示されません。 |
   | レポート対象のオーディエンス | オーディエンスを追加して、レポートでオーディエンスによるフィルタリングを可能にします。デフォルトでは、レポートにすべての認定訪問者の結果が表示されます。オーディエンスを追加して結果をフィルタリングすると、訪問者をさらに絞り込むことができます。<br>**注意**： 他のアクティビティタイプと異なり、Automated Personalization ではレポートソースとして Adobe Analytics を使用できません。 |
   | メモ | アクティビティに関して、自分自身または他のチームメンバーにとって手元にあると便利な情報を入力します。メモウィンドウはサイズ変更可能です。 |

   指標に名前を付けたり、名前を変更したりする場合、以下の文字は使用できないことに注意してください。

   | 文字 | 説明 |
   |--- |--- |
   | / | フォワードスラッシュ |
   | ? | 疑問符 |
   | # | 番号記号 |
   | : | コロン |
   | = | イコール |
   | + | プラス |
   | - | マイナス |
   | @ | アットマーク |

「**[!UICONTROL 作成]**」をクリックすると、アクティビティの概要が表示されます。エクスペリエンスが提供されたときにどのように表示されるかをプレビューするには、「**エクスペリエンスをプレビュー**」をクリックします。ポップアップが表示されます。このポップアップを使用して、サイト上の AP エクスペリエンスへのリンクを表示および共有して、Target の Visual Experience Composer の外部でエクスペリエンスの「実際の表示」をプレビューできます。プレビューを共有するには、メッセージに表示されたリンクを共有する必要があります。URL にはメッセージ内のリンクからページにアクセスしたときにのみページが正しく表示されるパラメーターが含まれているので、リンクをクリックして、ページから直接 URL をコピーしても、うまく動作しません。

詳しくは、「[Automated Personalization レポート](../../c-reports/reports-ap.md#concept_C02BAFC922114A44846998FD956E345A)」を参照してください。
